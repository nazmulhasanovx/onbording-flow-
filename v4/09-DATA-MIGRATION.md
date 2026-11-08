# 09 — Proposed Data Architecture / Migration Impact
Status: Conceptual design only. Current HMS database, API, integrations and live schemas were NOT inspected.

## Entities and relationships
~~~text
ACCOUNT / USER
  -> PROPERTY_MEMBERSHIP {property_id, role, status}
PROPERTY {id, type, name, timezone, contact, onboarding_status}
  -> PROPERTY_PROFILE, PROPERTY_OPERATING_DEFAULTS
  -> ACCOMMODATION_CONFIGURATION {version}
      -> LOCATION_NODE {id, property_id, parent, kind, label, code}
      -> NUMBERING_POLICY {property_id, type, location_strategy, format}
  -> ACCOMMODATION_CATEGORY {id, property_id, accommodation_type,
       occupancy, beds, amenities, gallery, video, default_rate, strategy}
      -> UNIT {id, property_id, category_id, unique_display_code,
               location_id, operational_state, exceptions}
          -> UNIT_DATE_BLOCK / RATE_DATE_OVERRIDE / BOOKING_ALLOCATION
  -> RESERVATION {id, property_id, stay_dates, status, guest_id}
      -> RESERVATION_UNIT_ASSIGNMENT
  -> SUBSCRIPTION {property_id, plan_version, quantity, cycle, status}
      -> QUOTE -> ACCEPTANCE -> INVOICE -> PAYMENT
  -> SERVICE_ORDER {activation/training, fee, promotion_snapshot, status}
  -> PROPERTY_APPROVAL {submitted_version, reviewer, decision, corrections}
  -> DIGITAL_CHANNEL {website/marketplace/OTA, readiness_state}
~~~
One Account can have multiple Property memberships; a Property can have multiple Accommodation Types; a Category has many Units. A whole Villa or Apartment with 3 bedrooms remains one UNIT.

## Important implementation constraints
- Data scoping: every property-owned read/write checks authenticated user property membership and server authorization. Client-supplied property_id is never trusted alone.
- Stable internal IDs vs display names/numbering; unique normalized display Unit code within property (DB constraint, transaction-safe idempotent single-Unit draft registration).
- Save mutable configuration as versioned records; already booked inventory is preserved, no silent cascade after changing a building name or numbering policy.
- Reservation allocation conflicts must block overlapping bookings and maintenance for same physical sellable unit; proper transaction isolation.
- Category photos and optional YouTube tour inherited by Unit with explicit replace/hide override; validate hosted content.
- Commercial snapshot includes exact monthly rate, Q, billing cycle, discount, activation waiver, training shifts/fees, fee-free modules, tax context, acceptance and version.
- S3/object storage/backup/cache/exports must enforce property separation; do not leak IDs, NID, trade licenses or personally identifying guest documents into public design files.
- Subscription, property approval, service order and digital publishing must not be represented by one boolean.
- Feature entitlement policy at server and audit scope; plan change never destroys history.

## Existing-system compatibility checklist before code changes
1. Inspect real production Room schema, live reservations, guest-side room filters and booking calendar; design mapping table, not blind replace.
2. Validate migration of legacy Room Type -> Accommodation Category and Room Number -> physical UNIT without losing booking assignments.
3. Preserve routes/API keys/permitted integrations; UI dynamic Rooms/Accommodations label is separate from database renaming.
4. Test website themes, guest Stays, online/offline booking, availability sync, housekeeping, rates, payments, finance reports, OTA interfaces.
5. Prepare database migration/backfill, auditing, duplicate ID inspection, feature flags and rollback plan; test with staging copy and redacted data.
6. Do not turn on Dormitory per-bed inventory until its distinct accounting/booking model is approved.
7. No production migration is authorized by this document.

## API boundary examples (conceptual, not real endpoints)
- GET authorized properties -> return only memberships.
- GET property setup -> scoped by authorized property, minimum necessary data.
- POST category/units -> server validates category belongs to same property, location type, quota, conflicts and uniqueness.
- POST owner submission -> idempotent, validates required fields and quote snapshot.
- POST admin decision -> dedicated audit, authorized reviewer, no automatic payment.
- POST channel publication -> separate readiness gate and channel permission.

# 01 — ROOM Onboarding Journey (Review Draft)

**Status:** DRAFT — awaiting individual review; not implemented.  
**Priority:** P0 / first journey to review.  
**Use case:** Property has one or more actual Hotel Rooms. **Hotel is a property type; Room is an accommodation type.** Hotel/Resort/Guest House may enable Room alongside other accommodation types.

## A. Property entry, once per new property

```text
OWNER REGISTERS ACCOUNT (once) -> verifies mobile/email as applicable
  -> CREATE PROPERTY DRAFT [property_id]
  -> Property Profile: name, kind, official contact, address, map optional
  -> Select PLAN + subscribed physical unit capacity + setup support
  -> Save ONE set of operating defaults:
     BDT/timezone as appropriate, language, check-in/out, tax, basic policies
  -> ACCOMMODATION TYPES [Enable Room]
     (Other types may be independently enabled within same property)
  -> ROOM LOCATION PRESET [Recommended: Building -> Floor]
     -> Existing building/floor locations for THIS property?
        YES -> reuse existing nodes, no duplicated entry
        NO -> guided location setup for only what's missing
  -> NUMBERING RULE PREVIEW
     -> choose floor-code, separator, padding, sequence start, reserved codes
     -> suggested Floor 1: 101..199; Floor 2: 201..299
     -> support nonconsecutive 101, 103, 105
     -> multiple buildings: qualified codes, e.g. MAIN-101 / ANNEX-101
     -> ground/basement/mezzanine + 100+ floors: configured tokens and collision checks
  -> SAVE VERSIONED ROOM CONFIGURATION
```

**Do not** assume all hotels use floors. Owner may explicitly choose a valid floor-less configuration. Do not force extra buildings or repeat property information. Keep the source of truth in this property's saved configuration.

## B. Room category and physical units (shared 5-stage wizard)

```text
ACCOMMODATIONS / ROOMS DASHBOARD
  -> + New Accommodation
  -> [1] TYPE: ROOM (selected; only enabled types available)
  -> [2] CATEGORY
     -> Select existing Room Category?
        YES -> load saved beds/capacity/amenities/photos/base rate/location strategy
        NO  -> Create Room Category
               name (Deluxe Twin), style (Twin/Double/Single/Suite/etc.)
               max adults/children; bed type/count; size; bathroom/accessibility
               description, photos, amenities, optional YouTube Video Tour
               base rate and policy; valid Building->Floor strategy
               Save Category for future reuse
  -> [3] LOCATION & PHYSICAL ROOM UNITS
     -> Load category's saved location path
     -> Building [auto if sole choice, otherwise select saved building]
     -> Floor [choose existing floor if floor-based]
     -> Numbering modes: single / Generate N / range / manual / selectable preview
     -> Suggestions: 101,102,103,104,105
     -> Operator chooses: 101,103,105 (no requirement to create 102/104)
     -> Validate all codes, conflicts, location, plan capacity; show EXACT resulting list
  -> [4] DETAILS & PRICING
     -> inherited category price, beds, photos, amenities, policies
     -> optional room-level notes/media/rate overrides (permission dependent)
     -> operational state Active / Inactive / Out of Service
  -> [5] REVIEW / CREATE
     -> Room / Deluxe Twin / Main Building / Floor 1
     -> Units to create: [101,103,105] — exactly 3 physical rooms
     -> Save Draft or Create & Publish (publish gated by proper readiness)
  -> ROOM INVENTORY DASHBOARD
     -> Unit 101 | Deluxe Twin | Main / Floor 1
     -> Unit 103 | Deluxe Twin | Main / Floor 1
     -> Unit 105 | Deluxe Twin | Main / Floor 1
```

**Returning fast path:** Room -> existing category -> saved Floor -> chosen unique numbers -> review/create. Never ask to redefine beds or building/floor configuration.

## C. Finish property's overall onboarding (not independent Room-only signup)

```text
Room Units saved
  -> set rates, day-specific availability/restrictions, applicable taxes/charges
  -> confirm or import existing reservations, holds and maintenance blocks
  -> validate no overlaps/double-booking; distinguish Operational vs Dated Availability
  -> configure plan-enabled staff/operations and guest payments
  -> preview property website/listing (keep DRAFT, not publicly sellable)
  -> submit required owner/business verification + final property checklist
  -> OWNER SUBMITS PROPERTY -> BinGi team REVIEW
        -> needs changes: exact correction link -> resubmit
        -> approved: plan-entitled HMS dashboard unlocked
  -> Online website/marketplace publishing requires independent channel readiness
```

## D. Exact field ownership / inherited values

| Field | Configure in | Reuse |
| --- | --- | --- |
| Property identity/contact | Property Profile | All subsequent steps |
| Currency, time zone, check-in/out, taxes | Operating Defaults | Room rates & reservations |
| Building/Floor nodes | Property Accommodation Configuration | All Room categories/units |
| Numbering format | Numbering policy | Room unit creation |
| Beds, capacity, media, facilities, base rate | Room Category | Future physical Rooms |
| Actual number, floor, unit exceptions, operational state | Physical Unit | Booking/housekeeping/maintenance |
| Dates, allocation and booking state | Reservation/availability | Calendar & public channels |

## E. Product validation / acceptance

1. Only authorized property nodes/categories/units are queried; no data leakage across properties. Server validates `property_id` and permissions.
2. Floor 1 -> 101/103/105 creates precisely three units, not five; duplicate 103 fails with no silent overwrite. Concurrent creates protected by database constraints/transactions.
3. Multiple buildings cannot both create ambiguous visible code 101; rule qualifies or rejects duplicate property-wide code.
4. Floor 100+, floor aliases and no-floor categories remain valid under explicit numbering policy; do not concatenate blindly.
5. Category-level video is optional; units inherit; per-unit override may replace/hide; photos-only valid.
6. Room holds/bookings/maintenance dates prevent incompatible edits; use immutable internal IDs and audit.
7. Room is one whole physical sellable unit, even if Suite describes multiple subspaces; no bedroom-level sale.
8. Existing bookings must be reconciled before public inventory is enabled; a DRAFT is never bookable.
9. Plan capacity is not the owner-entered total property size: display actual created units, declared units, purchased limit separately.
10. Stable Back/Next/Review actions, autosave/resume, responsive forms, bilingual readability, clear errors follow Foundation UI.
11. Do not duplicate initial check-in/out/timezone in later Operations screen.
12. Full HMS unlock occurs after BinGi property approval; published website/marketplace requires separate checks.

## F. Proposed UX screen components (reused across all four journeys)

```text
Property Setup Shell
  -> Enabled Accommodation Type Cards
  -> Location Hierarchy Editor / Numbering Preview
  -> Category Picker / Conditional Category Editor
  -> Unit Selector / Bulk ID Preview
  -> Pricing & Media panel
  -> Review & Validation
  -> Property Readiness / Approval Status
```

**Status to reviewer:** Please review this Room journey before marking approved. Changes will be reflected consistently in the other type diagrams where shared logic applies.

**References:** [Shared onboarding rules](README.md) · [Room Spec](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/02-ROOM-SETUP.md) · [UI Foundation](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX).

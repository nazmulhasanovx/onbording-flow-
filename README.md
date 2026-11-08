# BinGi HMS — Property-Wise Onboarding V3 (Review Draft)

**Date:** 2026-11-08  
**Status:** DRAFT FOR PRODUCT REVIEW — not approved, not implemented.  
**Purpose:** Keep the four priority accommodation journeys in four independent, reviewable text-diagram documents. **No live HMS code, settings, or hotel data are changed by these files.**

## Start reviewing (one journey at a time)

1. [01-ROOM-ONBOARDING.md](01-ROOM-ONBOARDING.md) — Building/Floor → Room Category → real Room IDs.
2. [02-COTTAGE-ONBOARDING.md](02-COTTAGE-ONBOARDING.md) — Zone/Area → optional Block → Cottage IDs.
3. [03-VILLA-ONBOARDING.md](03-VILLA-ONBOARDING.md) — Zone/Area → whole Villa with bedrooms and optional pool.
4. [04-APARTMENT-ONBOARDING.md](04-APARTMENT-ONBOARDING.md) — Tower/Building → Floor → entire Apartment.

**Review order:** Room → Cottage → Villa → Apartment. Keep each as DRAFT until individually reviewed and explicitly approved.

## Latest pricing and service policy — separate review draft

- [05-PRICING-PLAN-AND-TRAINING-V2-DRAFT.md](05-PRICING-PLAN-AND-TRAINING-V2-DRAFT.md) — revised monthly per-room subscription (custom quantity from 10), 6-/12-month discounts, Business/Ultra activation waiver, remote per-shift training promotion, onsite training and open commercial decisions. **This latest working pricing supersedes older tier pricing for new onboarding planning only; not approved for production or retroactive invoices.**

## Essential distinction

- **Property Type:** Hotel, Resort, Guest House, Serviced Apartment, etc.
- **Accommodation Type:** Room, Cottage, Villa, Apartment, Dormitory, Other/Custom.
- **Do not create four different property databases or force one accommodation type per property.** One Resort/Hotel may enable several accommodation types; all belong to that exact authorized property and share a common onboarding engine.
- **Priority now:** Room, Cottage, Villa, Apartment. **Dormitory:** retained in accommodation blueprint but is outside these four review files. **Other/Custom:** intentionally deferred.

## Common product journey (for each separate property)

```text
ACCOUNT REGISTRATION (once per user)
  -> Verify account
  -> Create a NEW PROPERTY DRAFT (unique property_id)
  -> Property Profile & Contact (enter once)
  -> Choose Subscription Plan + physical unit capacity + setup assistance
  -> Operating Defaults (currency, time zone, check-in/out, policies, tax defaults)
  -> FIRST-TIME ACCOMMODATION CONFIGURATION (enabled types, location tree, numbering)
  -> Category template(s) and actual physical Unit(s)
  -> Rate / availability / restrictions
  -> Existing reservation & maintenance block reconciliation
  -> Relevant plan-enabled operations, staff, payments
  -> Website/channel PREVIEW AS DRAFT (not public)
  -> Required identity/business documents (conditional)
  -> Check readiness, plan limit, and conflicts
  -> Submit THIS PROPERTY to BinGi for review
  -> WAITING / NEEDS CHANGES / APPROVED
  -> On approval: unlock this property's HMS dashboard & entitled modules
  -> Independently publish website / marketplace only when channel-ready
```

**Owner target:** Complete ~80–90% of relevant property configuration before submit. That is a setup coverage goal, **not permission to skip mandatory validation**. The owner remains on a property-specific approval/status workspace until BinGi team approval (per current product direction).

## Shared architecture and UX constraints

1. Property-scoped data and access: verify `property_id` and user role on the server for every location/category/unit/reservation/asset; never display another property's configuration. Switching between authorized properties switches context and independent onboarding progress.
2. Plan-based entitlements and limits are server-enforced and driven by the authoritative subscription matrix; do not infer that a selected plan supports a module. Compare declared physical inventory vs configured Unit count vs purchased capacity explicitly. Avoid counting Villa/Apartment bedrooms as separate physical units.
3. **Configure once → reuse always.** Reuse Property Profile, saved location nodes, type/category location strategy, numbering policy, rate/amenity defaults. Single valid option should be auto-selected. Do not ask the owner to recreate floors/zones on subsequent unit additions.
4. Common reusable 5-stage accommodation wizard: **Type → Category → Location & Units → Details & Pricing → Review/Create**. For returning operators with existing category defaults, allow the shortest path. Keep CTA positions/stepper consistent.
5. Numbering: recommend 101/201 for floors and C01/V01/TA-101 etc. Owner can select nonconsecutive IDs; property-wide uniqueness and safe concurrent creation must be enforced. No 99-floor assumption; immutable internal record IDs.
6. Inventory: Room/Cottage/Villa/Apartment each sell as a **whole physical Unit** in V1. Bedrooms inside Cottage/Villa/Apartment are descriptive—not extra independently bookable inventory.
7. Publish status, operational status, and dated reservation availability are different. Draft/created does not imply publicly sellable; reconcile existing bookings/blocks before accepting public bookings.
8. Optional YouTube video tour belongs on the category's Media section, inherited by units unless a genuine unit-level replace/hide override is set. Do not demand video link for each unit; photos-only flow must work.
9. No forced floor selection for Cottage/Villa. No repeated fields such as currency/time zone/check-in/out in multiple onboarding stages.
10. Verification/approval: owner supplies required information, reviews a precise setup summary, submits, then sees BinGi decision or exact corrections. Full dashboard remains locked until property approval; online listing/channel go-live is a separate gate.
11. Loading/empty/error/draft/retry states, keyboard access, Bangla/English text, responsive layout, autosave/resume and fixed navigation button slots must follow Foundation UI.
12. Be backward compatible: don't blindly rename production Room IDs, tables, reservations or API contracts; migration/implementation requires actual backend review and rollback plan.

## Sources and boundaries

- [BinGi UI Foundation](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX): UI-00 through UI-06 and UX navigation/settings.
- [BinGi Accommodation Master Plan](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/MASTER-PLAN.md), [Property Configuration](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/01-PROPERTY-CONFIGURATION.md), [QA](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/08-VALIDATION-AND-QA.md), [Ecosystem Change Impact](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/09-ACCOMMODATION-ECOSYSTEM-CHANGE-IMPACT.md).
- Actual production UI observed in supplied Nov 8 onboarding screenshots. **This is not a source-code or backend audit.**
- This repository records **proposed onboarding user journeys**, not proof of a live feature, payment integration, KYC/legal entitlement, or OTA integration.

## Product decisions still open

- Confirm the exact plan-to-feature entitlement matrix and approval requirements.
- Confirm physical unit subscription accounting for mixes and future dormitory beds.
- Confirm trial/paid billing start trigger, payment collection and commercial policies.
- Confirm mandatory property verification documents and who can submit on behalf of owner.
- Confirm migration from existing Room-only HMS entities and actual backend/API contracts.

**Do not change or publish live hotel data based on these planning diagrams.**

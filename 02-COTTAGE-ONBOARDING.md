# 02 — COTTAGE Onboarding Journey
**Status: DRAFT FOR INDIVIDUAL REVIEW — not approved or implemented.**
**Property Type ≠ Accommodation Type.** Resort/Hotel/Guest House may enable Cottage plus Room/Villa/Apartment; never force one type per property.
## Full Text Diagram
```text
ACCOUNT REGISTRATION (ONCE)
 -> Create THIS PROPERTY's draft workspace (unique property_id)
 -> Property name/type, official contacts, address (saved once)
 -> Select subscription plan, physical Unit capacity, setup support
 -> Save shared currency/timezone/check-in/out/taxes/booking policies ONCE
 -> ENABLE ACCOMMODATION TYPES: Cottage (plus any applicable others)
 -> COTTAGE ONE-TIME LOCATION CONFIGURATION
    -> Recommended location: Zone / Area -> optional Block
    -> Reuse existing zones: Garden Zone / Lake Zone / Hill Zone
    -> If no zones exist, configure zones ONCE
    -> Block configured? YES -> show existing blocks; NO -> hide Block selector
    -> One valid zone? Auto-select during subsequent unit creation
    -> Do NOT require Hotel Floor; internal Cottage levels are descriptive
    -> Save code format: C01, C02... or zone/block-qualified G-C01 / A-C01
    -> Manual gaps allowed: C01, C03, C05; reject property-wide duplicate codes
    -> Save versioned type/category location and numbering strategy
 -> UNIVERSAL 5-STEP ACCOMMODATION WIZARD
    1 TYPE: Cottage
    2 CATEGORY: Pick existing Garden/Family Cottage OR create new
       -> Category Name / Style / Adults & Children
       -> Bedrooms & bed arrangements / Bathrooms / optional internal levels
       -> Size, description, photos, amenities, meals (if plan permits)
       -> Optional YouTube Video Tour, default Cottage/night rate
       -> Save reusable category defaults
    3 LOCATION + UNITS: choose saved Zone, Block only if configured
       -> Generate N / Select / Range / Manual unique IDs
       -> Example select C01,C03,C05 -> EXACTLY 3 physical Cottages
       -> Verify saved location, quota and concurrency-safe uniqueness
    4 DETAILS + PRICING: inherit category defaults; optional per-unit differences
       -> Unit-specific view/notes, operational status, video replace/hide override
    5 REVIEW: exact IDs, category, location, rates -> Save Draft / Create
 -> Existing Cottage bookings / maintenance blocks / availability reconciliation
 -> Guest payments, plan-enabled staff & operations, website as DRAFT
 -> Required owner/business verification and property readiness validation
 -> SUBMIT PROPERTY FOR BINGI TEAM APPROVAL
    -> Needs Changes: fix named section & resubmit
    -> Approved: unlock THIS property's plan-entitled HMS dashboard
    -> Public channels require separate readiness/publishing checks
```
## Returning-operator fast path
```text
Select Cottage -> Existing Garden Cottage -> Saved Zone (if ambiguous)
 -> Optional saved Block -> Select C06,C07,C09 -> Review -> Create.
NO repeat of property profile, location-tree creation, bedrooms, amenities or default price.
```
## Rules and acceptance
- Cottage is ONE whole-unit inventory item even with multiple bedrooms. No per-bedroom selling in V1.
- Cottage Floor is not required. Blocks absent -> hide field. Internal levels never create hotel Floor nodes automatically.
- All reads/writes validate authorized property_id and role server-side. Never show another property's zones, units or categories.
- C01 and C03 without C02 valid. Same displayed ID in different zones requires qualification or rejection; no silent overwrite.
- Created/Draft/Published/Operationally Active/Available for given dates must remain distinct.
- Category media and rate inherited; per-unit overrides preserved; YouTube optional; missing video never blocks publication.
- Booking conflicts guard edits, relocation or removal of active Units. Immutable database IDs and audit required.
- Subscription counts physical Cottage units, not bedrooms; actual plan entitlements and tier limit are server-enforced.
- Use consistent five-stage header, back/next positions, autosave/resume, accessible localized fields and clear errors.
## References
[Shared rules](README.md) · [Cottage specification](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/03-COTTAGE-SETUP.md) · [Foundation UI](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX).

# 03 — VILLA Onboarding Journey
**Status: DRAFT FOR INDIVIDUAL REVIEW — not approved or implemented.**
**Villa is an accommodation type**, not necessarily a Property Type. The same Resort can enable Room, Cottage, Villa, Apartment.
## Full Text Diagram
```text
ACCOUNT REGISTRATION (ONCE)
 -> Create isolated Property Draft / property_id
 -> Save Property Profile & owner contact once
 -> Subscription plan, physical Unit capacity, setup support
 -> Save property currency/timezone/check-in/out/tax/policies once
 -> ENABLE Villa (and only other actual accommodation types)
 -> VILLA ONE-TIME LOCATION CONFIGURATION
    -> Recommended strategy: Zone/Area -> optional Block
    -> Existing Beachfront / Garden / Lake Zones? REUSE
    -> Otherwise create required Zones once
    -> Optional Blocks / standalone Villa wing if valid strategy configured
    -> Do not require a Hotel Floor for Villa
    -> Saved numbering V01,V02... or BF-V01 / G-V01 / A-V01
    -> Allow nonconsecutive V01,V03,V05; enforce property-wide uniqueness
    -> Save versioned location strategy + numbering policy
 -> UNIVERSAL 5-STEP ACCOMMODATION WIZARD
    1 TYPE: Villa
    2 CATEGORY: Existing Private Pool/Garden Villa OR Create Category
       -> Villa name, style, maximum adults/children
       -> Bedroom count and separate bed arrangement for each bedroom
       -> Example 2 bedrooms: King x1; Single x2
       -> Bathrooms; optional internal levels (NOT separate sellable units)
       -> Optional private pool, kitchen, living, size, accessibility
       -> Category photos, amenities, meals (when entitled), default Villa/night rate
       -> Optional YouTube Video Tour; Save category reusable defaults
    3 LOCATION + UNITS: select saved Zone; optional Block
       -> Preview/Generate/Manual IDs; choose V01,V03,V05
       -> Validate no duplicates, correct location, plan quota
    4 DETAILS + PRICING: inherit category, optional unit pool/view exceptions
       -> Unit operational status; optional video override/hide
    5 REVIEW: 3 Villas V01,V03,V05 = EXACTLY 3 physical/bookable whole units
       -> Save Draft or Create; online publication is separately gated
 -> Set rates/date restrictions & import/confirm existing bookings/maintenance
 -> Property plan-enabled operations, staff, guest payment methods
 -> Website and marketplace remain DRAFT until channel-specific readiness
 -> Verification required for the applicable property/services
 -> Final readiness check -> SUBMIT PROPERTY FOR BINGI APPROVAL
    -> Needs Changes -> targeted correction -> resubmit
    -> Approved -> unlock this property's HMS Dashboard / entitled modules
```
## Returning-operator fast path
```text
Villa -> Existing Pool Villa -> Saved Beachfront Zone -> Block if configured
 -> Select V06,V07,V09 -> Review -> Create. Do not ask for bedrooms/rates again.
```
## Rules and acceptance
- One Villa = ONE physical Unit = ONE whole-unit sellable item; bedrooms/internal floors are descriptive, not individually bookable in V1.
- Saved Zone/Block reused. If only one valid location, auto-select. No compulsory Floor.
- Private pool at category level may have a unit-level exception or maintenance status.
- V01/V03 gaps allowed, duplicates blocked, property-scoped numbering. DB identity immutable.
- Booking and dated maintenance conflicts must protect changes to unit number, category or location.
- Only authorized property zones/categories/units shown, and backend property_id/RBAC checks enforced.
- Published status, operational status and dated availability are independent.
- Category YouTube Video Tour optional and inherited; exact-unit representation must be truthful; unit override can replace/hide.
- Physical Unit count, not bedroom count, consumes plan capacity. Server enforces plan entitlements.
- Standard five-stage UX, consistent action placement, autosave, readable Bangla/English, errors and draft resume.
## References
[Shared rules](README.md) · [Villa specification](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/04-VILLA-SETUP.md) · [Foundation UI](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX).

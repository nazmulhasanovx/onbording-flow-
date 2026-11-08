# 04 — APARTMENT Onboarding Journey
**Status: DRAFT FOR INDIVIDUAL REVIEW — not approved or implemented.**
**Serviced Apartment** can be a Property Type; **Apartment** is an Accommodation Type inside any compatible Hotel/Resort/Serviced Apartment property.
## Full Text Diagram
```text
ACCOUNT REGISTRATION (ONCE)
 -> Create Property Draft with unique property_id and independent status
 -> Property Profile/contact/address saved once
 -> Plan, physical Unit capacity, setup assistance
 -> Shared operating defaults (time zone, currency, policies, check-in/out) once
 -> ENABLE APARTMENT (plus other types actually present)
 -> APARTMENT ONE-TIME LOCATION CONFIGURATION
    -> Recommended Building / Tower -> Floor
    -> Existing Tower A, Tower B? Reuse configured nodes
    -> If none, set Towers/Buildings and child Floors ONCE
    -> Tower A / Floor 1 vs Tower B / Floor 1 are distinct locations
    -> Numbering 101/201 or A101/A201 or tower-qualified TA-101/TB-101
    -> If 101 would collide, require a unique full display code/prefix
    -> Support nonconsecutive numbers & 100+ floors with safe formatting
    -> Save category/location strategy and versioned numbering policy
 -> UNIVERSAL 5-STEP ACCOMMODATION WIZARD
    1 TYPE: Apartment
    2 CATEGORY: select Studio/1BR/2BR/Family OR Create Category
       -> Category name, style Studio/1BR/2BR/3+BR, max occupancy
       -> Bedrooms, bedroom-by-bedroom beds, bathrooms
       -> Studio can have zero separate bedrooms but must have valid beds
       -> Conditional kitchen/living/dining/balcony, size & amenities
       -> Photos, description, optional YouTube Video Tour, default whole-unit rate
       -> Saved Tower/Building->Floor location strategy; Save category
    3 LOCATION + UNITS: Tower A / Floor 1
       -> Preview TA-101, TA-102, TA-103...
       -> Select TA-101,TA-103,TA-105 (nonconsecutive allowed)
       -> Validate duplicate codes, valid floor parent and plan limit
    4 DETAILS + PRICING: inherit category; optional view/notes/unit overrides
       -> Operational state and optional media override/hide
    5 REVIEW: [TA-101,TA-103,TA-105] = EXACTLY 3 whole Apartments
       -> Save Draft / Create; publish only when readiness passes
 -> Rates & date-restriction configuration and existing booking conflict check
 -> Guest payments, plan-enabled staff/modules and draft website preparation
 -> Conditional owner/business verification, final readiness checklist
 -> SUBMIT PROPERTY -> BINGI APPROVAL WORKSPACE
    -> Needs Changes -> targeted edit/resubmit
    -> Approved -> property HMS Dashboard unlocked with plan-based access
    -> Public channels require separate validation & publish
```
## Returning-operator fast path
```text
Apartment -> Existing 2BR Category -> Tower A/Floor 2 -> TA-201, TA-203
 -> Review/Create. No repeated Tower/Floor definition or bedroom/price setup.
```
## Rules and acceptance
- Apartment rooms/bedrooms/kitchen/living/balcony are subspaces/features: one Apartment is ONE bookable physical Unit in V1.
- Studio has zero separate bedrooms but may have beds in shared sleeping space.
- Multiple towers with same floor must use distinct visible unit codes (TA-101/TB-101) or disallow duplicates.
- Existing location configuration and category strategy reused. No other property's location/category surfaced; backend property_id and permissions checked.
- Owner can select A101/A103 without A102 if numbering rule allows. Enforce exact preview and transaction-safe uniqueness.
- Room or Apartment units count toward subscription limits per applicable physical-unit accounting; bedrooms do not.
- Existing bookings/maintenance protect edits, room assignments and availability; stable immutable IDs and audit.
- Price per entire Apartment per night. Publish/Operational status/dated availability are separate.
- Optional category tour inherited; unit override replace/hide; don't promise exact view for unassigned category bookings.
- Stable wizard structure/CTA slots, draft autosave/resume, validation and accessible responsive Bangla/English UX.
## References
[Shared rules](README.md) · [Apartment specification](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/05-APARTMENT-SETUP.md) · [Foundation UI](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX).

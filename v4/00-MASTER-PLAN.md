# 00 — V4 Master Product Plan
Status: REVIEW DRAFT. Scope: BinGi HMS onboarding and handoff, not production implementation.

## Product objective
Owner configures ~90% of the applicable property before submission; all required safety-critical checks must pass (100%). BinGi approves the specific property, then plan-authorized HMS becomes available. Actual public booking and OTA publishing are **separate** gates.

## Definitions
- **Account**: Login user; can access one or more authorized properties.
- **Property Type**: Hotel, Resort, Guest House, Serviced Apartment, etc.
- **Accommodation Type**: Room, Cottage, Villa, Apartment. Dormitory is future subsequent priority, Other/Custom deferred.
- **Category**: Reusable sellable class, such as Deluxe Twin, Garden Cottage, Private Pool Villa, 2BR Apartment.
- **Physical Unit**: A specific bookable accommodation: 101, C03, V01, TA-101. In V1 one Room/Cottage/Villa/Apartment sells as a whole unit; internal bedrooms are not independent inventory.
- **Commercial Quantity**: Minimum 10 (user decided). Whether mixed accommodation units all count equally is strongly recommended but pending explicit approval.

## Core diagram
~~~text
ONE ACCOUNT / AUTHORIZED PROPERTIES
  -> CREATE NEW PROPERTY DRAFT
  -> 01 PROPERTY & PRELIMINARY PLAN
  -> 02 SMART ACCOMMODATIONS
     [Room | Cottage | Villa | Apartment; one-time presets; category + bulk units]
  -> 03 BOOKINGS & RATES
  -> 04 PLAN-AWARE OPERATIONS
  -> 05 DIGITAL PRESENCE & PAYMENTS
  -> 06 COMMERCIAL / VERIFICATION / REVIEW
  -> SUBMIT PROPERTY -> BinGi REVIEW
       Needs changes -> targeted edit -> resubmit
       Hold/reject -> clear reason and next steps
       Approved + required commercial condition -> Full HMS access
  -> separately verify WEBSITE/MARKETPLACE/OTA readiness
~~~

## Principles (must survive UI changes)
1. **Easy first**: one task per viewport, progressive disclosure, safe recommended defaults; avoid endless forms and re-asking data.
2. **Configure once**: property profile, operating defaults, location trees, numbering and category defaults reused.
3. **One engine**: common accommodation wizard with conditional type-specific fields and location strategy.
4. **Property isolation**: all APIs, read/write, assets, user permissions and cache are property-scoped server-side. Never show one property's data in another.
5. **Plan enforcement**: real entitlements from server configuration, not sidebar hiding; no unrelated HRM/Restaurant setup forced on Starter.
6. **Commercial clarity**: subscription, activation, training, promotions, commissions, domain/provider extras and taxes separately itemized; preserve accepted quote versions.
7. **Review before billing surprises**: customer explicitly accepts prices/terms; changes never retroactively rewrite invoices.
8. **No false readiness**: draft content != published listing; active physical unit != unoccupied date; property approved != publicly bookable.
9. **Existing HMS safety**: immutable internal IDs, booking conflict checks, no blind Room API/table renaming or destructive plan downgrade.
10. **Future design**: source of truth here is draft; Figma Make builds editable UI and click paths; backend logic is specified but not magically implemented.

## Six visible sections
| Section | Owner outcome | Main optionality |
|---|---|---|
| 01 Your Property | Profile, contacts, type, preliminary plan | map optional |
| 02 Accommodations | saved locations/categories/actual units | only enabled types |
| 03 Booking Ready | rates, policies, current stays/blocks | no bookings explicit |
| 04 Operations | relevant plan modules, team and financial defaults | hide unused modules |
| 05 Digital & Payments | guest payment, draft website, gallery, theme | publishing later |
| 06 Review & Confirm | final commercial quote, verification, readiness, submit | exact required docs |

## Success criteria
- First-time owner can configure 10 rooms using bulk add without entering the same category or property-wide settings 10 times.
- Mixed property can manage Room/Cottage/Villa/Apartment without four isolated property onboarding accounts.
- User cannot see/access unauthorized property records, even by guessed ID.
- Only relevant critical setup blocks submission; optional polish remains a post-approval checklist.
- Final purchase screen accurately matches selected plan, actual capacity, promotional zero-charge modules and approved services.
- Owner has preview/status and targeted correction pathway until approval, not a dead-end locked page.

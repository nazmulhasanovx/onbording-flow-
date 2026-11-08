# 05 — BinGi Plan-Based Per-Unit Pricing, Promotions & Training (Draft V2)

**Date:** 2026-11-08
**Status:** USER-PROVIDED LATEST WORKING PRICING, DRAFT FOR REVIEW. Not deployed and not a legal offer.  
**Supersedes for new onboarding design:** earlier fixed room-package tier amounts (Starter 10/20/30, etc.). Preserve any accepted customer quotes and existing invoices independently.

## A. New subscription model

**Minimum billable quantity: 10 rooms (for each plan).** Unlike a tier picker, owner should be able to enter a custom count (10, 11, 12, 19, 37, ...). No arbitrary maximum has been provided; do not invent one.

| Plan | Monthly base per room | Minimum quantity | Minimum monthly base |
| --- | ---: | ---: | ---: |
| Starter | ৳30 | 10 | ৳300 |
| Business | ৳50 | 10 | ৳500 |
| Ultra | ৳116 | 10 | ৳1,160 |

**Billing cycle**: monthly 0% discount; 6 months 10% subscription-only discount; 12 months 25% subscription-only discount. These discounts **do not** apply to one-time activation, training, on-site visits, approved expenses, guest booking commission, or taxes unless an independent explicit rule says otherwise.

### Subscription calculation

```text
Customer selects Plan = Starter / Business / Ultra
 -> enters Custom Room Quantity Q (whole number; Q >= 10)
 -> show subscription base = Q * plan.monthly_rate
 -> choose Cycle = 1 / 6 / 12 months
 -> cycle subtotal = Q * rate * number_of_months
 -> subscription discount =
       1 month: 0%
       6 months: 10%
      12 months: 25%
 -> discounted subscription = cycle subtotal - cycle discount
 -> add applicable taxes separately according to approved tax rules
```

**Billing accuracy:** Store currency BDT, precise money values, snapshot of plan rate, quantity, duration, discounts and applied promotions on accepted order/invoice. Round only according to an explicit money policy (not ad hoc per-line rounding). Future pricing updates never retroactively alter accepted orders.

### Example, 10 rooms

| Plan | 1 month | 6 months after 10% | 12 months after 25% |
| --- | ---: | ---: | ---: |
| Starter | ৳300 | ৳1,620 | ৳2,700 |
| Business | ৳500 | ৳2,700 | ৳4,500 |
| Ultra | ৳1,160 | ৳6,264 | ৳10,440 |

Example custom quantity 15 rooms: Starter = ৳450/month; Business = ৳750/month; Ultra = ৳1,740/month, before any taxes.

## B. Existing commissions and plan features (from previous user policy; verify alongside new rates)

- Starter: core room/accommodation management, online and offline bookings, website management, limited themes, domain management; marketplace 12%, website bookings 1.5%, walk-in 0%.
- Business: Starter core plus housekeeping, meals/restaurant, expense, Other Services, QR food orders, menu limit 20 (previous commercial matrix); marketplace 8%, website 1%, walk-in 0%. **User's latest note:** 'restaurant currently free' — do not add an unspecified restaurant fee while promotion applies.
- Ultra: Business-based broader advanced operations, HRM, Inventory, 500 menu capacity and unlimited website themes from previous matrix; marketplace 4%, website 0.5%, walk-in 0%. **User's latest note:** 'restaurant management limited' — definition/cap and its relation to the Business free restaurant promotion must be explicitly reviewed; do NOT invent or assume unlimited entitlement.
- Plan-to-feature permissions are enforced on the SERVER by active entitlement/feature flags. Do not merely hide modules in the sidebar.
- **Capacity for all four priority accommodation types still needs commercial confirmation.** Recommended consistent interpretation: one actual physical Room / Cottage / Villa / whole Apartment = one billable Unit. Bedrooms within Villa/Cottage/Apartment are never counted separately. If commercial labeling remains 'room', display explanatory text '1 physical accommodation unit = 1 room for plan capacity.' This interpretation is proposed, **not yet locked by the user**.
- Dormitory bed billing policy remains open; Other / Custom deferred.

## C. Activation fee — Business and Ultra only

| Plan | Standard activation charge | CURRENT promotional charge |
| --- | ---: | ---: |
| Starter | Not applicable | ৳0 |
| Business | ৳29,500 | ৳0 (currently waived) |
| Ultra | ৳29,500 | ৳0 (currently waived) |

The waived ৳29,500 may be displayed as 'Standard ৳29,500; promotional fee ৳0'. **No promotion end date, duration, or renewal rule has been specified** — do not invent one. Persist the applicable promotional discount on each accepted order. One-time activation must never recur automatically with subscription renewal.

## D. Training and onsite service

| Service | Standard charge | CURRENT offer | Important |
| --- | ---: | ---: | --- |
| Remote Team Training | ৳500 / shift | ৳0 per eligible shift currently | Shift count/scope and free-offer limits to define |
| Onsite Training | ৳12,500 | ৳12,500 (no current waiver specified) | Property must provide meals and accommodation/stay for visiting team |

- Remote training can support **configurable discounts** in addition to the current free promotion. Prevent stacked offers from making fees negative or applying more discounts than authorized.
- Avoid interpreting 'currently free' as unlimited free training forever: no eligibility, number of shifts or expiry provided yet.
- Onsite duration, included number of trainers, travel/transport, taxes and minimum notice/cancellation rules require written commercial policies; do not assume old plan-wise one-time remote/onsite fees remain current once this new model is adopted.
- Meals and stay are provided by the PROPERTY, not charged by BinGi as included service. Display clearly before confirmation.
- Do not charge a separately selected remote training package again when the same service is already included with a contracted onsite package unless independently agreed.

## E. Owner-side onboarding pricing and payment journey

```text
PROPERTY PROFILE CREATED
  -> CHOOSE PLAN [Starter/Business/Ultra]
       -> display plan module matrix and access restrictions
       -> select custom number of physical rooms/units: min 10
       -> review exact unit-count preview and occupancy inventory
       -> choose 1 / 6 / 12 month subscription cycle
       -> show dynamic base + exact cycle discount
  -> ACTIVATION
       -> Starter: no activation fee
       -> Business/Ultra: standard 29,500, currently 100% waived
  -> ASSISTANCE
       -> Self-setup (if enabled)
       -> Remote training: 500 per selected shift; currently free
       -> Onsite training: 12,500; property supplies meals + stay
       -> editable shift quantity; schedule/trainer details when applicable
  -> COMMERCIAL SUMMARY
       -> Subscription before discount
       -> Subscription cycle discount
       -> Standard activation fee / current waiver
       -> Standard training fee / applicable promo/discount
       -> Onsite charge and disclosed obligations
       -> Other approved charges and taxes
       -> GRAND TOTAL; no hidden charge
  -> OWNER CONFIRMS PRICE AND TERMS
  -> create Subscription Order and separate Setup/Training Service Order
  -> payment according to approved collection policy
  -> continue property-specific accommodation/operations setup
  -> owner submits for BinGi approval
  -> BinGi team reviews required verification and technical readiness
  -> unlock HMS only after approval + applicable commercial conditions
  -> website/marketplace publish only after separate channel readiness
```

**Do not require completion of onsite training to submit a perfectly valid self-configured property** unless there is a specifically agreed contract/approval policy. Keep order/payment/property-approval/training-schedule statuses independent.

## F. Super Admin controls (configuration, not hardcoded)

- Monthly per-room price per plan, minimum quantity, billing cycle discount rules and future effective dates.
- Enable/disable custom quantity entry, validate authorized quantities and additional unit upgrades.
- Activation standard fee per plan and active promotion eligibility/percentage/amount, effective range and expiration.
- Remote training price per shift, training-promotion eligibility/quantity limits, optional discounts, trainer assignment and service status.
- Onsite price, property-provided meals/stay requirement and any separately approved expense policies.
- Features/menu/theme/restaurant/HRM entitlements, custom exceptions by property and subscription version.
- Audit who changed price/discount/feature, when, old/new values; never rewrite accepted invoices or offers.

## G. Test / QA cases

1. Starter 10 rooms -> ৳300/month, 6m ৳1,620, 12m ৳2,700 before tax.
2. Business 10 -> ৳500/month, 6m ৳2,700, 12m ৳4,500 before tax.
3. Ultra 10 -> ৳1,160/month, 6m ৳6,264, 12m ৳10,440 before tax.
4. Custom Q=13 accepted; Q=9 rejected or corrected to minimum 10 with explicit explanation.
5. 15 units mixed Room/Cottage/Villa/Apartment -> capacity handling **requires approval of common physical-Unit accounting**.
6. Business/Ultra standard activation ৳29,500 is waived to ৳0 currently; no accidental recurring activation on renewal.
7. Starter never receives an activation fee.
8. Remote training, 2 shifts: standard 2*৳500, currently waiver to ৳0 for eligible shifts; proper promo snapshot.
9. Onsite training ৳12,500 with explicit 'Meals and accommodation provided by property' notice.
10. Discounts on subscription never discount activation/onsite fees without explicit rules.
11. Paid vs property approved vs training completed vs website published are distinct statuses.
12. Dynamic plan changes correctly update entitlements but never delete physical unit data or active reservations.

## H. Pending approval / ambiguities

1. Does the per-room bill apply to EACH physical unit of the four types equally (Room/Cottage/Villa/Apartment)? Recommended yes for consistency; **not confirmed**.
2. Confirm the exact 'Ultra restaurant management limited' limit and how it compares to Business restaurant currently free.
3. Define remote-training free shift count, promo eligibility and expiry (none specified).
4. Confirm activation waiver eligibility and expiry (none specified).
5. Onsite: per-property/per-visit basis, number of training days, travel expense treatment and actual trainer count not specified.
6. Clarify timing of subscription charge, first payment and trial (if any), plus refund/cancellation.
7. Confirm plan module scope, especially Staff Basic Access vs Full HRM and Finance/Cashbox.
8. Update any existing pricing pages, quotes and onboarding UI only AFTER this draft is reviewed and approved.

**Sources of truth:** User's new 2026-11-08 per-room pricing proposal, earlier plan feature/commission matrix, current [BinGi onboarding review index](README.md), [Accommodation architecture](https://github.com/nazmulhasanovx/Room-Accomodation-), [UI Foundation](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX). No claim of live system implementation.

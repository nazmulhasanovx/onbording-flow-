# 05 — BinGi Plan-Based Per-Unit Pricing, Promotions & Training (Draft V2)

**Date:** 2026-11-08
**Status:** USER-PROVIDED LATEST WORKING PRICING + PROMOTIONAL MODULE RULES, DRAFT FOR REVIEW. Not deployed and not a legal offer.  
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
- Business: Starter core plus housekeeping, meals/restaurant, expense, Other Services, QR food orders, menu limit 20 (previous commercial matrix); marketplace 8%, website 1%, walk-in 0%. Restaurant & Bar Management **currently has no additional module fee for eligible/entitled properties**; precise Bar entitlement/scope still requires confirmation.
- Ultra: Business-based broader advanced operations, HRM, Inventory, 500 menu capacity and unlimited website themes from previous matrix; marketplace 4%, website 0.5%, walk-in 0%. Restaurant & Bar Management **currently has no additional module fee within verified plan entitlements**, but the user's 'Ultra restaurant management limited' statement is not yet defined; do NOT claim unlimited features.
- Plan-to-feature permissions are enforced on the SERVER by active entitlement/feature flags. Do not merely hide modules in the sidebar.
- **Capacity for all four priority accommodation types still needs commercial confirmation.** Recommended consistent interpretation: one actual physical Room / Cottage / Villa / whole Apartment = one billable Unit. Bedrooms within Villa/Cottage/Apartment are never counted separately. If commercial labeling remains 'room', display explanatory text '1 physical accommodation unit = 1 room for plan capacity.' This interpretation is proposed, **not yet locked by the user**.
- Dormitory bed billing policy remains open; Other / Custom deferred.

## B1. Website Management + Restaurant & Bar Management — Currently Free, no future billing surprises

**Latest user instruction (2026-11-08):** `Website Management — currently free`; `Restaurant & Bar Management — currently free`. Treat these as **no separate incremental module/service charge at present**, NOT a promise that a customer automatically receives every module on every plan or that third-party costs are waived. This section must be included in the customer-facing offer, onboarding order summary, Billing screen and saved agreement, after final policy approval.

| Service / module | Present additional module fee | Eligibility / limitation |
| --- | --- | --- |
| Website Management | **৳0 — currently free** | Website management is previously listed in Starter/Business/Ultra; plan-specific themes/domain capabilities still apply. |
| Restaurant Management | **৳0 — currently free** | Only where the customer's active plan or specific contract enables Restaurant. Exact Business/Ultra limits require a final feature matrix. |
| Bar Management | **৳0 — currently free** | Bar access and scope per plan **not yet specified**; do not automatically enable it for Starter/Business/Ultra without a plan entitlement decision. |

**These are module-fee statements only.** They do **not** waive the paid room/unit subscription, marketplace/website booking commissions, online payment gateway/provider charges, purchased domain/renewal fees, premium development or custom integration, onboarding/onsite training, approved travel, or other third-party costs. Any extra fee must be separately itemized, not implied by 'Free Website Management' or 'Free Restaurant & Bar'. Distinguish **website management software access** from **website setup, custom web development, hosting and domain costs**; the inclusions/exclusions require an explicit written scope.

### Dispute-prevention commercial rules (proposed contractual policy)

1. **Show exactly what's free:** On Plan Comparison + Final Checkout display `Included in your plan / currently no extra module fee`, with exact enabled features and limitations. Don't show a 'free' restaurant/bar module that the selected plan doesn't permit.
2. **Do not use vague 'free forever':** `Currently free` is a current promotional pricing status. **No offer expiry is confirmed**. Do not invent an expiration date, strike-through 'standard price' or fee amount for these two modules.
3. **Accepted-term protection:** Any property that confirms a monthly, 6-month or 12-month order retains the **documented module access, included services and accepted charges for the entire paid/committed term**, subject to explicit published service terms and applicable law. No retroactive charge or removal of paid-for access midterm merely due to a future promotion change.
4. **Future fee changes:** Before changing a currently free module to a paid extra, provide advance written notice (in-app + email where deliverable), clear future price, effective date, impacted plan/properties, alternatives and an **explicit opt-in/contract renewal agreement**. **Never start automatic extra-module billing without affirmative customer acceptance.** A 30-day minimum notice could be a useful policy, but is **not yet approved**.
5. **Declining a future paid add-on:** Customer may decline the newly priced optional add-on without a hidden charge. If a module was expressly included as a paid plan feature, do not silently remove it; honor the accepted commitment or negotiate a separately agreed plan change with fair transition/data portability options.
6. **Audit and quote snapshot:** Store `offer_version`, `plan_version`, `property_id`, `included_modules`, `module_fee=0`, `promo_status`, `effective_from/to` if actually defined, and `customer_acceptance_timestamp` on the accepted order. Preserve original approved invoices, promotions and communications.
7. **Zero-charge display:** Show a line such as `Website Management — Included (currently ৳0 extra)` and `Restaurant & Bar Management — ৳0 extra (when included in your plan)`. Do not place an undisclosed module charge in renewal invoices.
8. **Approval / payment / publishing gates remain separate:** Free module fees do not bypass owner verification, subscription payment, plan entitlement, domain rights, channel go-live readiness or BinGi Team property approval.
9. **Staff / scope safeguards:** Restaurant & Bar can have separate menu, orders, POS, inventory, taxes or licensing functionality; never imply those all exist or are free unless scope is formally defined. Bar operations must follow applicable local legal requirements and age restrictions where relevant. No unsupported functionality is promised.

### Owner-facing recommended offer text (draft; not final legal terms)

> **Website Management:** Included in eligible BinGi plans with **no additional module management charge at present**. Available themes, domain features and any third-party costs depend on your selected plan and agreed service scope.
>
> **Restaurant & Bar Management:** **Currently no additional module management charge** for eligible plans/properties. Available functionality and usage limits depend on the confirmed feature entitlements of your subscription.
>
> We will not add new module charges automatically to an existing accepted subscription. Any future optional paid service will be disclosed in advance with its price and terms and will require your agreement before billing. Existing agreed plan benefits and charges remain protected for the accepted term.

### Data fields and statuses

```text
Property + Active Plan Entitlements
 -> Is Website Management included? yes/no
 -> Is Restaurant Management included? yes/no + feature limits
 -> Is Bar Management included? yes/no + feature limits (UNDECIDED)
 -> Current optional module charge: 0 when eligible and active
 -> Promotion metadata: no expiry/standard price invented
 -> Customer Quote/Invoice: explicit included/free line items
 -> Future add-on price proposal -> notification -> affirmative acceptance
 -> Activation on agreed effective date, not retroactively
```

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
       -> show Website Management included/no extra module fee (current)
       -> show Restaurant & Bar Management currently fee-free ONLY IF entitled
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
       -> Website / Restaurant / Bar module fee line items = ৳0 if eligible
       -> Clear exclusions (booking commissions, domain/provider costs, custom services)
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
- Features/menu/theme/website/restaurant/bar/HRM entitlements, custom exceptions by property and subscription version.
- Separate module fee and active promotion fields, eligibility, customer offer snapshots, renewal notice and affirmative opt-in for later paid optional add-ons.
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
13. Eligible plan: Website Management appears as currently ৳0 additional module fee; ineligible module never appears as free access.
14. Restaurant & Bar fee currently ৳0 only for entitled features; test future pricing toggle cannot back-bill existing accepted orders.
15. Customer offered a future paid add-on and declines: no new billing, no retroactive invoice, no unexpected midterm removal of contractually included features.
16. Quoted free module line items, limits, price/offer version and customer acceptance are preserved in audit trail.

## H. Pending approval / ambiguities

1. Does the per-room bill apply to EACH physical unit of the four types equally (Room/Cottage/Villa/Apartment)? Recommended yes for consistency; **not confirmed**.
2. Confirm the exact 'Ultra restaurant management limited' limit and how it compares to Business restaurant currently free.
3. Define remote-training free shift count, promo eligibility and expiry (none specified).
4. Confirm activation waiver eligibility and expiry (none specified).
5. Onsite: per-property/per-visit basis, number of training days, travel expense treatment and actual trainer count not specified.
6. Clarify timing of subscription charge, first payment and trial (if any), plus refund/cancellation.
7. Confirm plan module scope, especially Staff Basic Access vs Full HRM and Finance/Cashbox.
8. Confirm the precise Website Management free scope versus third-party domain/hosting and custom setup costs.
9. Confirm Restaurant and Bar entitlements by plan; Bar Management has not been explicitly assigned to a plan, and Ultra Restaurant limits remain undefined.
10. Confirm whether future paid module changes require opt-in (recommended), advance notice period (30 days proposed but unapproved), and grandfathering/renewal protections in finalized customer terms.
11. Update existing pricing pages, quotes and onboarding UI only AFTER this draft is reviewed and approved.

**Sources of truth:** User's new 2026-11-08 per-room pricing proposal, earlier plan feature/commission matrix, current [BinGi onboarding review index](README.md), [Accommodation architecture](https://github.com/nazmulhasanovx/Room-Accomodation-), [UI Foundation](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX). No claim of live system implementation.

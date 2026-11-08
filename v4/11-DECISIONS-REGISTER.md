# 11 — Decision Register & Risk Log
Date: 2026-11-08. Update before changing spec/producing the next Figma Make batch.

Legend: **DECIDED** = explicitly stated by owner or previously approved architecture; **RECOMMENDED** = proposed, not locked; **OPEN** = no reliable final rule. Conflict always flagged instead of silently resolved.

## Confirmed direction
| ID | Decision | Status |
|---|---|---|
| D-01 | Property-specific onboarding, owner sees only own authorized property | DECIDED |
| D-02 | Room, Cottage, Villa, Apartment are primary priority; Other/Custom deferred | DECIDED |
| D-03 | One-time config, saved locations, category defaults, guided individually saved Unit Numbers incl nonconsecutive | DECIDED in Accommodation architecture |
| D-04 | 80–90% applicable configuration before BinGi approval, full HMS only after property approval | DECIDED goal |
| D-05 | Plan-wise software module access and per-room custom quantity min 10 | DECIDED |
| D-06 | Monthly rate Starter 30, Business 50, Ultra 116 BDT per room | DECIDED latest pricing |
| D-07 | Six-month subscription discount 10%, annual 25% | DECIDED |
| D-08 | Business/Ultra activation standard 29,500 BDT, currently free | DECIDED |
| D-09 | Remote training 500 BDT per shift, currently free; promo discounts possible | DECIDED |
| D-10 | Onsite training 12,500 BDT; property provides visiting team's meals and stay | DECIDED |
| D-11 | Website Management and Restaurant & Bar Management currently no additional module fee | DECIDED fees only, not automatic entitlement |
| D-12 | Shared one 5-stage accommodation wizard; dynamic Rooms/Accommodations label | DECIDED in prior accommodation architecture |
| D-13 | Public website/marketplace go-live separate from HMS approval | DECIDED product direction |
| D-14 | No automatic bulk Unit Creation in onboarding; owner uses Save & Add Next to register real physical Units while repeating no Category/Location fields | DECIDED latest owner instruction |
| D-15 | Keep BinGi Starter/Business/Ultra dashboard screenshot appearance as Figma Make visual foundation | DECIDED latest owner instruction |

## Recommended changes needing owner approval
| ID | Decision | Reason |
|---|---|---|
| R-01 | Use six top-level onboarding sections and Airbnb-inspired task panels | Less cognitive load |
| R-02 | Same core 4 accommodation types available on all three plans | Simplifies pricing/product |
| R-03 | Count 1 Room/Cottage/whole Villa/whole Apartment as 1 billable Unit | Avoid bedroom disputes |
| R-04 | If actual units <10, bill for minimum 10 without creating fake inventory | Allows boutique properties |
| R-05 | Preview/read-only dashboard while approval pending | Owner can validate |
| R-06 | Quote accepted during onboarding, collect first subscription after property approved | Minimize rejected-property refund disputes |
| R-07 | Preserve accepted module rights and fees for committed billing term | Customer trust |
| R-08 | Not-applicable/Recommended/Optional items bypass required readiness | Reach 90% without friction |
| R-09 | Versioned templates, plan fee rules, permission flags and acceptance snapshots | Safe future revisions |

## Open / inconsistent — must decide before signed contract or production
| ID | Open question | Impact |
|---|---|---|
| O-01 | "Per Room" commercial label vs four-type Unit accounting? | Pricing/quantity |
| O-02 | Is 10 a minimum *billed* quantity or minimum *eligible real* inventory? | Boutique onboarding |
| O-03 | Restaurant "currently free" vs Ultra "restaurant limited"; exact Business/Ultra menu and feature caps? | Entitlements |
| O-04 | Bar Management permitted on which plan and what bar-specific capability? | Entitlements/legal |
| O-05 | Website management scope vs hosting, custom pages, domain registration/renewal? | Future billing disputes |
| O-06 | Activation waiver eligibility/end date, and price basis / how to display reference fee? | Promotions |
| O-07 | Remote shift minutes/participants, currently free eligible count & expiry? | Services |
| O-08 | Onsite number of staff, duration, visits, transport/travel, cancellation? | Services |
| O-09 | Exact first payment trigger, trial, refunds, renewal, delinquency, proration? | Finance |
| O-10 | Booking commission calculation base and refunds; taxes/payment gateway fees? | Finance |
| O-11 | Basic staff/team vs Ultra Full HRM, Finance/Cashbox module boundaries? | Plan gating |
| O-12 | Physical Unit quotas for mixed inventory, future Dormitory bed accounting? | Inventory/plan |
| O-13 | Identity/business document minimums for BD and other markets, retention? | KYC/security |
| O-14 | Existing live PMS/backend contracts, OTA integrations and migration approval? | Release safety |

## Product risks with mitigations
- Risk: Extremely low subscription + broad free human support -> poor unit economics. Mitigation: real hosting/support cost model, free training cap, promotion controls.
- Risk: Free module feels permanent even though promo -> disputes. Mitigation: precise scope, dated accepted offers, advance notice and opt-in for future paid optional add-ons.
- Risk: long 90% onboarding -> abandonment. Mitigation: six simple sections, presets, autosave, skip unused modules, assisted setup, measurable conversion.
- Risk: multiple property data leakage -> security incident. Mitigation: server-side tenant authorization, row scoped queries, tests and audit.
- Risk: existing reservations invalid after structure change -> operational loss. Mitigation: migration plan, immutable IDs, conflict detection and staging.

## Review protocol
Set "Owner Approved: YES/NO", approver date and rationale for each R or O decision. Do not infer owner acceptance from Figma screens. Explicitly update affected pricing, UI, QA and older document status after any decision.

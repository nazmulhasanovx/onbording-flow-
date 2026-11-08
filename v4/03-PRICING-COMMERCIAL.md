# 03 — Subscription, Promotions and Services
Status: Latest user-provided working rates, pending final published commercial agreement. Earlier fixed room-tier prices superseded for **new onboarding planning only**, not retroactively.

## Base subscription (BDT)
| Plan | Rate / month / Room | Minimum billing Q | Q=10 monthly | Q=10 six months (-10%) | Q=10 year (-25%) |
|---|---:|---:|---:|---:|---:|
| Starter | 30 | 10 | 300 | 1,620 | 2,700 |
| Business | 50 | 10 | 500 | 2,700 | 4,500 |
| Ultra | 116 | 10 | 1,160 | 6,264 | 10,440 |

Owner custom Q: 10,11,12,13,... whole numbers; no arbitrary maximum specified. Q=15 examples: 450 / 750 / 1,740 BDT monthly. Formula: Q × monthly rate × term months × (1 - applicable subscription discount); discount 0%/10%/25% for 1/6/12 months. Taxes separate as applicable. Rounding according to approved money policy, use exact numeric money types. Do not assume tax-inclusive.

**Commercial clarification pending:** Owner said "per room". Since core product manages Room/Cottage/Villa/Apartment, recommend equal 1 billable physical accommodation Unit each, regardless of bedroom count. For 7 actual Cottages with minimum billable 10, recommend charge for 10 while only creating seven real units (no fake inventory); this *minimum billing* reading needs final approval. Show physical count and billable Q distinctly.

## Current service promotions
| Item | Standard | Currently charged | Condition |
|---|---:|---:|---|
| Starter Activation | not applicable | 0 | no Starter activation |
| Business Activation | 29,500 | 0 | temporary waiver, expiry not defined |
| Ultra Activation | 29,500 | 0 | temporary waiver, expiry not defined |
| Remote Team Training | 500 / shift | 0 | promo; free shift count and shift duration not defined |
| Onsite Training | 12,500 | 12,500 | property provides visiting team's meals and stay |
| Website Management | no separate fee specified | 0 extra currently | only entitled plan; third-party costs excluded |
| Restaurant & Bar Management | no separate fee specified | 0 extra currently | only entitled features; Bar scope by plan NOT decided |

Do NOT invent a former list price for Website/Restaurant/Bar. Do NOT promise "free forever". Remote training discounts configurable but cannot create negative charges. Onsite visit/day, travel cost, trainers count and service duration open decisions. Historical setup/training per-room-tier fee matrix is no longer assumed current.

## Existing booking commission terms (carry forward pending confirmation)
| Channel | Starter | Business | Ultra |
|---|---:|---:|---:|
| BinGi marketplace | 12% | 8% | 4% |
| Property website booking | 1.5% | 1% | 0.5% |
| Walk-in | 0% | 0% | 0% |
Commissionable base, refund reversal, taxes/fees and payment processing must be defined before billing.

## Owner-facing quote (required line items)
~~~text
Plan/rate × Billable Q × 1/6/12 months
 - Subscription term discount only
 + Activation standard fee (if applicable)
 - Activation current waiver (if eligible)
 + Remote training fee × accepted shifts
 - Remote promo discount (if eligible)
 + Onsite service (if selected; not stacked with remote unless agreed)
 + Approved extra implementation/travel/services
 + Applicable taxes
 = TOTAL AMOUNT DUE (show exact currency)
~~~
Additionally display: "Website management: included / currently ৳0 extra" and "Restaurant & Bar: currently ৳0 extra only where plan entitled". Explain purchased domain renewal, gateway/provider fees, custom work and commissions separately. Plans and limits shown before acceptance.

## Customer protection
- Persist price_rule_version, plan_version, property_id, base Q, quoted effective amount, each discount/waiver, terms, customer acceptance time, transaction IDs and tax context; no secrets in git.
- Never amend confirmed invoices when Super Admin changes pricing. No new optional module fee without advance disclosure and affirmative consent; protect accepted term.
- Paid subscription, setup/training service order and invoice are independent.
- For first activation, recommend collect subscription **after BinGi property approval** to reduce rejected-property refunds; this sequencing is PROPOSED, not yet user-locked. Customer may review/accept quote earlier.
- Billing start, renewals, trial, cancellations, refunds, proration and promo eligibility are unresolved; do not guess.

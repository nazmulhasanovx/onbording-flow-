# 05 — Figma Make: Waiting, Read-Only Preview, Activated UI & Super Admin
Status: batch 5. Create WAIT-01, PREV-01, HMS-01, ADM-01, ADM-02, ADM-03 only. Use Base Prompt, [Approval Lifecycle](../05-APPROVAL-ACTIVATION.md) and [Admin spec](../08-SUPER-ADMIN.md).

## Owner after submit
**WAIT-01 / Property Review Status**: show Property name, saved summary, submitted date (demo), Pending Review, required payment status, optional remote/onsite scheduling, actual Room/Cottage/Villa/Apartment totals, support link, versioned quote. Alternative states "Needs Changes" with exact link to P02-07 or P06-03 then Resubmit; On Hold with reason; Approved with separate activation conditions.

**PREV-01 / Read-Only Property Dashboard**: simple cards for actual Units, Categories, rates and Website Draft; prominent "Preview — not operational yet" label. All booking/payment/publish buttons disabled with plain reason, no fake backend data. Owner can exit to review status.

**HMS-01 / Activated Plan-Specific Dashboard**: premium Pearl Light dashboard header and authorized Property scope, dynamic "Rooms" or "Accommodations" nav, plan-only modules, real conceptual metrics placeholders, separate Website Go-live checklist. Show Starter, Business and Ultra variants of the SAME dashboard (not three unrelated designs). Never show another property's booking.

## Super Admin
**ADM-01 / Review Queue + Detail**: filters pending/resubmitted/hold; one demo property review shows required docs summary (no real ID), category/unit counts, rates, booking overlap findings, accepted quote, exact approval flags and change request composer; decisions Approve/Needs Changes/Hold/Reject with reason and audit note.

**ADM-02 / Plan & Promotions Console**: edit plan per-room price, minimum Q, 6/12 discounts, activation standard/waiver and training rates/promos with future effective date and immutable accepted customer quote warning. Entitlement checkboxes should show OPEN labels on undecided Bar scope; no fake auto-billing. Show audit history example.

**ADM-03 / Training Service Orders**: remote shifts 500 promo free, onsite 12,500, meals/stay by property, scheduling, assigned trainer, service statuses and invoice link. Clear extra cost confirmation. Full HRM not part of this admin screen.

## Prototype state machine interactions
~~~text
P06-04 Submit -> WAIT-01 Pending -> PREV-01 -> WAIT-01
Admin ADM-01 Request Changes -> WAIT-01 Needs Changes -> P02-07 correction -> Resubmit
Admin ADM-01 Approve -> WAIT-01 Approved + Awaiting Payment
Simulate required commercial condition met -> HMS-01 available
Channel Website Draft remains unpublished until readiness
~~~
Approval and payment are independent flags. Training scheduled does not imply payment/approval. Entire sequence is local Figma prototype, not a real authorization or payment event.

## Quality gates
Roles isolated: owner cannot access admin. Brand and controls stable across roles. Verify refusal state for owner opening unauthorized property/route, no exposure of private verification docs. Dashboard variant must use actual entitlement matrix, with unresolved Restaurant/Bar notes rather than invented modules.

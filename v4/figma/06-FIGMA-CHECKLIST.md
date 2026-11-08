# 06 — Figma Make Quality Review and Dev Handoff
Use after EACH packet, not only at the end. The owner wants one-by-one review.

## 1. Screen/frame coverage
- All packet-required screen IDs exist, correctly titled and linked from predecessor/successor.
- One clickable happy path; at least one error/correction path; no dead Back/Continue/Save/Add/Review controls.
- Same shared Wizard/Onboarding Shell, footer CTA position, input spacing and icon placement.
- No duplicate full dashboard per accommodation type; variants share components and consistent data model.

## 2. Key scenario replay
~~~text
A. Room-only hotel: Register -> Room -> Main/Floor1 -> Deluxe Twin -> 101,103,105
 -> Rates -> Starter -> quote -> submit -> pending -> approved -> Rooms dashboard.
B. Mixed resort: Room + Cottage + Villa -> configure Buildings/Zones once -> add
 101, C01, V01, V03; count real 4 units, bill min 10 only if policy confirmed.
C. Apartment: Tower A and B Floor1 -> TA-101 and TB-101; Studio with no
 separate bedrooms valid; entire Apartment counted once.
D. Business: Restaurant enabled only when entitlement permits, currently no
 separate incremental management charge; promo never secretly increases total.
E. Ultra: HRM/Inventory visible; "Ultra Restaurant Limited" marked unresolved.
~~~

## 3. Logic and commercial validation
- Q=10 Starter 6m total 1620 BDT; Business 6m 2700; Ultra annual 10440 pre-tax.
- Business/Ultra activation reference 29,500 currently waived to 0; remote 500/shift currently free; onsite 12,500, meals+stay notice.
- Website/Restaurant/Bar currently fee-free as additional module fees where eligible, without assuming feature access, domain fee-free or unlimited support.
- No conflicting booking writes, no duplicate unit codes, no copying other property's categories into current property.
- Approval, payment and channel publishing distinctly represented; no claim of live action.

## 4. Responsive and accessibility
Desktop 1440px, compact 1024px and mobile 390px; layouts remain readable; keyboard focus and errors next to fields, input labels, modal escape/focus return; Bengali and English text fit. No unlabelled icon-only buttons. Empty/error/loading/success/draft/pending states available as component variants.

## 5. Owner sign-off template
Packet ID:
Date:
Figma file/page:
Approved frames:
Corrections required:
Business decisions changed (IDs from V4/11):
New component variants:
Unresolved before next packet:
Owner Approved: YES / NO

## 6. Developer handoff fields
For each screen: Figma frame ID, controlled form fields, field source/reuse, validations, RBAC/property scope, plan entitlements, server action (to implement), request errors, success transition, analytics event, QA IDs, redaction requirements. Do not infer API endpoints from the prototype. Any code changes/migrations are a separate authorized engineering task.

## 7. Stop rules
Do not proceed to design the next type if common 5-step wizard or Room variant is rejected. Do not label unresolved pricing, Bar or payment sequencing as a final customer commitment. Never ask Figma Make to deploy, charge, publish real listings or access personal KYC.

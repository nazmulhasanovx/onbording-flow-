# 10 — QA, UX and Commercial Acceptance Suite
Status: Test PLAN, not a record of completed tests. Each ID should become an executable test case when implemented.

## Owner UX, scope and progress
- UX-01 Account registration happens once; one account can create or resume different authorized properties.
- UX-02 Owner of Property A sees zero B categories/zones/units in UI, exports and API by guessed ID.
- UX-03 Switching property preserves separate onboarding progress, subscription and approval status.
- UX-04 Six-section progress does not mix inner screen progress; Back, Next, Save & Exit stay same location.
- UX-05 Autosave failure retains unsaved input and supports retry; duplicate Submit is idempotent.
- UX-06 Optional or plan-ineligible module cannot block 100% required checklist.
- UX-07 Mobile <=768 and desktop 1280+, browser zoom, keyboard, Bangla long copy, reduced-motion pass.
- UX-08 Pending approval shows read-only preview/status and correction links, not live booking actions.

## Accommodation / location / category
- ACC-01 Room defaults Building>Floor, selects 101,103,105 exactly, NOT 102/104.
- ACC-02 Cottage uses Zone and optional Block; no forced Floor. Internal levels do not become sellable room.
- ACC-03 Villa with 2 bedrooms and a pool creates exactly one sellable Villa; V01/V03 gap valid.
- ACC-04 Apartment Studio can have zero separate bedrooms + bed in shared space.
- ACC-05 Tower A 101 and Tower B 101 cannot collide as full Unit code; TA-101/TB-101 valid.
- ACC-06 Saved Location and Category reused on later additions; no repeated property-wide fields.
- ACC-07 100+ floors, custom prefixes/aliases, manual codes and sequential Save & Add Next, without auto-generating missing Units.
- ACC-08 Same category/gallery video inherited; Unit-level override/hide retained; URL validation rejects unsafe hosts.
- ACC-09 Concurrent individual draft Unit saves cannot create duplicate ID; failed save preserves input and doesn't silently create a Unit.
- ACC-10 Changing booked Unit or its location requires impact review; all reservation references preserved.
- ACC-11 Room-only HMS navigation says Rooms; mixed type says Accommodations; guest app says Stays.
- ACC-12 Empty inventory, invalid category, missing location and over capacity show actionable errors.

## Booking and readiness
- BOOK-01 Existing bookings YES must map dates/units; overlapping active bookings are rejected.
- BOOK-02 Existing bookings NO requires explicit confirmation.
- BOOK-03 Unit maintenance block takes priority over same-date new availability.
- BOOK-04 Draft/published status differs from operational Active and date Available.
- BOOK-05 Website cannot go live while missing validated inventory/rates/channel readiness.

## Subscription and promotions
- BILL-01 Starter Q10 monthly=300, six months=1620, annual=2700 BDT pre-tax.
- BILL-02 Business Q10 monthly=500, six months=2700, annual=4500.
- BILL-03 Ultra Q10 monthly=1160, six months=6264, annual=10440.
- BILL-04 Custom Q13 works; Q9 is reconciled to minimum billed Q10 without fake physical units (if policy approved).
- BILL-05 Total physical Unit quantity mixed property consistent with approved Unit-count rule.
- BILL-06 Business/Ultra activation std 29,500 currently waiver to zero; Starter no activation.
- BILL-07 Remote training std 500/shift, current free promotion, no negative/undefined fee stack.
- BILL-08 Onsite 12,500; meals/stay owner obligation disclosed before accept; no unapproved travel fee.
- BILL-09 Website and eligible Restaurant/Bar incremental module fees zero currently; do not imply ineligible feature access.
- BILL-10 Subscription cycle discounts never accidentally reduce setup/training/booking commissions.
- BILL-11 Accepted quote/invoice version immutable when Super Admin updates future rates; no retroactive charge.
- BILL-12 No optional paid module enabled or billed without prior explicit customer consent.
- BILL-13 Upgrade/downgrade preserves Unit/booking history and previews new charge or quota excess.
- BILL-14 Accepted billing period first charge, renewal and refund tested only after final policy approval.

## Admin and activation
- ADM-01 Owner submits only own property after 100% applicable required checks.
- ADM-02 Admin reviewer requests correction; owner edits exact subsection, resubmits with audit history.
- ADM-03 Invoice Paid alone does not approve property; Approved alone does not mean Payment Collected.
- ADM-04 A property under review cannot accept live bookings; read-only preview safe.
- ADM-05 Training orders and scheduled shifts do not overwrite subscription/approval states.
- ADM-06 Each channel independent approval/publication; disabling channel doesn't delete historical bookings.
- ADM-07 Admin permissions, sensitive owner documents and audit trails access-restricted.

## Acceptance gates
Gate A: user approves Product/Commercial Open Decisions; Gate B: Figma component system + all primary paths reviewed; Gate C: backend authorization, migration and billing model verified; Gate D: functional staging and regression passed; Gate E: rollout monitoring/rollback ready. No checklist item is claimed tested by creation of these docs.

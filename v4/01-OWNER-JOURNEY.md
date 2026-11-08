# 01 — Owner Onboarding Journey
Status: PROPOSED V4; six owner-facing sections. Each large section may contain 1–5 focused tasks; no oversized multi-purpose form.

## Registration / property entry
~~~text
REGISTER/LOGIN ONCE -> verify contact -> accept terms
 -> My Properties (only authorized properties)
    -> New Property: create server-scoped DRAFT property_id
    -> Existing Property: resume its own saved progress/approval
~~~
Save owner identity/account once; do not require new account per property.

## Section 01: Your Property [ONB-01]
- Property name, Hotel/Resort/etc., country/division/district/area/full address and map pin (optional), official mobile/email, owner/manager role.
- Show four primary accommodation types as multi-select *after* property type (recommended defaults, editable).
- Show plan preview Starter/Business/Ultra and estimated physical count; owner can choose preliminary plan now. Final quote reconciles with actual inventory in section 06.
- Store property-specific currency, timezone, language, check-in/out/policy defaults ONCE in a short expandable card. Use appropriate suggested defaults, confirm not assume.
- Autosave after safe events and explicit Continue; no duplicate business/address step.

## Section 02: Accommodations [ONB-02]
- Start with compact type picker; don't ask about non-enabled types.
- Show recommended location strategy and numbering preview for each enabled type; owner only edits if different.
- Location Setup reuses actual buildings/towers/floors/zones/blocks across categories.
- Create or reuse Category with beds/occupancy/amenities/gallery/highlights, optional video, description, base rate.
- Add exact physical units by manual, range, count or checkbox selection; preview duplicates, reserved codes, plan capacity and mixed inventory totals.
- Save Draft / Finish & Add Another Category. Fast path for repeat add.
- Before continuing require at least one real sellable category and configured physical unit; custom billing minimum 10 does NOT require 10 fabricated units.

## Section 03: Booking Ready [ONB-03]
- Check-in/out, taxes etc. are inherited; edit through link to single source of truth.
- Category rates, selected weekday/weekend or seasonal overrides if useful, restrictions, unavailable dates.
- "Do you already have bookings?" YES -> add/import, map dates/category/unit, reconcile overlaps and maintenance blocks. NO -> explicit confirmation.
- Preview inventory and first calendar; do not claim public bookings activated.

## Section 04: Plan-Aware Operations [ONB-04]
- Starter: core guests/front desk, permitted basic team roles/payment defaults only.
- Business: show entitled housekeeping, expenses, meal/restaurant/QR order/other services conditionally; setup modes can be "not operating this department" and omit irrelevant forms.
- Ultra: additional verified entitlements such as HRM/Inventory/advanced operations. Avoid forcing 500 dishes or full payroll to submit a property.
- Staff invite and role permissions: invite only needed people; otherwise "I'll add staff later" if not blocking critical operation.
- Full Restaurant & Bar feature scope NOT final. Never show Bar as guaranteed until entitlement approved.

## Section 05: Digital Presence and Guest Payments [ONB-05]
- Guest collection methods (cash, transfer, mobile banking, supported provider), deposit/refund defaults, receipt details, gateway conditional.
- Website branding (inherited property name/logo), theme permitted by plan, gallery cover/reorder, two to three highlights, editable description, contact/map inherited.
- Website preview, save DRAFT. Marketplace requests and OTA integrations remain separate and never auto-publish.

## Section 06: Review and Confirm [ONB-06]
- Compare actual physical units vs preliminary quantity and chosen *billable* quantity (minimum 10); permit adjust (do not silently change).
- Select 1/6/12 month cycle, see discounted subscription, separate activation/training and waived promos, commissions, taxes and exclusions.
- Service method Self/Remote/Onsite if available; remote per shift currently free, onsite ৳12,500 with property meals/stay notice.
- Verify legal owner/business documentation according to approved rules; collect sensitive documents securely, do not embed NID in public Github/design mocks.
- Readiness page groups Required / Recommended / Optional; explicit "Fix" links.
- Customer accepts quote/version and service terms; submit for BinGi review.

## Pending/approved branch
~~~text
Submitted -> Pending Review -> [Needs Changes | On Hold | Rejected | Approved]
 Needs Changes -> single named section edit -> resubmit
 Approved -> satisfy required payment/contract conditions -> HMS Dashboard
 Channel Ready separately -> publish Website / Marketplace
~~~
Before approval: review/status, safe edit where allowed, read-only preview, support and receipts; no live HMS writes or guest bookings.

## UX requirements
Keep step label "Section 2 of 6" separate from focused internal task progress. Save & Exit always present; Back/Continue in fixed footer; confirm before abandoning unsaved entries. Use soft defaults not invented property data. Property switcher never surfaces unauthorized properties. English UI copy first and Bangla equivalent for localized handoff.

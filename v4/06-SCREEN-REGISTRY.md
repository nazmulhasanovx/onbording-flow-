# 06 — Stable UI Screen Registry / Navigation Contract
Status: V4 proposed layout inventory. IDs are stable across Figma designs, QA and development; do not renumber approved IDs.

**6 owner-facing sections**, **35 named view IDs**, plus type-specific variants, drawers and review states; **not** 35 separate disconnected dashboards. Reuse a single Wizard Shell and components.

| ID | Screen name / intention | Section / Figma batch |
|---|---|---|
| AUTH-01 | Register / Login / Verification | Batch 1 |
| OWN-00 | Authorized Property Picker / Resume | Batch 1 |
| P01-01 | Property type + name + contacts | Section 1 / Batch 1 |
| P01-02 | Location + address + map | Section 1 / Batch 1 |
| P01-03 | Accommodation type multi-select | Section 1 / Batch 1 |
| P01-04 | Preliminary plan + estimated quantity | Section 1 / Batch 1 |
| P01-05 | Property operating defaults (compact) | Section 1 / Batch 1 |
| P02-01 | Type preset summary and edit | Section 2 / Batch 2 |
| P02-02 | Location hierarchy and numbering | Section 2 / Batch 2 |
| P02-03 | Accommodation inventory workspace | Section 2 / Batch 2 |
| P02-04 | Wizard: Type + existing/new Category | Section 2 / Batch 2 |
| P02-05 | Wizard: Category details/capacity/beds | Section 2 / Batch 2 |
| P02-06 | Wizard: Category media, highlights & description | Section 2 / Batch 2 |
| P02-07 | Wizard: Guided Unit Entry — one actual Unit at a time | Section 2 / Batch 2 |
| P02-08 | Wizard: Price/inheritance/exceptions | Section 2 / Batch 2 |
| P02-09 | Wizard: Review/create + error/success | Section 2 / Batch 2 |
| P03-01 | Rates and availability basics | Section 3 / Batch 3 |
| P03-02 | Existing reservations choice/import/blocks | Section 3 / Batch 3 |
| P03-03 | Booking readiness/calendar preview | Section 3 / Batch 3 |
| P04-01 | Applicable operations module chooser | Section 4 / Batch 3 |
| P04-02 | Team roles / invite essentials | Section 4 / Batch 3 |
| P04-03 | Dynamic module setup (Housekeeping/Meals/HRM) | Section 4 / Batch 3 |
| P05-01 | Guest payment collection setup | Section 5 / Batch 4 |
| P05-02 | Website theme/content and draft preview | Section 5 / Batch 4 |
| P05-03 | Gallery/cover/highlights/description | Section 5 / Batch 4 |
| P06-01 | Quantity, plan and 1/6/12-month quote | Section 6 / Batch 4 |
| P06-02 | Activation/training/waivers + final breakdown | Section 6 / Batch 4 |
| P06-03 | Owner/business verification | Section 6 / Batch 4 |
| P06-04 | Readiness checklist + submit confirmation | Section 6 / Batch 4 |
| WAIT-01 | Pending, hold, correction & resubmit | Approval / Batch 5 |
| PREV-01 | Property read-only dashboard preview | Approval / Batch 5 |
| HMS-01 | Activated plan-aware dashboard template | After approval / Batch 5 |
| ADM-01 | Super Admin property review queue/detail | Admin / Batch 5 |
| ADM-02 | Plan prices, promotions, entitlement controls | Admin / Batch 5 |
| ADM-03 | Setup/training service order management | Admin / Batch 5 |

**Numbering correction:** The registry contains 35 named view IDs including account, approval and admin; actual required designs reuse templates and may differ by state. Do NOT infer workload simply by multiplying accommodation types × wizard screens. Room/Cottage/Villa/Apartment share P02-04–09 with conditional fields.

## Navigation
Global shell: header [Back | property identity | Section x of 6 | Save & Exit]; progress; content; fixed bottom action area [Back, Save Draft, Continue/Review]. No duplicate top-right Continue on some screens. Section tree collapsible; each task always has one obvious primary CTA. After P02 inventory completion return to P02-03 rather than exiting entire onboarding.

## States to design for every critical template
Initial/pre-filled, loading/skeleton, invalid field, saving, saved, connection failure with retained inputs, empty inventory, property permission failure, duplicate ID/over quota, unsaved changes, review warning, confirmed success. Additional: no plan entitlement, payment pending, correction requested, approval locked, mobile stacking.

## Figma handoff
Design components before pages. Use clickable linking for primary happy path and at least one exception path per batch. Every frame named with screen ID, e.g. "P02-07 / Villa / Location & Units / Filled".

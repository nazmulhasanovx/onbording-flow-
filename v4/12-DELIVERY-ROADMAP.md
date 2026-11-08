# 12 — Step-by-Step Figma Make and Implementation Roadmap
Status: planning, not timeline promise. Work in narrow batches, review before continuing.

## Phase 0 — policy / design foundation
Read V4 00–11; resolve O-01/O-02 billing units, O-03/O-04 features, O-09 payment activation or mark a prompt explicitly provisional. Create Pearl Light components, type styles, input/error/empty/loading/confirmation states and six-section onboarding shell. No production backend work implied.

## Figma Make delivery order (one small review at a time)
**Batch 1: Property & Preliminary Plan**
AUTH-01, OWN-00, P01-01..05. Outcome: create Property Draft, relevant four-type selection and preliminary subscription plan.

**Batch 2: Core Accommodation System** (highest priority)
P02-01..09. First build Room entire happy/duplicate/error path, review and lock common UI. Then Cottage, Villa, Apartment as variants using SAME components, do not build four independent dashboards. Mixed-property preview and bulk IDs validated.

**Batch 3: Booking & Plan Operations**
P03-01..03, P04-01..03. Rate inventory, booking import/conflict, plan-entitled modules, staff access.

**Batch 4: Digital, Commercial & Submission**
P05-01..03, P06-01..04. Website preview, guest payment, exact 1/6/12 price calculations, free promos, consent, KYC readiness.

**Batch 5: Approval, Preview and Super Admin**
WAIT-01, PREV-01, HMS-01, ADM-01..03. Distinct approval/payment/channel status; owner locked from live operations until approved.

## Per-batch handoff checklist
- Explicit scope: screen IDs and clickable routes only; don't invent adjacent app modules.
- Figma frames, variants, prototype links, English copy + Bangla-readable variants.
- Screen state examples: blank, prefilled, validation error, save loading/failure, success, no plan feature, mobile.
- Consistent header/stepper/footer and tokens from Foundation. No duplicated property input.
- Short review questions and documented owner feedback. Only after review: modify relevant markdown decisions + produce next batch.
- For developer handoff: screenshot/frame ID -> state -> field source -> validation -> server action -> success/error transition.

## Implementation phases AFTER Figma approval
1. Plan/entitlement, tenant authorization, property drafts and audit data foundations.
2. Location hierarchy/category/unit database with safe migration from existing Room records.
3. API validation, bulk ID creation, booking conflict engine and date-based availability.
4. Subscription quote acceptance, invoice/payment, training service orders and approval state machines.
5. Website and marketplace publish readiness; permitted integrations.
6. Comprehensive QA, secure staging, migration/backfill, feature flag, rollback and monitored rollout.

## Release readiness gates
A. Commercial decisions signed off.
B. Owner tests show no repeated configuration and acceptable completion for representative Room-only, Resort-mixed and Apartment property.
C. Security and booking integrity tests pass.
D. Billing quote and no-hidden-charge tests pass.
E. Owner/approved Super Admin agree go-live conditions.

## Out of scope for first round
Dormitory bed-level sales, Other/Custom, unauthorized OTA automation, exhaustive website theme variations, production code rewrite, features absent from selected plan. Build after separate spec review.

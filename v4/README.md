# BinGi HMS — Onboarding V4 Master Workspace
Version: V4.0 review draft | Date: 2026-11-08 | Status: PROPOSED / NOT IMPLEMENTED

**Purpose:** One organized source for owner onboarding planning, plan-based billing, four priority accommodation types, Super Admin review, and screen-by-screen Figma Make creation.

## Read and review in order
1. [00 MASTER PRODUCT PLAN](00-MASTER-PLAN.md): vision, six stages, decisions hierarchy.
2. [01 OWNER JOURNEY](01-OWNER-JOURNEY.md): onboarding steps, paths and handoffs.
3. [02 ACCOMMODATION ENGINE](02-ACCOMMODATION-ENGINE.md): Room, Cottage, Villa, Apartment, shared wizard, guided one-by-one actual Unit registration.
4. [03 PRICING AND COMMERCIAL](03-PRICING-COMMERCIAL.md): per-unit proposal, discounts, promotions, setup/training.
5. [04 PLAN ENTITLEMENTS](04-PLAN-ENTITLEMENTS.md): visible vs locked modules; outstanding scope questions.
6. [05 APPROVAL AND ACTIVATION](05-APPROVAL-ACTIVATION.md): payment, review, operational and online gates.
7. [06 SCREEN REGISTRY](06-SCREEN-REGISTRY.md): stable screen IDs, flows and Figma order.
8. [07 UI FOUNDATION](07-UI-FOUNDATION.md): tokens, components, behaviour, accessibility.
9. [08 SUPER ADMIN](08-SUPER-ADMIN.md): approvals, pricing rules, service orders.
10. [09 DATA AND MIGRATION](09-DATA-MIGRATION.md): conceptual property-scoped model and existing HMS compatibility.
11. [10 QA AND ACCEPTANCE](10-QA-ACCEPTANCE.md): test cases and sign-off.
12. [11 DECISIONS](11-DECISIONS-REGISTER.md): settled, provisional and unresolved.
13. [12 DELIVERY ROADMAP](12-DELIVERY-ROADMAP.md): screen design batches and release gates.
14. [13 GUIDED UNIT REGISTRATION](13-GUIDED-UNIT-REGISTRATION.md): latest owner decision—no bulk Unit Creation in onboarding.
15. [Figma Make Work Packets](figma/README.md): copy-ready prompts; ONE batch at a time.

## Status and source-of-truth rules
- **User-decided direction:** One account, independent property onboarding; four primary accommodation choices; complete relevant configuration before BinGi approval; plan-based access; custom room quantity, minimum 10; latest per-room rates; current fee-free promotions.
- **Existing approved accommodation concepts:** one-time location configuration; category/unit hierarchy; whole-Villa/Apartment inventory; dynamic Rooms/Accommodations label. See [Accommodation Architecture](https://github.com/nazmulhasanovx/Room-Accomodation-).
- **Proposals requiring explicit review:** six navigation sections, minimum *billable* 10 for smaller properties, shared billable physical units for all four types, post-approval payment sequencing, read-only preview, precise Free-feature legal wording.
- **Not confirmed:** Restaurant/Bar access by plan, Ultra restaurant limits, remote shift length/free eligibility, activation waiver date, domain/hosting exclusions, tax/commission base and exact billing start.
- No code was audited or deployed by these markdown documents; they are product/design specifications and Figma handoff material. Do not represent proposed screens as implemented.
- Existing root 01–05 documents remain historical drafts; do not silently overwrite accepted customer contracts or pricing.

## Screenshot-matched Figma visual direction
Use the user-provided BinGi Starter/Business/Ultra dashboard screenshots as the primary reference. See [Figma Visual System](figma/07-SCREENSHOT-VISUAL-SYSTEM.md) and [First Figma Batch](figma/08-FIRST-DESIGN-BATCH.md).

## Review workflow
Review 00 -> 01 -> 02 -> 03/04/05 -> 06/07 -> each Figma packet. Record corrections in 11; mark a screen batch APPROVED only after owner review; then design next batch. Figma design is not authorization to deploy or change live hotel data.

## External references
- [Foundation UI & UX](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX) (proposed styling and navigation rules).
- [Accommodation Engine Master](https://github.com/nazmulhasanovx/Room-Accomodation-/blob/main/MASTER-PLAN.md).
- Prior flow drafts in repository root: [Room](../01-ROOM-ONBOARDING.md), [Cottage](../02-COTTAGE-ONBOARDING.md), [Villa](../03-VILLA-ONBOARDING.md), [Apartment](../04-APARTMENT-ONBOARDING.md), [Pricing V2](../05-PRICING-PLAN-AND-TRAINING-V2-DRAFT.md).

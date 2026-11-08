# 00 — Figma Make Base Design Prompt (Copy with one packet)
Status: MASTER DESIGN RULES; append exactly one task-specific packet.

## Role and objective
Act as Principal SaaS Product Designer for BinGi Hotel Management Technology, a premium desktop-first hospitality operating system. Build an editable, cohesive, clickable interface prototype for the **specified screen IDs only**, using reusable components, local UI state and meaningful transitions. Prioritize first-time Hotel/Resort Owner clarity. Avoid disconnected artboards or generic template layouts.

## Product model
One user -> multiple *authorized* independent properties -> one property onboarding at a time -> first-time accommodation setup -> category + physical units -> rates/bookings -> plan-aware operations -> draft website/guest payments -> final accepted quote and BinGi approval -> property-scoped HMS dashboard. Four priority accommodation types are Room, Cottage, Villa, Apartment. Whole Cottage/Villa/Apartment = one bookable physical unit; bedrooms are descriptive. No Dormitory or Other/Custom screens in this round.

## Exact visual system
Use the three user-provided BinGi Starter/Business/Ultra dashboard screenshots as PRIMARY VISUAL REFERENCE. Follow [07 Screenshot Visual System](07-SCREENSHOT-VISUAL-SYSTEM.md): screenshot-matched white sidebar, red active navigation/CTA, navy text, pastel peach/lavender/lemon/mint cards and faint lavender panel borders. Foundation tokens are proposed; reconcile exact screenshot appearance before final Figma approval. Calm white professional style, restrained red accent, clean cards and compact form controls. Design reusable tokens/components first. Use 4/8/12/16/24/32 spacing and consistent approx 40px desktop / 44px touch controls, 10px radius.

## Common onboarding shell
Header: BinGi brand left; Current Property and section indicator center; Save & Exit right. A 6-section progress rail on desktop; contextual tasks inside section. Main content uses max-width reading line, one question/task per panel, explanatory microcopy, no long form. Persistent bottom footer: Back on left, Save Draft secondary if needed, Continue primary in same slot always. Show loading, error, empty, saved and read-only states. Mobile single-column responsive.

## Interactions and behaviour
- Every visible Next, Back, Edit, Save, Add, Select, Remove, Review, Preview, Skip (when allowed), and Submit must navigate or update believable state; do not draw dead buttons.
- Local-state prototype: editable property fields, type selection, plan selection, one-at-a-time real Unit Number entry with Save & Add Next (no bulk creation), gallery ordering mock interactions, quote math, checklist status, correction loop; no claims of live database/API/payment connections.
- Preserve input values across Back/Next and type changes; keep selected property scope in local model.
- Dynamic rendering: hide inapplicable fields, show only entitled modules, explain missing required work.
- All layouts use consistent icon positions, button slots, form labels, validation and accessible focus/contrast. Long Bangla labels should fit. Skeleton and retry on mock save.
- Show at least one happy path + one meaningful error/alternate branch per packet.

## Commercial truth
Starter ৳30/room/month, Business ৳50/room/month, Ultra ৳116/room/month; minimum **billable** 10 proposed, 6-month 10% and 12-month 25% subscription-only discount. Business/Ultra activation standard ৳29,500 currently waived, remote training ৳500/shift currently free, onsite ৳12,500 and property provides meals/stay; Website Management and entitled Restaurant/Bar module fees currently zero extra. Entitlement of Bar and "Ultra Restaurant Limited" still OPEN; do not falsely activate them in prototype. Existing commission matrix separate.

**Latest owner decision:** No bulk Unit Creation in onboarding. Each Save & Add Next records exactly one real draft Unit, reusing saved category, location and policy. Never generate a range of Rooms merely from a count.

## Explicit non-goals
Do not copy Airbnb or competitor UI artwork; references are for interaction principles only. Do not put real owners' IDs, email, invoices or bank details in demo. Do not build a functioning payment gateway, backend, KYC upload service, authentication, OTA connector, live guest booking or publish live websites. Don't create unrelated HRM/Restaurant full apps inside onboarding.

## Handoff output
Editable frame/component hierarchy, consistently named screen IDs, clickable prototype linking all in-scope routes and validation states; one paragraph explaining happy path, errors and exactly which business rules remain tentative.

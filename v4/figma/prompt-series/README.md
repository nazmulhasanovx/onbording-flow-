# BinGi HMS — Figma Make Prompt Series

**Design status:** Review draft, no Figma file created by these specifications.

**Instructions for each packet:** First attach the user-provided BinGi F-01–F-07 Foundation screenshots and the three Starter/Business/Ultra Dashboard screenshots to Figma Make. Paste the existing [Base System Prompt](../00-BASE-SYSTEM-PROMPT.md) and [Visual Reference](../07-SCREENSHOT-VISUAL-SYSTEM.md) with EXACTLY ONE numbered packet. Reuse the existing Figma components. Build only in-scope IDs, clickable prototype interactions, responsive/error/empty states. Do not implement backend, database, booking, payment, OTA, KYC or live approval. Stop and review each before moving to next.

**Screen counting:** 36 unique view templates = 33 owner + 3 admin. P02-01–09 are shared across four types; plan Dashboard HMS-01 is ONE screen with three variants. Component boards and state variants do not add unique screens. Appearance APP-01 is ONE screen with SIX controls. 14 prompts = 13 foundation/owner/dash + 1 admin.

## Prompt order
01. [Reuse Foundation & Appearance](01-FOUNDATION-APPEARANCE.md) — APP-01
02. [Registration & Authorized Property Picker](02-ACCOUNT-PROPERTIES.md) — AUTH-01, OWN-00
03. [Property Profile & Initial Plan](03-PROPERTY-PRELIMINARY-PLAN.md) — P01-01..05
04. [Shared Accommodation Engine: Room First](04-ROOM-COMMON-WIZARD.md) — P02-01..09
05. [Cottage Type Adaptation](05-COTTAGE-VARIANT.md) — P02-01..09 Cottage variants
06. [Villa Type Adaptation](06-VILLA-VARIANT.md) — P02-01..09 Villa variants
07. [Apartment Type Adaptation](07-APARTMENT-VARIANT.md) — P02-01..09 Apartment variants
08. [Rates & Booking Readiness](08-RATES-BOOKINGS.md) — P03-01..03
09. [Starter/Business/Ultra Relevant Operations](09-PLAN-OPERATIONS.md) — P04-01..03
10. [Guest Payments & Website Draft](10-WEBSITE-PAYMENTS.md) — P05-01..03
11. [Pricing, Training, Verification & Final Review](11-QUOTE-VERIFY-SUBMIT.md) — P06-01..04
12. [Approval Status & Read-only Owner Preview](12-APPROVAL-PREVIEW.md) — WAIT-01, PREV-01
13. [Activated HMS Dashboard](13-DASHBOARD-PLAN-VARIANTS.md) — HMS-01 (Starter/Business/Ultra variants)
14. [Super Admin Review & Pricing Console](14-SUPERADMIN.md) — ADM-01, ADM-02, ADM-03

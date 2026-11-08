# 07 — Figma & UI/UX Foundation Alignment
Status: Proposed design instructions based on existing BINGI-FOUNDATION-UI-and-UX specs. Tokens are **proposed**, not proof of deployed UI.

## Brand / Pearl Light
- Logo accent: #FD413F; primary action: #C8232E; hover: #B11C29; pressed: #8F1520.
- Canvas: #F6F7FB; surface: #FFFFFF; ink: #18202F; muted text: #5F697A; border: #DCE1EA; selected: #FFF0EE; focus: #2456B8.
- Status colors need accessible paired tokens; do not use color alone to communicate successful billing/approval.
- Premium light UI, minimal ornament, compact professional data tables, consistent rounded cards. Do not copy Airbnb screens or use unauthorized real property branding.

## Type & spacing
- Page heading approx 24px / 32, section 18px / 26, body 14px / 20; Bangla fallback supported; confirm precise typography in UI-01.
- 4/8/12/16/24/32 spacing scale; 24px desktop page padding and 16px narrow; avoid page-wide horizontal scroll.
- Desktop width >=1280 expanded rail ~220px where applicable; 1024–1279 compact rail ~64px; below 1024 contextual drawer; below 768 single column. For focused onboarding, a dedicated progress sidebar may replace full HMS module rail rather than stacking both.
- 40px controls desktop / 44px touch; radius 10px; fixed button slots, primary min width ~112px, secondary ~88px.
- Purposeful 150–200ms transitions, skeletons matching final geometry, reduced motion and retained data on errors.

## Reusable Figma components (create once)
1. App Logo/Header + Property Scope Switcher (authorized only).
2. Onboarding progress Sidebar (six sections + active subtask).
3. Wizard Header, Context Breadcrumb, Stepper, Sticky Footer actions.
4. Accommodation Type Select Card, Category Card, Property Location Tree.
5. Guided one-by-one Unit Entry: save real Unit Number, keep Category/Location, exact saved list, nonconsecutive and duplicate feedback.
6. Category Form Panels (bed layout, bathroom, kitchen, pool, amenities).
7. Gallery uploader/cover/reorder, highlights multi-select, description text area.
8. Rate input and optional calendar preview; plan quota banner.
9. Plan Card, quantity stepper and billing-cycle selector; invoice breakdown.
10. Training selection card, promotional-free lines and service scope tooltip.
11. Required/Recommended/Optional checklist; payment/verification/approval status components.
12. Standard dialog/drawer, empty/loaded/invalid/loading/success states.

## Behaviour
One primary action per task, fixed Next/Back positions and deterministic progress. Save & Exit always possible. Selected plan changes module forms dynamically but must not delete entered data. If one valid Zone/Floor choice, auto-select; never show fields that do not apply. Preview exact numbering and actual billable Q before final purchase.
Use plain English labels with Bangla localization prepared: "Create your first room", "Choose existing category", "Review 3 units", "Save & exit", "Fix duplicate room number".

## Screenshot-matched Figma reference
The three user-uploaded BinGi Starter/Business/Ultra screenshots are the primary visual references for this Figma plan. Match their sidebar, header, red active navigation, pastel cards, deep navy typography, borders and buttons. See [Screenshot Visual System](figma/07-SCREENSHOT-VISUAL-SYSTEM.md); reconcile visual seeds with proposed Foundation tokens before implementation.

## UI source crosslinks
[UI-01 Typography](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX/blob/main/UI-01_Typography_and_Text_Styles.txt) · [UI-02 Colors](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX/blob/main/UI-02_Colours_Design_Tokens_and_Themes.txt) · [UI-03 Layout](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX/blob/main/UI-03_Spacing_Grid_and_Responsive_Layout.txt) · [UI-04 Controls](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX/blob/main/UI-04_Icons_Buttons_and_Form_Controls.txt) · [UI-06 Templates](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX/blob/main/UI-06_Page_Templates_Loading_States_and_Motion.txt).

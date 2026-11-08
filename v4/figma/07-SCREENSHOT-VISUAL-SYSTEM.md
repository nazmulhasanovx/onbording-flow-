# 07 — BinGi Screenshot-Matched UI/UX Design Reference

**Date:** 2026-11-08 | **Status:** V4 Figma visual direction, sourced from 3 user-uploaded Starter/Business/Ultra BinGi dashboard images. Not yet a Figma file or shipped UI.

## NON-NEGOTIABLE DESIGN DIRECTION

Use **the user's three BinGi screenshots** as the visual source of truth for Figma Make, not a generic SaaS theme. Attach all three images as design references inside Figma Make. They are 1671–1672 x 941 screenshots, and show three plan variants of the SAME product design system. Keep their professional Pearl Light style: white/near-white workspace, narrow navy text, BinGi red gradient selected action, outlined lavender cards, soft pastel KPI blocks, restrained purple progress indicators, same line icon family, and dense but legible tables.

This visual reference supersedes proposed color numbers when there is a genuine appearance mismatch; reconcile exact values against [Foundation UI tokens](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX/blob/main/UI-02_Colours_Design_Tokens_and_Themes.txt) before implementation. Do not claim sample values are a final audited design token export.

## Visual observations from source images

- **Desktop HMS Shell:** fixed approx. 268 px white sidebar on a 1672 px frame; top header approx. 66 px; main content starts after the sidebar with roughly 26–28 px horizontal inner margin.
- **Header:** property avatar/icon and name/location at left; rounded search at center-right; language, notification, help, round user avatar right. Header remains identical across all three plan dashboards.
- **Navigation:** simple outlined 20–24 px icons, uppercase dark-muted small group labels. Active Dashboard row is bright red pill/rounded rectangle with white text/icon. Consistent location for Settings, and plan name at bottom.
- **KPI cards:** single row of four equal flexible cards. Gentle warm peach, lavender, lemon and mint fills; white soft elevated icon tiles; dark large values. The accent colors indicate distinct metric types, not status guarantees.
- **Content cards:** large white panels with faint lavender borders, 12–18 px corners, subtle/shallow shadow, regular vertical spacing. Business/Ultra main left panel shows tasks and thin purple progress.
- **Buttons:** primary red, high contrast white label, consistent approximately 48–52px height on prominent dashboard action; secondary white outlined; utility action black/dark navy. Small inline row actions are outlined.
- **Tables:** purple-gray tinted header row, readable 14–16px, thin horizontal dividers, rounded group container, avatar initials in pale red circles, success pills in pastel mint.
- **Plan differences:** Starter fewer nav groups and small upgrade card, Business operational groups with optional locked features, Ultra full eligible nav. **The layout itself is identical**; plan and permissions determine content.
- **Responsive:** maintain layouts not pixel-bound; 1440x900 base, 1672x941 screenshot comparison, 1024 tablet, 390px mobile one column.

## Suggested visual token seed (approximate, sampled/estimated from screenshot)

| Semantic use | Seed value | Notes |
|---|---|---|
| App white surface/sidebar | #FFFFFF | High-contrast white |
| Near-white dashboard canvas | #FCFCFE | Faint cool canvas |
| Main dark ink | #10152F | Deep navy-black appearance |
| Secondary text | #4F5576 | Navy-gray |
| Selected navigation red | #E42228 | Observed dominant selected bar region |
| Primary CTA red | #E81822 | Observed main action region |
| Subtle border | #DADAF0 | Approximate faint lavender |
| Peach metric card | #FEF3F2 | Actual sample across region |
| Lavender metric card | #EDE9FD | Actual sample |
| Lemon metric card | #FEF5D1 | Actual sample |
| Mint metric card | #E1FAEC | Actual sample |
| Purple tinted table header | #F0ECF6 | Actual sample |
| Progress purple | #7448F7 | Approximation from visible bar |
| Positive status background | #DEF8E6 | Approximate status pill |
| Error / destructive | Accessible red pair | Contrast audit required |

Use Foundation token semantics and audit contrast. Avoid overusing badges, hard shadows, heavy glass/glows, decorative gradients and oversized onboarding illustrations. It should feel like **these screenshots, not Airbnb**. Airbnb supplies one-task-per-screen UX lessons only.

## UX: same theme, different task density

The screenshots show an **operating dashboard**, which should remain information-dense. Onboarding is different: keep the exact BinGi branding/color/navigation/controls but use a **focused guided setup workspace**, no full live HMS sidebar before property approval.

~~~text
ONBOARDING SHELL
[BinGi logo]  [Property draft name / Section X of 6]   [Help] [Save & Exit]
[6-section left progress sidebar] | [Clear title + short helpful text]
                                  | [One main task / card / selector]
                                  | [Saved property context summary]
[Fixed bottom footer]  Back | Save Draft | Continue / Save & Add Next
~~~

One shared container width, stable footer button positions, 40px desktop input/44px touch, 4/8/12/16/24/32 spacing; design for Bangla/English copy. Use calm whitespace, same card radii and icon positioning. No visually noisy multi-question page.

## Guided Unit Creation — LATEST OWNER RULE

No automatic bulk generate or "Create N Units" action in onboarding. One-time Property + Building/Floor/Zone/Block + Category setup; then owner explicitly enters one real Unit Number at a time.

~~~text
Category: Deluxe Twin (saved) | Location: Main Building > Floor 1 (saved)
Unit Number: [101] [Save & Add Next] -> list shows 101
Unit Number: [103] [Save & Add Next] -> list shows 101,103
Unit Number: [105] [Save & Review] -> list shows 101,103,105
Review exactly 3 actual Units; do not create 102/104
~~~

One saved Category/context persists. No extra room created from pricing's minimum billable 10 quantity. Type-specific fields for Cottage, Villa, Apartment reuse this same styled unit-entry component.

## Screenshot consistency requirements

The Starter, Business and Ultra dashboard views use ONE component library with controlled plan differences, never unrelated redesigned pages. Plan access is separate from current "Website Management free" and "Restaurant & Bar Management currently free" incremental module fees. Avoid showing Bar to unentitled plans or promising unlimited restaurant features when commercial scope remains open.

Visual QA before each Figma review: compare screenshot sidebar width, header geometry, typography hierarchy, selected red/nav colors, four-card KPI styling, card corner/border/shadow and button spacing. Clickable paths must work with local prototype state; Figma Make does not create real tenancy security, billing, OTA connections or production operations.

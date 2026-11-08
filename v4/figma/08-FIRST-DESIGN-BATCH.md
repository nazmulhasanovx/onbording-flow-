# 08 — First Figma Make Design Batch: Screenshot-Matched Foundation & Owner Entry

**Status:** Ready for design review (not yet created in Figma). Attach 3 user-provided BinGi dashboard screenshots, then paste [00 Base Prompt](00-BASE-SYSTEM-PROMPT.md) plus [07 Visual Reference](07-SCREENSHOT-VISUAL-SYSTEM.md) and THIS packet into Figma Make.

## Goals

Create the coherent **BinGi Pearl Light** design system matching the three screenshots, then build only the first onboarding screens. Do not design all modules or duplicate a hundred boards.

## Part A: shared components / component library

1. Header: BinGi logo/brand, property draft context, Help/Language/Save & Exit, consistent heights.
2. Onboarding sidebar: six section labels, active red row, completed checkmark, future section muted, clear progress; no preapproval live HMS modules.
3. Selected type cards Room/Cottage/Villa/Apartment; same visual grammar as KPI cards with soft colors and white icon tile but no excessive shadows.
4. Property input fields/selects, contextual explanation, inline errors, optional markers.
5. Step indicators and sticky bottom navigation: Back left, Save Draft, Continue primary right, same placement every screen.
6. Buttons/icon controls: screenshot-red primary, white outline secondary, navy utility action; loading/disabled states.
7. Gallery/cover/reorder component from Airbnb UX but visibly BinGi style.
8. Guided one-at-a-time Unit Register with saved list, Save & Add Next, duplicate error, category/location reuse; **NO Bulk Create button**.
9. Cards, summary/KPI cards, table rows/pills, quote breakdown, approval status. Only design component examples; full dashboard pages belong in later batch.

## Part B: screens (keep frame IDs)
- AUTH-01 Login/Register + verification demo.
- OWN-00 My authorized properties (resume draft, review status, new).
- P01-01 Property Name/Type/Contact (guided).
- P01-02 Property Address/Location.
- P01-03 Select types: Room/Cottage/Villa/Apartment (multi-select).
- P01-04 Preliminary Starter/Business/Ultra selection (current per-room prices and min quantity, no payment).
- P01-05 Basic operating defaults and saved profile review.

## Exact clickable prototype

AUTH-01 -> OWN-00 -> P01-01 -> P01-02 -> P01-03 -> P01-04 -> P01-05 -> "Accommodation Setup Next" placeholder. Back, Continue, Save & Exit and change type should preserve local data. Multi-select 0 types error; Q<10 gives min-billable explanation (not a fake physical inventory); property picker isolates the two dummy properties.

## Visual acceptance
- White/near-white screenshot look and red active/primary treatment, not generic blue SaaS.
- Sidebar/header proportions align with dashboard reference.
- Consistent layout for Starter/Business/Ultra, differences are only entitlements/content.
- Short form panels; one task at a time, no excessive padding or oversized typography.
- Mobile 390px one-column flow and desktop 1440px. Long Bangla text does not break buttons.
- Hand off editable components, frame IDs, short interaction flow and any unapproved commercial decisions; no production actions.

**Stop after this batch. Review the design with the owner before creating Room onboarding P02 screens.**

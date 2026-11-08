# 15 — Global Appearance Settings (APP-01)

**Date:** 2026-11-08 | **Status:** Design plan based on uploaded BinGi F-07 Appearance screenshot + Starter/Business/Ultra screenshot sidebar behavior. **1 screen, 6 settings controls**. This is ONE shared appearance route across active plans, NOT one screen per plan.

## Six controls

| Setting | Values | Default proposed | Shared effect |
|---|---|---|---|
| 1. Interface Scale | 90%, 100%, 112%, 125%, 140% | 100% | Sizes typography, controls and spacing without overlaps |
| 2. Density | Comfortable / Compact | Comfortable | Cards, tables, forms, rows; consistent functional positions |
| 3. Language | বাংলা / English | Saved user preference; fallback English | All shared labels, validation, help and navigation |
| 4. Numeral Display | ১২৩ / 123 | Saved user preference; fallback 123 | Human-readable counts and amounts, not canonical stored IDs |
| 5. Motion / Effects | Full effects / Lite effects | Full subject to reduced-motion override | Animations, transition and skeleton behavior; Lite avoids heavy effects |
| 6. Navigation | Flat / Expandable | Flat as pictured | Sidebar groups only; no data or permission change |

**Pearl Light** is the V1 visual theme. This screenshot does NOT authorize a Dark theme switch, so do not invent a seventh Appearance control. Browser-level zoom is separate from app Interface Scale; test both. Language/numeral settings do not mutate Room Unit IDs, booking references or invoice data: canonical identifiers stay unchanged.

## Foundation-first token registry

Official screenshot F-01 visual values (prefer over previously estimated screenshot seed; still check against original Figma variables on implementation):

| Token | Value |
|---|---|
| brand.logo | `#FD413F` |
| brand.action | `#C8232E` |
| brand.hover | `#B11C29` |
| brand.pressed | `#8F1520` |
| canvas | `#EEEAF6` |
| surface | `#FFFFFF` |
| ink / heading | `#1D1A24` |
| body | `#433F4B` |
| muted | `#665F6E` |
| border | `#E6E1EC` |
| soft | `#F1EEF4` |
| peach | `#FFF1E6` |
| lavender | `#ECE8FF` |
| mint | `#E3F7EE` |
| butter | `#FFF7D6` |
| sky | `#E8F1FF` |
| rose | `#FFECED` |
| violet | `#6D5BD0` |
| lime | `#D6F03C` |
| teal | `#14B8A6` |
| amber | `#F59E0B` |

Do not use invented gray or unrelated blue primary for new onboarding. Focus on contrast and actual screenshot tokens. The prior V4 visual page contains approximate values from dashboard screenshots; **this Foundation screenshot is higher-priority for exact tokens**, while dashboard screenshots still govern shell composition and metric cards.

## APP-01 screen structure

```text
HMS Header: [Property] [Search] [Language] [Avatar]
Left Sidebar: Dashboard/Settings (plan appropriate)
Main: Settings -> Appearance
  Header: Appearance / "Make BinGi comfortable for your team"
  [Interface Scale] 90 100 112 125 140
  [Density] Comfortable / Compact
  [Language] বাংলা / English
  [Numerals] ১২৩ / 123
  [Motion] Full effects / Lite effects
  [Sidebar] Flat / Expandable
  Live Sample: 4 KPI tiles + booking table + wizard controls
  Save / Reset to Defaults
Back to HMS Dashboard
```

Prefer immediate local preview and explicit Save for persistent preference changes. Changing language or scale must not lose unsaved hotel changes; prompt before a disruptive reload if needed. Every preference is per authorized user (NOT a property-wide operational policy), persist for next sessions as actual implementation work. Staff permissions, subscription access and booking data are unaffected.

## QA matrix

- UI scale all five values incl. 140% at desktop 1440, tablet 1024 and phone 390; no clipping of Back/Continue or status pills.
- Density toggles rows and spacing but keeps all actions and meaning available.
- Bangla and English switch without content truncation; font fallbacks available.
- ১২৩/123 changes visible formatted quantities but stored 101, V03, TA-101 and booking reference IDs do not change.
- Lite and OS reduced-motion avoid heavy animation; skeleton/loading remains accessible.
- Flat/Expandable sidebar changes arrangement only, keeps plan-gated modules and settings discoverable.
- Owner/admin appearance preference stays independent of Property A/B operational settings.
- Plan Starter/Business/Ultra dashboards use SAME APP-01; no triplicated Appearance frame.

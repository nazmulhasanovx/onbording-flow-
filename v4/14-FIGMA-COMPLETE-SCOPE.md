# 14 — Figma Full Delivery Scope: Registration to Dashboard

**2026-11-08 | Proposed design plan, NOT implemented.** Review/edit this screen budget before each Figma Make packet. This is the current screen-count source of truth; root V3 and prior V4 packets are references.

## Exact count, no double counting

| Block | Unique IDs | Count |
|---|---|---:|
| Register / verify / property picker | AUTH-01, OWN-00 | 2 |
| Your Property / preliminary plan | P01-01 through P01-05 | 5 |
| Smart accommodations | P02-01 through P02-09 | 9 |
| Rates and existing bookings | P03-01 through P03-03 | 3 |
| Plan-enabled operations | P04-01 through P04-03 | 3 |
| Guest payments and draft website | P05-01 through P05-03 | 3 |
| Subscription/training/KYC/final review | P06-01 through P06-04 | 4 |
| Submitted property / owner preview | WAIT-01, PREV-01 | 2 |
| Activated HMS | HMS-01 | 1 |
| Appearance Settings | APP-01 | 1 |
| **OWNER TOTAL** | | **33** |
| Super Admin | ADM-01 through ADM-03 | 3 |
| **ALL UNIQUE SCREENS** | | **36** |

**Important:** one UI template can have multiple states. AUTH-01 includes register/login/verify; HMS-01 has Starter/Business/Ultra variants. Nine P02 templates are reused by Room/Cottage/Villa/Apartment. Additional modal, drawer, confirmation, empty, loading, errors, keyboard view and mobile are states/components, not new unique route IDs. **Current requirement: no Bulk Unit Creation**. Each Unit Number is saved individually with Save & Add Next.

## 14 independent Figma Make design prompts

| Prompt | Scope | New unique screens |
|---|---|---:|
| 01 | Reuse Foundation & Appearance | 1 |
| 02 | Registration & Authorized Property Picker | 2 |
| 03 | Property Profile & Initial Plan | 5 |
| 04 | Shared Accommodation Engine: Room First | 9 |
| 05 | Cottage Type Adaptation | 0 |
| 06 | Villa Type Adaptation | 0 |
| 07 | Apartment Type Adaptation | 0 |
| 08 | Rates & Booking Readiness | 3 |
| 09 | Starter/Business/Ultra Relevant Operations | 3 |
| 10 | Guest Payments & Website Draft | 3 |
| 11 | Pricing, Training, Verification & Final Review | 4 |
| 12 | Approval Status & Read-only Owner Preview | 2 |
| 13 | Activated HMS Dashboard | 1 |
| 14 | Super Admin Review & Pricing Console | 3 |
| **TOTAL** | **14 prompts** | **36** |

**Owner/core:** 13 prompts covering the foundation, registration, onboarding, approval, activated plan dashboards and Appearance. **Separate administration:** Prompt 14 with 3 screens.

## Screen and data journey
```text
Prompt 01 Foundation reused + APP-01 Appearance (settings route after approval)
Prompt 02 AUTH-01 -> OWN-00
Prompt 03 P01-01..05 (Property Basics / Types / preliminary Plan)
Prompt 04 P02-01..09 (shared engine, first complete Room variant)
Prompt 05 P02-xx Cottage component variant ONLY
Prompt 06 P02-xx Villa component variant ONLY
Prompt 07 P02-xx Apartment component variant ONLY
Prompt 08 P03-01..03 Rates -> Reservations -> readiness
Prompt 09 P04-01..03 Plan-entitled operations
Prompt 10 P05-01..03 Website / Guest Payments (draft)
Prompt 11 P06-01..04 Commercial quote / Training / Verification / Submit
Prompt 12 WAIT-01 -> PREV-01, correction loops
Prompt 13 HMS-01 Starter / Business / Ultra, one shared dashboard
  Settings -> APP-01 -> Dashboard
Prompt 14 ADM-01..03 (separate administrative interface)
```

## Visual source precedence
1. New user-provided Figma F-01..F-07 Foundation (tokens/icons/components/templates/appearance), use EXACT values where visible. **Do not rebuild existing Foundation as unrelated pages.**
2. User's three Starter/Business/Ultra dashboard screenshots as layout and plan-variant baseline.
3. Airbnb amenities/photography images only for **one-focused-task, selectable amenity cards, cover/reorder, Save & Exit** UX patterns, never direct visual copying.
4. Earlier [Foundation GitHub](https://github.com/nazmulhasanovx/BINGI-FOUNDATION-UI-and-UX) for specifications not pictured; reconcile rather than silently switching colors.

## Component work already represented by Foundation, NOT billable screen count
F-01 color/typography tokens; F-02 Icons; F-03/04/05 shared components; F-06 Page Templates; F-07 Appearance demo. Desktop/Table/Phone shells, Plan Matrix, responsive Switchers/Panels, Motion, Surface & Light stay reusable foundations and examples. Their existing frame count is not included in these 36 new route-template estimates.

## Product safety & scope
No plan-based UI may grant backend entitlements; no other property data, no fake real Rooms, no hidden subscription charges, no premature public publishing. Group one task per onboarding panel under 6 progress sections; all real room/cottage/villa/apartment units entered one by one; subscription min billable 10 must not fabricate real inventory. Four accommodation variants + three plan variants share a common library.

## Deliverable definition
Each prompt yields Figma editable components + frame variants + working clickable primary and exception paths, responsive checks, error/empty/loading states and stable IDs. No backend engineering or deployment is included. Owner reviews each before next; log changes in [Decisions](11-DECISIONS-REGISTER.md) and [QA](10-QA-ACCEPTANCE.md).

**Entry point:** [14 Figma Make Prompt Index](figma/prompt-series/README.md) · [Appearance Rules](15-APPEARANCE-SETTINGS.md) · [Original Screen Registry](06-SCREEN-REGISTRY.md).

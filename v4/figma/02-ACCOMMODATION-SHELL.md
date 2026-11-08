# 02 — Figma Make Packet: Smart Accommodation Component System
Design status: batch 2 common shell, review BEFORE applying four type variants. Paste after [Base Prompt](00-BASE-SYSTEM-PROMPT.md). Scope P02-01 through P02-09 only.

## Purpose
Build ONE reusable Accommodation engine and wizard components, not Room/Cottage/Villa/Apartment as four unrelated apps. Keep common stage logic Type -> Category -> Location & Units -> Details/Pricing -> Review/Create. Short UI task panels under logical stage 2 are permitted.

## Screens and components
**P02-01 / Setup preview**: saved four type toggles from section 1, recommendations for Room Building>Floor, Cottage/Villa Zone>Optional Block, Apartment Tower>Floor. "Accept Recommended" and "Customize" actions; reuse property profile data, never retype it.
**P02-02 / Structure and numbering setup**: property-scoped location node tree; create/reuse Buildings, Towers, Floors, Zones, Blocks. Per-type strategy picker, prefix/padding/separator/sequence rule and live examples. Show first floor 101..199, second 201..299 as suggestions, NOT rigid assumption; handle 100+ levels and nonconsecutive IDs. Hidden Block for a Cottage/Villa property with none.
**P02-03 / Inventory workspace**: four filters according to enabled types, category cards, total physical Unit counts and configured vs billable Q summary (tentative), + New Accommodation, Add Category, View Existing; empty state. Room-only property navigation label Rooms, mixed property Accommodations.
**P02-04 / Wizard: type + category**: choose enabled type; existing saved category fast path versus Create New. Include recommended simple category names.
**P02-05 / Wizard: category details**: name, style/config, adults/children, bed types/count, bathrooms/size; type adapters render only applicable fields; clearly separate bedrooms (subspaces) from physical Unit.
**P02-06 / Wizard: media & description**: category photos upload placeholders, reorder, set cover, photo-only valid; optional YouTube link, select up to 3 highlights and editable suggested description, preserved on Back.
**P02-07 / Guided Unit Entry**: one real Unit Number input with saved Category and Location; Save & Add Next validates/saves ONE draft Unit, keeps context, clears number only. Saved Unit list with precise count, Edit/Remove draft and duplicate/quota errors; final Save & Review. No range, count generator or mass-create button.
**P02-08 / Wizard: details and pricing**: category nightly base rate, unit overrides only when expanded; operational state; policy inheritance. Avoid 40 identical per-unit forms.
**P02-09 / Wizard: review/create**: show actual category, location path and exact unit IDs, count and derived states, Save Draft vs Create; successful return to P02-03 with "Add another category" and "Continue to Bookings".
 
## Component variant strategy
Create shared "Type Card", "Location Node", "Category Summary", "Bed Layout", "Gallery", "Unit Number Chip", "Price Field", "Unit Table", "Error Summary", "Wizard Footer", "Review Dialog". Variation by type controls fields, labels and hierarchy; never vary button placement or fonts.

## Links to variants
[Room](02A-ROOM.md), [Cottage](02B-COTTAGE.md), [Villa](02C-VILLA.md), [Apartment](02D-APARTMENT.md). Review Room first as baseline, then adapt three variants; mixed property can enable multiple types.

## Required interactions
Accept/Customize preset, create location, existing category select, show/hide conditional fields, add/remove number chips, reject duplicate, show capacity warning, individually saved Unit list, Back/Continue persistence, Save Draft, success summary. Stable CTA spots; no backend claims.

## Demo & error state
Deluxe Twin on Main Building/Floor 1; Save 101, then 103, then 105 individually = exactly 3 draft Units. Try 103 again -> inline duplicate error, do not pretend overwrite. Another owner property location must never appear. All media optional except where later channel-specific publishing rule requires it.

## Completion
Common shell + P02-01..09 interactive flow before any type-specific independent style exploration. Do NOT rebuild login/plan/HRM inside this packet.

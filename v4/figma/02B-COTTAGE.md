# 02B — Figma Make: COTTAGE (Second Individual Review)
Status: review draft. Follow [Room](02A-ROOM.md) approval and reuse SAME [P02 shared shell](02-ACCOMMODATION-SHELL.md). Do not re-create all components.

## Cottage-specific difference
Property: Azure Bay Demo Resort; Cottage selected. Recommended hierarchy Zone/Area > Optional Block. Existing Garden Zone and Lake Zone; no Blocks initially -> **Block selector is hidden**, not disabled. Cottage internal floors/levels, bedrooms and bathrooms are details, NOT Hotel floor hierarchy. Whole Cottage is ONE physical Unit and one bookable item.

## Figma frames and flow
~~~text
P02-01 / Cottage / Preset Zone>Optional Block
 -> P02-02 / Cottage / Garden & Lake zones (reused from property tree)
 -> P02-04 / Cottage / choose existing or create "Garden Family Cottage"
 -> P02-05 / Cottage / bedrooms, beds, bathrooms, internal levels optional
 -> P02-06 / Cottage / category gallery, Garden View highlight, editable description
 -> P02-07 / Cottage / Zone Garden / no Block / choose C01,C03
 -> P02-08 / Cottage / nightly whole-Cottage rate and optional notes
 -> P02-09 / Cottage / EXACT 2 Cottage Units -> Create
 -> P02-03 / mixed Accommodation workspace
~~~

## Interaction requirements
- If only Garden Zone exists, auto-select. If two Zones, show clear Zone cards.
- Optional "Does your property use Blocks?" No -> no Block dropdown; Yes -> choose existing Block or add within zone.
- Numbering C01,C03 is valid; G-C01 or A-C01 optional configured prefix for collision safety, not mandatory.
- Bedrooms do not increase subscription inventory count.
- Returning flow: Cottage -> existing Garden Family Cottage -> saved Garden Zone -> choose C05,C06 -> review/create; no repeated gallery/rate/bed questions.
- Category photo and optional video can be inherited; unit overrides are in advanced collapsible panel.

## Test state
Try duplicate C03 in Lake Zone with a property-wide C03 code; warn and offer unique prefix/re-number, no overwrite. Hide floor field always unless a deliberately configured valid alternate strategy (do not imply standard Cottage needs floors).

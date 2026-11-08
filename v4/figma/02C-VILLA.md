# 02C — Figma Make: VILLA (Third Individual Review)
Status: review draft. Reuse the Room/Cottage approved components, maintain six-section shell and identical wizard CTA positions.

## Villa-specific concept
One Private Pool Villa with two or more bedrooms is **ONE sellable physical Unit**. Property uses Beachfront Zone and Garden Zone, optional Blocks. Recommended display IDs V01, V03, BF-V01. Do not treat internal levels as Hotel Floors.

## Clickable story
~~~text
P02-01 / Villa / Zone>Optional Block preset
 -> P02-02 / Villa / saved Beachfront Zone, optional Block A
 -> P02-04 / Villa / New "Private Pool Villa" category
 -> P02-05 / Villa / 2 bedrooms:
       bedroom 1: King bed x1
       bedroom 2: Single bed x2
       2 baths, max occupancy, optional pool/kitchen/living
 -> P02-06 / Villa / photos, cover, Private Pool + Spacious highlights, video optional
 -> P02-07 / Villa / Beachfront Zone -> choose V01,V03
 -> P02-08 / Villa / whole Villa/night rate; optional unit pool/view exceptions
 -> P02-09 / Villa / EXACT 2 whole Villas, NOT 4 bedrooms as units
 -> P02-03 / Villa inventory summary
~~~

## Variants and error handling
- Private Pool feature switch controls subordinate pool details only; don't force pool for all Villas.
- Internal level count should NOT trigger floor number or new Unit creation.
- If Villa V01 booked, editing category/location displays impact preview and support escalation path.
- Unit media override may replace/hide category media to avoid misleading images for different pool/view conditions.
- Returning Villa add uses existing category, zone and new IDs only.
- Correct status labels: unit active vs occupied on a date vs published channel are separate.

## Review tests
First-time and returning creation, V01/V03 gaps, blocked V01 duplicate, two-bedrooms count=one Unit, conditional pool and optional Block. No independent per-bedroom booking screens.

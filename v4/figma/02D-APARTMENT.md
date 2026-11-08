# 02D — Figma Make: APARTMENT (Fourth Individual Review)
Status: review draft. Design with identical shared P02 shell and footer.

## Apartment-specific concept
Apartment Category may be Studio, One Bedroom, Two Bedroom or Family Apartment. Recommended location Tower/Building > Floor. 2-bedroom Apartment is ONE physical sellable Unit, not two rooms. Studio has 0 separate bedrooms but a sleeping arrangement.

## Clickable path
~~~text
P02-01 / Apartment / Tower>Floor preset
 -> P02-02 / Apartment / saved Tower A and Tower B, each has Floor 1
 -> P02-04 / Apartment / New "Two Bedroom Apartment" category
 -> P02-05 / Apartment / bedrooms, beds, bathrooms; kitchen/living/balcony conditional
 -> P02-06 / Apartment / photo cover, Spacious highlight, editable description
 -> P02-07 / Apartment / Tower A Floor 1, Save TA-101 then Save TA-103 individually
 -> P02-08 / Apartment / whole-Apartment nightly rate, optional unit view
 -> P02-09 / Apartment / Review EXACT 2 physical Apartments -> Create
 -> P02-03 / Apartment inventory and type filter
~~~

## Two special cases
1. **Studio variant**: "Studio Apartment" has no separate bedroom; bed x1 in main space valid. Do not display red invalid state just because separate bedrooms=0.
2. **Tower collision**: Tower A / Floor 1 / 101 and Tower B / Floor 1 / 101 must either become TA-101 and TB-101 or be rejected by property-wide duplicate code policy. Do not claim both are the same displayed "101" if property-wide uniqueness applies.

## Core interactions
- Tower/Floor choices limited to this property's saved tree; one tower auto-selected only if unique.
- Apartment 201,203 or TA-201,TA-203 supported as nonconsecutive.
- Conditional kitchen, balcony, living fields hidden when absent. Inside Apartment bedrooms are descriptive subspaces, not separately bookable.
- Existing booked Apartment cannot be moved/re-identified without conflict review; no silent data loss.
- Returning flow: Existing 2BR category -> Tower A/Floor 2 -> Save TA-201, then TA-203 individually -> Review.

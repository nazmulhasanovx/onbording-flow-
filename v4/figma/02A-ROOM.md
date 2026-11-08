# 02A — Figma Make: ROOM (First Individual Review)
Status: Room flow review draft; append to [Base Prompt](00-BASE-SYSTEM-PROMPT.md) after first implementing [Shared Accommodation Shell](02-ACCOMMODATION-SHELL.md).

## Objective
Demonstrate ONE Room category creation and three physical room IDs through existing shared P02 screens. Focus on effortless first-time setup and fast return. Frame names use same P02 IDs with suffix "Room".

## Room-specific scenario
Property: Azure Bay Demo Resort; enabled Room and Cottage; saved Main Building; Floor 1 and Floor 2. First-time Room template suggests Building>Floor, 1st floor units 101–199 and 2nd floor 201–299; owner can customize. Category "Deluxe Twin", 2 single beds, 2 guests, default price example ৳5,000/night. No extra property-wide currency/timezone fields; pull from property defaults.

## Frames and click path
~~~text
P02-01 / Room / Preset
 -> P02-02 / Room / Main Building & Floors (accept or customize)
 -> P02-03 / Rooms/Accommodations / empty
 -> P02-04 / Room / New Deluxe Twin Category
 -> P02-05 / Room / Twin Beds & Occupancy
 -> P02-06 / Room / Gallery Cover & Highlights
 -> P02-07 / Room / Floor 1 / select [101,103,105]
 -> P02-08 / Room / Price + optional room notes
 -> P02-09 / Room / Review exactly 3 -> Create
 -> P02-03 / Room / 3 units saved
 -> repeat fast flow: Existing Deluxe Twin -> Floor 2 -> [201,203] -> Review
~~~

## Distinct Room UI requirements
- On Floor selector, if one building exists auto-select Main; if multiple show Building select; if category floorless strategy configured do not force Floor.
- Room 101 and Room 103 remain separate one-unit bookables; skipping 102 is valid.
- Bulk unit builder shows exact selected list. If 103 already exists, show "Room 103 already exists in this property" without silently saving a partial batch.
- Later numbering rules/Building name edits with existing booked rooms show impact warning, not immediate destructive changes.
- Optional room view/accessible amenities flags; never equate Suite bedroom count to physical Unit count.
- Display dynamic sidebar label "Accommodations" if Cottage also enabled; "Rooms" for Room-only property.

## Review checkpoints
Owner should be able to answer: What building? What floor? Which category? Which exact room numbers? How much per room-night? Which photos? Can I reuse my category? Each question should take minimal clicks.
No KYC, subscription payment, OTA or standalone full HMS dashboard built in this Room packet.

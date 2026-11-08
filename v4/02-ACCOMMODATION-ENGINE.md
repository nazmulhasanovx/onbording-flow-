# 02 — Smart Accommodation Engine
Status: V4 proposal grounded in approved Accommodation repository; four priority types only.

## Inheritance hierarchy
~~~text
PROPERTY -> Accommodation Configuration (once)
   -> enabled types: Room / Cottage / Villa / Apartment (multi-select)
   -> saved nodes: Building, Tower, Floor, Zone, Block
   -> saved type/category location strategy and numbering policy
   -> Category (templates: capacity, beds, photos, amenities, video, base rate)
   -> Physical Unit (exact ID, location, operational state, optional overrides)
   -> Dated availability, restrictions and reservations
~~~
Category templates avoid repeated fields; existing category -> saved path -> chosen numbers -> review is repeat fast path.

## Four type adapters
| Type | Recommended location | Category conditional questions | Example IDs |
|---|---|---|---|
| ROOM | Building > Floor (floorless strategy allowed if genuinely relevant) | bed configuration, occupancy, size, baths, view | 101, 103, MAIN-101 |
| COTTAGE | Zone/Area > optional Block | bedrooms, beds, bathrooms, internal levels descriptive, view | C01, C03, G-C01 |
| VILLA | Zone/Area > optional Block | bedrooms+per-bedroom beds, optional pool, kitchen/living/internal levels | V01, V03, BF-V01 |
| APARTMENT | Building/Tower > Floor | studio/1BR/2BR, kitchen/living/balcony, beds; Studio allows 0 separate bedrooms | TA-101, TA-103 |

**Same Property can enable all four**. Property Type and Accommodation Type are different. Cottage/Villa internal floors and multiple bedrooms do not create additional physical units. One entire Room/Cottage/Villa/Apartment = one whole sellable inventory unit in first release. Counting these equally for subscription is recommended but needs commercial approval.

## First-time location configuration
~~~text
Enable Type -> Show recommended strategy and example
 -> "Does your property use this structure?" Yes (quick accept) / Customize
 -> Reuse existing nodes under THIS property
 -> Add only missing building/tower/floor/zone/block nodes
 -> Save naming & numbering policy (prefix, pad, scope, separator)
 -> Preview examples against real locations
 -> Confirm once
~~~
If a type doesn't use Block, hide Block, not disabled clutter. One valid building/zone can auto-select. For floor 1 recommend 101–199, floor 2 201–299; numbering is configurable and 100+ floors must work. Distinguish display Unit Code (property-unique) vs immutable internal unit_id. Concurrency-safe uniqueness on server; never force consecutive IDs.

## Common logical 5-stage wizard / focused UI tasks
~~~text
1 TYPE             choose one of enabled Room/Cottage/Villa/Apartment
2 CATEGORY         existing/new -> category identity, occupancy/beds/features
                   -> category gallery: upload/reorder/cover
                   -> optional YouTube Video Tour
                   -> choose <=3 supported highlights -> editable description
                   -> default rate (per entire unit)
3 LOCATION & UNITS choose saved applicable location
                   -> number builder: generate / range / manual / select
                   -> exact preview; skip taken codes; capacity warnings
4 DETAILS/PRICE    inherit category defaults; unit-specific exceptions optional
5 REVIEW/CREATE    preview category + physical unit count + IDs + states
                   -> Save Draft / Create; do not auto-publish publicly
~~~
The five stages are logical steps; Figma may split Category into focused panels while keeping stable progress and Back/Continue.

## Bulk add and return path
~~~text
Room -> Deluxe Twin -> Main/Floor 1 -> choose [101,103,105] -> create 3
Cottage -> Garden Cottage -> Garden Zone -> [C01,C03] -> create 2
Villa -> Pool Villa -> Beachfront Zone -> [V01,V03] -> create 2
Apartment -> 2BR -> Tower A/Floor 1 -> [TA-101,TA-103] -> create 2
Returning -> existing category/location auto -> new IDs only -> confirm
~~~

## States and safety
- Category DRAFT vs READY; unit Active/Inactive/Out of Service; listing Draft/Published; date-wise Available/Occupied/Blocked: different fields.
- Reservation overlap and maintenance block checks before operational booking readiness. Validate server-side transactionally, including concurrent bulk creation.
- If unit is booked, changing ID, category or location needs impact warning/controlled migration; never delete historical bookings.
- Gallery inherited from category; unit-level replace/hide possible; do not misrepresent unit-specific photos on category bookings.
- File/YouTube URLs validated, optional video never required; alt text and cover cropping reviewed.
- Guest-side UI label "Stays"; HMS nav dynamic Rooms only if exclusively Room else "Accommodations". These are already approved architecture concepts; avoid breaking existing API routes.
- Dormitory separate bed-level later; Other/Custom explicitly deferred.

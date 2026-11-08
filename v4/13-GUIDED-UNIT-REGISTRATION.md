# 13 — Guided Unit Registration (Latest Owner Decision)

**Status:** Owner's latest direction; onboarding must **NOT** automatically create Units in bulk.  
**Date:** 2026-11-08. **Scope:** Room, Cottage, Villa and Apartment in one property-specific onboarding journey.  
**Supersedes:** Earlier V4 auto-generation/range/bulk-create proposals. Root-level older documents are historical drafts.

## Principle

**Configure once → Add actual Units clearly, one by one → Review once.**

Onboarding is the Owner documenting real inventory—not generating virtual Rooms. Building/Floor/Zone/Block, numbering rules, and Category details must be saved once. Then each new actual Unit needs only its unique number and any genuine Unit-specific exception. The user must never recreate the entire wizard for each Room.

## Full flow

```text
REGISTER ACCOUNT ONCE
  -> CREATE PROPERTY DRAFT (unique property_id)
  -> Enter Property Profile / select real Accommodation Types
  -> ACCEPT / CUSTOMIZE LOCATION & NUMBERING PRESET ONCE
  -> CREATE / SELECT CATEGORY ONCE
     Deluxe Twin / Garden Cottage / Pool Villa / Two-Bedroom Apartment
     Save occupancy, beds, photos, amenities, optional YouTube tour, default rate
  -> GUIDED UNIT REGISTRATION
     Show chosen property / type / category / saved location
     Input: Unit Number [101] -> [Save & Add Next]
       Server validates and saves **ONE DRAFT UNIT**
       Show Room 101 in saved list
       Keep Category, Floor and all inherited details
     Input: Unit Number [103] -> [Save & Add Next]
       Save only Room 103; no Room 102 generated
     Input: Unit Number [105] -> [Save & Review]
       Save only Room 105; no Room 104 generated
  -> REVIEW EXISTING DRAFT UNITS: 101, 103, 105, EXACTLY 3
     Edit mistake / Remove unbooked draft / Add Next / Confirm
  -> Booking rates, availability, existing reservations and applicable operations
  -> Review commercial quote and required verification
  -> Submit Property -> BinGi approval -> HMS Dashboard if approved/activated
```

## Four adapters — one shared screen

| Type | Reused location context | Sequential IDs | Inventory |
|---|---|---|---|
| Room | Main Building → Floor 1 | 101, 103, 105 | 3 actual Rooms |
| Cottage | Garden Zone → optional Block | C01, C03 | 2 whole Cottages |
| Villa | Beachfront Zone → optional Block | V01, V03 | 2 whole Villas |
| Apartment | Tower A → Floor 1 | TA-101, TA-103 | 2 whole Apartments |

Internal Villa/Apartment bedrooms do not count as separate bookable Units. Cottage/Villa Floor selector is not mandatory. Room/Apartment Floor locations and property-wide code uniqueness must be validated.

## P02-07 — Guided Unit Entry screen

- Context: current authorized Property, Accommodation Type, saved Category and Location.
- One Unit Number input; editable suggested next number is a hint ONLY, never auto-saved.
- **Save & Add Next** validates/saves one actual DRAFT Unit, retains Category/Location, clears only number.
- **Save & Review** saves the current one and navigates to P02-09.
- Saved Unit list underneath with exact count, Edit / Remove *draft* (not booked live records).
- If unit location changes mid-entry, previous units keep their saved locations.
- Errors: duplicate code, location mismatch, unsafe number, plan quota, connection retry. Failed save retains input and must not create duplicates.
- Separate **actual physical count** from **minimum billable quantity 10** (specific accounting still pending policy approval).
- No **Create 30**, **Generate N**, **select range and bulk-create**, or hidden one-click mass creation on onboarding.
- Support keyboard Enter and fast focus for repetitive entry; owner should never retype beds, currency, price, building or category.

## P02-09 — Final Review

Show only actually saved draft Units, their locations and rate inheritance; Owner confirms before continuing. Drafts never become bookable merely because added. Approval, activation, website publishing and booking readiness remain independent.

## QA

1. Save 101 → one Unit; Save 103 → two; Save 105 → three; gaps 102/104 remain absent.
2. Duplicate 103 shows error; previous saved 103 unchanged, input retained.
3. Switch Floor, save 201; existing 101/103/105 remain on Floor 1.
4. Returning Add uses saved Category and Location with no repeated configuration.
5. Simultaneous owners saving same code result in one valid Unit, not duplicates.
6. Unit belonging to Property B cannot be accessed or saved into Property A.
7. 2BR Villa V01 = one physical Unit.
8. Q=10 minimum billable does not create 10 fake units where physical units fewer.
9. One failed network save can be safely retried without duplication.
10. Onboarding Figma prototype contains no Bulk Unit Creation button.

**Future optional import/tools** may be separately researched for large properties after onboarding approval; they are **not in this V4 owner-facing onboarding scope**.

See: [Accommodation Engine](02-ACCOMMODATION-ENGINE.md) · [Screen Registry](06-SCREEN-REGISTRY.md) · [Figma Shell](figma/02-ACCOMMODATION-SHELL.md).

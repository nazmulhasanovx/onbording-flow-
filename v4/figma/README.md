# Figma Make — BinGi HMS V4 Work Packets
**Use one file / one batch at a time.** This is a handoff for Figma Make; not a request to render or publish automatically.

## First read
[MASTER FIGMA MAKE PROMPT](00-BASE-SYSTEM-PROMPT.md) + [V4 UI Foundation](../07-UI-FOUNDATION.md) + [Screen Registry](../06-SCREEN-REGISTRY.md).

## Recommended execution order
1. [01 — Property & Plan](01-PROPERTY-PLAN.md): registration, property identity, four type choice, preliminary plan.
2. [02 — Accommodation Common Shell](02-ACCOMMODATION-SHELL.md): reusable wizard + location/category/unit/gallery components.
3. [02A — Room](02A-ROOM.md): first type to approve.
4. [02B — Cottage](02B-COTTAGE.md): reuse the Room components, change location/content.
5. [02C — Villa](02C-VILLA.md): multi-bedroom but whole Villa inventory.
6. [02D — Apartment](02D-APARTMENT.md): Tower/Floor, studio and whole unit.
7. [03 — Bookings & Operations](03-BOOKINGS-OPERATIONS.md).
8. [04 — Digital, Commercial & Review](04-DIGITAL-BILLING-REVIEW.md).
9. [05 — Approval & Super Admin](05-APPROVAL-ADMIN.md).
10. [06 — Acceptance and Figma Handoff](06-FIGMA-CHECKLIST.md).

## HOW TO USE
Copy **00 base prompt** into the design task as the design rules, append ONE packet. Tell Figma Make: "Build only the screen IDs in this packet; clickable prototype with working local-state interactions is enough. Do not invent backend, authentication, payments, actual reservation processing or external integrations." Review components/frames and flow; update decisions before the next packet.

## Review order / rules
- User wants one-by-one review; **Room** first, then Cottage, Villa, Apartment. The first time, approve foundation shell then Room screens; only then duplicate/adapt templates.
- Frame names: "P02-07 / Room / Bulk Units / Valid", etc.
- Use realistic demo property data without real customer NID, trade license, personal address, payment details or copyrighted Airbnb layouts.
- The 6 owner sections, common 5-stage accommodation wizard, current pricing and approval contract come from V4 docs, NOT the earlier loose screenshots.
- If a commercial rule is unresolved, put it in a visible design note and use a reversible example, not a silently finalized price or promise.

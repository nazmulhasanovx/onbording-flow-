# 01 — Figma Make Packet: Register, Your Property & Preliminary Plan
Design status: batch 1. Paste after [Base Prompt](00-BASE-SYSTEM-PROMPT.md). Build ONLY listed IDs, editable components and clickable prototype. Source: [Owner Journey](../01-OWNER-JOURNEY.md), [Registry](../06-SCREEN-REGISTRY.md).

## Frames and exact UI tasks
**AUTH-01 / Register**: clean login/registration phone primary, optional email, secure password/Google if supported as UI placeholder, terms checkbox, verification step. Do not simulate verified auth or store real credentials. Fixed auth CTA, guide video optional. State: empty/invalid/pending/verified example.

**OWN-00 / My Properties**: list only authorized demo properties with their own statuses (e.g. "Azure Bay Demo Resort — Draft", "City View Hotel — Awaiting Review"), Resume/Edit Setup buttons; + New Property. Switching property changes all local state and plan context. Never offer other properties in selectors.

**P01-01 / Property basics**: simple "What is your property called?" then property type Hotel/Resort/Guest House/Serviced Apartment/etc, official phone/email and authorized operator. Make focused guided panels, not one 30-field form. Show optional logo. Required errors.

**P01-02 / Property location**: country, division/district/area cascading example, full address, optional pin/map placeholder. Avoid duplicating address during verification. Default Bangladesh demo but editable. Save local state.

**P01-03 / Accommodation types**: four selectable visual cards Room, Cottage, Villa, Apartment (multiple selection allowed); property type suggests initial selections but owner can change. On selection show "BinGi will prepare" preview: Room Building>Floor, Cottage/Villa Zone>optional Block, Apartment Tower>Floor. Nothing created before Owner confirms. At least one selection required.

**P01-04 / Preliminary plan**: Starter / Business / Ultra cards, monthly price per room (30/50/116), estimated Q stepper minimum 10 for quote display, note final Q adjusted after actual inventory, show available plan modules and current fee-free scopes without promising Bar feature access. Highlight per-unit counting policy remains review subject. Billing period optional preview; do NOT collect payment yet.

**P01-05 / Property-wide defaults**: condensed card with currency BDT, time zone Asia/Dhaka, check-in/out suggested editable, language, default booking/cancellation/tax settings link; confirm once. Show a summary preview of saved property context.

## UX and navigation prototype
~~~text
AUTH-01 -> OWN-00 -> P01-01 -> P01-02 -> P01-03 -> P01-04 -> P01-05
 -> P02-01 (next batch placeholder with label, NOT fake complete page)
~~~
Use six-section rail with Section 1 active. Each screen has same fixed Back / Save & Exit / Continue, section task title and progress. When going Back entered values remain. "Save & Exit" returns to OWN-00 with Draft status. Change property type does not clear rooms inadvertently; ask before removing enabled types that would affect saved work.

## Prototype data
New demo "Azure Bay Grand Resort" in Cox's Bazar; keep fake official contact placeholders, no real NID. Type selections initially Room+Cottage+Villa; show Apartment can be selected. Preselect Starter for demo only, do not assume valid plan for real owner.

## Required states for review
- No type selected error and recovery.
- P01-04 Q below 10 rejected/min-billing explanation (no extra fake physical rooms).
- Resume another property's draft shows isolated progress.
- Narrow viewport, labels in Bangla fit; Save fail retention and disabled loading CTA.

## Done criteria
All seven view IDs, consistent Pearl Light shell, prototype navigation, one complete happy path and two error paths. No unrelated booking screens built.

# 05 — Property Approval, Payment, Setup and Channel Statuses
Status: PRODUCT LIFECYCLE PROPOSAL; payment sequencing pending final commercial policy.

## Four distinct state machines
### Property onboarding
~~~text
DRAFT -> CONFIGURING -> READY_TO_SUBMIT -> SUBMITTED -> UNDER_REVIEW
 -> NEEDS_CHANGES -> CONFIGURING -> RESUBMITTED -> UNDER_REVIEW
 -> APPROVED | ON_HOLD | REJECTED
~~~
Must retain activity log, reviewer, reason, status timestamp, version; exact correction links. Sensitive verification docs accessible to authorized reviewers only.

### Subscription/commercial
~~~text
ESTIMATE -> QUOTED -> CUSTOMER_ACCEPTED
 -> [AWAITING_PAYMENT -> PAID -> ACTIVE] or CANCELED / EXPIRED
 -> RENEWAL / PAUSED / EXPIRED under final billing rules
~~~
Proposed sequencing: pre-approval accepted quote, then required payment after approval, then active. Alternate prepaid requires separately agreed refunds. Do not activate solely on either paid or approved flag.

### Setup/training service order
~~~text
NOT_SELECTED | QUOTED -> CUSTOMER_ACCEPTED -> AWAITING_PAYMENT (if chargeable)
 -> SCHEDULING -> SCHEDULED -> IN_PROGRESS -> TRAINING -> VERIFIED -> COMPLETED
 -> ON_HOLD/CANCELED as appropriate
~~~
Remote shifts and onsite visits are service records, not always mandatory to property approval. Onsite property provides meals/stay; travel/expense policy approval separate.

### Digital channel
~~~text
DRAFT -> CONTENT_READY -> TECHNICALLY_READY -> REVIEWED -> PUBLISHED
 -> PAUSED/UNPUBLISHED
~~~
Channels independently: Property Website, BinGi Marketplace, each supported OTA. No auto-live toggle in onboarding merely because property setup is complete.

## Access gates
- Draft/submitted owner: access their own onboarding, pricing/receipts, safe read-only property preview and corrections. No live HMS booking operations or public orders.
- Approval + applicable contract/payment requirements: unlock property HMS dashboard with authorized plan features. Staff/permission scope separately checked.
- Publishing needs content, rates, availability, inventory mappings, payment/communication readiness and channel approval as relevant.

## Operational readiness checklist
**Required, applicable:** valid contact/property; at least one configured physical Unit and category; valid rates; no conflicting existing active bookings or maintenance; accepted plan Q adequate under policy; essential booking policies and suitable guest payment mode; applicable legal verification; current quote accepted. If no existing bookings, explicit "None".
**Recommended:** full photos, staff invitations, optional service setup, category highlights, extra pricing.
**Optional:** custom domain, seasonal campaigns, SEO, OTA, menu bulk import, video tours, HRM payroll where not needed.

90% is a coverage target over *applicable* tasks; never block on skipped or plan-unavailable optional modules. Required checks must pass 100%. No fake "online booking ready" until per-channel validation.

## Review SLA
Internal review queue, reviewer assignment, oldest waiting and escalation indicators. No publicly promised specific approval turnaround until real capacity/service policy exists.

# 08 — Super Admin, Billing Console and Training Operations
Status: V4 draft; never conflate approving a property with silently charging a customer's card.

## Admin property review workflow
~~~text
QUEUE -> filter Pending/Resubmitted/Hold + sort aging
 -> Open property-scoped Review Detail
 -> Read required verified identity/business fields (restricted)
 -> Compare property type, address, plan and actual physical inventory
 -> Validate location numbering, categories, units, rate & existing booking conflict report
 -> Check customer accepted quotation and relevant commercial status
 -> Decision: Request changes (named issues) / Hold / Reject (reason) / Approve
 -> Audit actor, timestamp, property_id, decision and doc/version
~~~
Needs Changes should deep-link owner to the exact substep. Never reveal unrelated property data to owner or other hotel staff.

## Plans, promotions, entitlements
- Editable plan monthly per-unit prices: Starter 30; Business 50; Ultra 116 (working).
- Minimum billed Q 10 and custom count; cycle discounts 0/10/25% for 1/6/12 months.
- Business & Ultra activation standard 29,500; active waiver to 0, no invented expiry.
- Remote Team Training 500 per shift; current promo 0; discount per shift, limits/expiry unset.
- Onsite 12,500; property meals and stay responsibility; travel extras must be agreed.
- Website Management and eligible Restaurant & Bar have current incremental module fee zero; exact feature access/limits unresolved.
- Maintain commission rules if approved: marketplace 12/8/4%, website 1.5/1/0.5%, walk-in 0%.
- Every change: old/new value, effective_from, plan/version, who approved, impacted customers, customer notification, audit trail and no retroactive mutation of accepted invoices.

## Service order management
Status: Pending -> Awaiting Payment if applicable -> Payment Confirmed -> Scheduling -> Scheduled -> In Progress -> Training -> Verification -> Completed; On Hold/Cancelled as alternatives. Assigned representative, planned shifts/days, travel/meal/stay responsibilities, service notes, customer acceptance and proof of delivery. Optional training must not block onboarding if not contractually mandatory.

## Security + audit
Server-side role checks for admin vs owner, allow only explicitly permitted documents, encrypted sensitive ID handling and short-lived access. Don't put NID, bank numbers, personal home addresses, tokens, raw ID pictures into public GitHub files or Figma Make prompts. Test audit/history and dual-control approval for risky finance changes if adopted.

## Admin screen IDs
ADM-01 Review Queue/Detail; ADM-02 Plans, Promotions & Fee Rules; ADM-03 Training Service Orders. Keep admin UI separate from owner onboarding navigation.

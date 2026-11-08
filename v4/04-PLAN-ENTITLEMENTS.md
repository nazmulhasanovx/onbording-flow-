# 04 — Plan Modules and Feature Entitlements
Status: COMPILATION OF USER-STATED SCOPE + OPEN QUESTIONS. Feature matrix must be approved before implementation.

## User-stated baseline
Legend: Y = advertised feature; — = not advertised; ? = unresolved / do not guarantee.

| Feature | Starter | Business | Ultra |
|---|:---:|:---:|:---:|
| Room / Core Accommodation management | Y | Y | Y |
| Online / Offline bookings | Y | Y | Y |
| Website Management (currently no additional module fee) | Y | Y | Y |
| Website themes | Limited | Limited | Unlimited |
| Domain management capability | Y | Y | Y |
| Housekeeping | — | Y | Y |
| Expense Management | — | Y | Y* |
| Restaurant / Meal Management | — | Y | Y* |
| Restaurant menu capacity (prior matrix) | — | 20 | 500* |
| QR Food Ordering | — | Y | Y |
| Other Services | — | Y | Y |
| HRM full | — | — | Y |
| Inventory | — | — | Y |
| Advanced Operations | — | — | Y |
| Bar Management | ? | ? | ? |
| Basic Team Roles / staff invited for operations | core minimum ? | ? | Y |
| Payments / Cashbox / Finance exact scope | ? | ? | ? |

* Previous Business/Ultra feature scope carried forward pending confirmation. Latest user said Business Restaurant currently free and Ultra Restaurant "limited"; free fee and feature limits must NOT be conflated. Do not assume Bar is enabled universally.

## Plan gates
~~~text
Login -> authorized property_id -> active subscription entitlement snapshot
 -> module visible/action permitted?
    YES -> render enabled module and allow server-authorized action
    NO  -> don't allow write/read; optional transparent upgrade explanation
~~~
Sidebar visibility cannot substitute for server permission. Quotas: per-unit subscription Q is separate from menu count limits, theme limit and staff/operational quotas.

## Accommodation across plans (proposal)
Recommended allow the same 4 physical accommodation types on Starter, Business, Ultra; charge by actual billable Units. Restrict advanced operational modules, not basic Property inventory types. This is a recommendation only until approved.

## Unused modules
A Business property with no Restaurant should be able to mark "Restaurant not operating" and bypass menu setup. No requirement to add 20/500 menu items; those are upper limits. Basic user/staff access required for housekeeping should not grant advanced HRM/payroll.

## Upgrade, downgrade and changing unit quantity
- Display price/proration preview and explicit consent. Preserve booking history, physical units and issued invoices.
- If reduced plan cannot cover physical inventory, do not delete units: present excess-unit resolution / grace/lock policy before downgrade.
- A removed entitlement must not destroy historical restaurant/HRM data. Restrict new actions according to approved read-only/export policy.
- Feature definitions and offer versions immutable for accepted terms; new promotions only affect eligible future orders.

# 03 — Figma Make: Booking Readiness & Plan-Based Operations
Status: batch 3. Use Base Prompt, Screen Registry and approved Accommodation wizard. Build P03-01..03 and P04-01..03 only.

## Booking readiness screens
**P03-01 / Rates & Availability**: categories with nightly default rates inherited; date calendar, weekend overrides and seasonal rule (optional), operational unit status, restrictions. Check-in/out defaults displayed as inherited editable link, not duplicated storage. For mixed property list units 101, C01, V01, TA-101 with type badges/filters.

**P03-02 / Existing Stays**: prominent branch "Do you have upcoming/existing bookings?" No -> explicit "No existing bookings" confirmation; Yes -> manual add or staged CSV import *UI mock*, map existing reference, dates, category/unit, paid status. Show collision warning when V01 already booked same dates. Import does not silently merge same guest or overwrite live data.

**P03-03 / Readiness Preview**: booking calendar mock with arrivals/departures and blocked dates; status "Bookings ready for review" not "Accepting online bookings". Label operational Active, unit Booked for a range and Website Draft separately.

## Operations screens
**P04-01 / Choose Applicable Modules**: dynamic plan entitlement cards. Starter: core setup; Business: housekeeping, meals/restaurant, expenses, QR food order/other services when entitled; Ultra: advanced HRM/Inventory/Operations. Restaurant currently zero extra module fee but not auto-enabled if unsupported; Bar entitlement **not defined**: use a draft note, not a live option.

**P04-02 / Team & Roles**: essential staff names/role permissions as invite UI mock; skip until later if not needed. Reception/Housekeeping users should not imply access to Ultra Payroll. Property-only staff access.

**P04-03 / Dynamic Module Starter Setup**: compact guided forms for only selected relevant modules: housekeeping room status policy, Restaurant operating hours and menu starter (max based on entitled menu capacity, not mandatory), basic expense categories, Ultra attendance mode and HRM defaults as optional later tasks. Don't design full Restaurant POS or HRM suite here.

## Required paths and errors
~~~text
P03-01 -> P03-02 (No or Yes) -> P03-03
 -> P04-01 (plan-filtered) -> P04-02 -> P04-03 -> P05-01
~~~
If no Restaurant, choose "Not operating restaurant" then skip all meal config. User can change plan via review, retains draft data but modules obey entitlement on server when implemented. Show one invalid booking overlap state, one No Existing Bookings state, one Starter path with no Business module, one Ultra path.

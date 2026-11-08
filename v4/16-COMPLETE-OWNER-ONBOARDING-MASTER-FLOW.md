# 16 — BinGi HMS: Complete Property Owner Onboarding Master Flow

**Version:** V4 — consolidated master text diagram  
**Date:** 2026-11-08  
**Status:** REVIEW DRAFT — product/design specification only; not deployed code  
**Journey:** Registration → Property Setup → Accommodation Configuration → Rates & Bookings → Plan Operations → Digital Presence → Subscription & Verification → BinGi Approval → Activated HMS Dashboard.

## Goal and immutable principles

The owner should complete **roughly 90% of applicable configuration** during onboarding. **100% of required critical validations** must pass before submission. Non-applicable departments, plan-disabled features and optional content must not prevent submission.

- One account may operate multiple authorized properties; each property has **isolated** configuration, users, unit inventory, reservation records, subscription, invoices and approval.
- Four priority accommodation types: **Room, Cottage, Villa, Apartment**; a single property may include multiple types.
- Property Type (Hotel/Resort/etc.) and Accommodation Type (Room/Cottage/Villa/Apartment) are separate concepts.
- **Configure property-wide settings ONCE**, **configure each accommodation category ONCE**, then **register actual physical units ONE BY ONE** using *Save & Add Next*; **NO automatic bulk unit creation in onboarding**.
- The 6 owner-facing setup sections are navigation groups; focused inner tasks are separate micro-screens. Registration, BinGi Approval and Dashboard are outside those six sections.
- Draft inventory is not publicly bookable. Property approval, subscription/payment conditions and website/marketplace/OTA publishing are **separate gates**.
- Paid/commercial statements must distinguish confirmed pricing from proposed interpretation and unresolved policy. Never promise undefined free entitlements.

## Complete End-to-End Diagram

~~~text
BINGI HOTEL MANAGEMENT TECHNOLOGY
│
▼
00 — ACCOUNT REGISTRATION (ONCE)
│
├── Full Name
├── Mobile Number & Verification
├── Email & Verification (where required)
├── Password / Supported Sign-in
└── Accept Terms & Privacy Policy
│
▼
MY PROPERTIES (AUTHORIZED ONLY)
│
├── Existing Property → Resume Setup / Review Status / Open HMS if active
│
└── + ADD NEW PROPERTY
      └── Create a NEW property-scoped draft workspace (property_id)
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
01 — YOUR PROPERTY & PRELIMINARY PLAN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── 1.1 Property Identity
│   ├── Property Name
│   ├── Property Type
│   │   ├── Hotel
│   │   ├── Resort
│   │   ├── Guest House
│   │   └── Serviced Apartment / Other supported property type
│   ├── Logo (can be completed later if noncritical)
│   ├── Official Phone
│   └── Official Email
│
├── 1.2 Property Location
│   ├── Country
│   ├── Division / State
│   ├── District / City / Area
│   ├── Full Property Address
│   └── Optional Map Pin
│
├── 1.3 Accommodation Types — MULTI-SELECT
│   ├── Room
│   ├── Cottage
│   ├── Villa
│   └── Apartment
│
├── 1.4 Preliminary Subscription (not charged here)
│   ├── Starter — ৳30 / room / month
│   ├── Business — ৳50 / room / month
│   ├── Ultra — ৳116 / room / month
│   ├── Estimated Quantity (minimum 10 billing policy needs clarification)
│   └── Plan Feature / Module Access Preview
│
└── 1.5 Property-wide Operating Defaults — SAVE ONCE
    ├── Currency and Time Zone
    ├── Check-in & Check-out Defaults
    ├── Basic Booking / Property Policies
    ├── Tax / Service Defaults where applicable
    └── Save or Resume independent property setup
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
02 — SMART ACCOMMODATION SETUP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── 2.1 Show only the enabled accommodation types
│   ├── Room
│   ├── Cottage
│   ├── Villa
│   └── Apartment
│
├── 2.2 Configure Location Hierarchy — ONCE PER PROPERTY
│   ├── ROOM        → Building → Floor
│   ├── COTTAGE     → Zone / Area → Optional Block
│   ├── VILLA       → Zone / Area → Optional Block
│   └── APARTMENT   → Tower / Building → Floor
│   └── Saved location nodes are reused by every next category / unit
│
├── 2.3 Save Numbering Rules — ONCE
│   ├── Floor 1 → 101, 103, 105... (recommended, not enforced)
│   ├── Floor 2 → 201, 203, 205...
│   ├── Cottage → C01, C03...
│   ├── Villa → V01, V03...
│   ├── Apartment → TA-101, TA-103...
│   └── Custom format / gaps / 100+ levels supported
│
├── 2.4 Create or Select ACCOMMODATION CATEGORY — ONCE
│   ├── Choose existing Category or create new Category
│   ├── Category Name (Deluxe Twin, Garden Cottage, Pool Villa, 2BR Apt)
│   ├── Category Configuration & Type-specific Attributes
│   ├── Bedrooms / Beds / Bathrooms / Guest Capacity / Size / View
│   ├── Amenities from selectable cards (only actual amenities)
│   ├── Category Photos
│   │   ├── Upload
│   │   ├── Choose Cover
│   │   └── Reorder
│   ├── Optional YouTube Video Tour
│   ├── Highlights and Editable Description
│   └── Default Nightly Rate / Applicable Category Settings
│
├── 2.5 GUIDED INDIVIDUAL UNIT REGISTRATION (NO BULK CREATE)
│   ├── Keep previously saved Category and Location selected
│   ├── Enter actual Unit Number 101 → [Save & Add Next]
│   │     └── Validate & save EXACTLY ONE draft Unit
│   ├── Enter actual Unit Number 103 → [Save & Add Next]
│   │     └── Validate & save EXACTLY ONE draft Unit
│   ├── Enter actual Unit Number 105 → [Save & Review]
│   │     └── Validate & save EXACTLY ONE draft Unit
│   ├── Display Saved Units list (101, 103, 105) — no 102 or 104
│   ├── Optional Unit-specific Photo / Amenity / Price Exceptions
│   ├── Reject duplicate numbers and location/category mismatches
│   └── Do NOT create fake Units to match the subscription minimum
│
├── 2.6 Review the Actual Accommodation Inventory
│   ├── Selected Types / Saved Categories / Location Path
│   ├── Exact Physical Units & Display Numbers
│   ├── Room / Cottage / Whole Villa / Whole Apartment counts
│   ├── Inherited Category Rates & Unit-specific Details
│   └── Confirm (draft inventory; not publicly live)
│
└── More real Categories / Types?
    ├── YES → Select existing Category and Location where possible
    │          → Add next actual Unit numbers individually
    └── NO  → Continue to Booking Readiness
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
03 — RATES, AVAILABILITY & BOOKING READINESS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── Base Rate by Category
├── Optional Weekend / Seasonal Pricing & Date Rules
├── Applicable Tax, Service Charge, Extra Guest & Meal Rate Settings
├── Deposit / Refund / Cancellation Policies
├── Minimum Stay and Restricted Dates (where applicable)
├── Available, Out-of-Service and Blocked Dates
│
├── Existing Reservations?
│   ├── YES → Enter / Import Existing Reservations
│   │         ├── Guest / Check-in / Check-out
│   │         ├── Existing Category / Physical Unit
│   │         ├── Payments / Reservation State
│   │         └── Overlap / Maintenance Block Validation
│   └── NO  → Explicitly Confirm No Existing Reservations
│
└── Booking Calendar Preview
    └── Booking-ready checks; NOT yet accepting public reservations
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
04 — PLAN-BASED OPERATIONS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── STARTER (plan-entitled core only)
│   ├── Accommodation Management
│   ├── Online / Offline Booking
│   ├── Guest Management
│   └── Essential team / access controls when entitled
│
├── BUSINESS (show only applicable entitled modules)
│   ├── Housekeeping
│   ├── Restaurant / Meal Management
│   ├── QR Food Orders
│   ├── Expense Management
│   └── Other Services
│
├── ULTRA (additional eligible modules)
│   ├── Advanced Operations
│   ├── HRM / Staff Management
│   ├── Attendance / Shifts
│   └── Inventory Management
│
├── Team & Roles
│   ├── Invite Staff (where needed)
│   ├── Department / Role / Property Permissions
│   └── Add remaining Staff later if not safety critical
│
└── Unused / plan-disabled Operations → Skip safely
    (Restaurant & Bar scope and Ultra Restaurant limitations remain OPEN)
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
05 — GUEST PAYMENTS & DIGITAL PRESENCE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── 5.1 Guest Payment Setup
│   ├── Cash
│   ├── Bank Transfer
│   ├── Supported Mobile Banking
│   ├── Optional Supported Payment Gateway
│   ├── Deposits / Refund Defaults
│   └── Invoice / Receipt Information
│
├── 5.2 Website Management — CURRENTLY NO EXTRA MODULE FEE
│   ├── Choose Plan-permitted Theme
│   ├── Inherit Property Logo / Name / Address
│   ├── Property Gallery / Cover / Photo Order
│   ├── Highlights & Description
│   ├── Property Contact / Location & Facilities
│   ├── Supported Domain Configuration
│   └── Website Preview → SAVE AS DRAFT
│
└── 5.3 Online Channel Readiness (independent gates)
    ├── BinGi Marketplace — pending
    ├── Property Website — draft until reviewed and ready
    └── OTA Integration — only if separately supported/configured
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
06 — FINAL SUBSCRIPTION, VERIFICATION & REVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── 6.1 Confirm Plan, Quantity & Billing Cycle
│   ├── Starter ৳30 / room / month
│   ├── Business ৳50 / room / month
│   ├── Ultra ৳116 / room / month
│   ├── Custom Quantity & Actual Unit Count displayed separately
│   ├── Minimum Billing Quantity 10 (interpretation still OPEN)
│   ├── Monthly: no subscription discount
│   ├── 6 months: 10% discount on subscription ONLY
│   └── 12 months: 25% discount on subscription ONLY
│
├── 6.2 Explain Included Features & Current Promotions
│   ├── Website Management: currently ৳0 extra if entitled
│   ├── Restaurant & Bar Management: currently ৳0 extra if entitled
│   │   (exact plan access and limits NOT yet finalized)
│   ├── Starter Activation: not applicable
│   ├── Business / Ultra Activation: ৳29,500 standard, currently waived
│   ├── Remote Team Training: ৳500 per shift, currently free promotion
│   └── Onsite Training: ৳12,500;
│       property provides meals and stay for visiting team
│
├── 6.3 Display FINAL, ITEMIZED QUOTE
│   ├── Subscription Price × Approved Billing Quantity × Term
│   ├── Subscription-only Term Discount
│   ├── Activation Fee / Current Waiver
│   ├── Optional Training / Current Waiver
│   ├── Approved Additional Services & Disclosed Third-party Fees
│   ├── Applicable Taxes
│   └── EXACT TOTAL + Customer Acceptance / Saved Quote Version
│
├── 6.4 Owner / Business Verification
│   ├── Authorized Representative / Owner
│   ├── Legal / Residential Address when required (not Property Address)
│   ├── Identity Verification as legally applicable
│   └── Business Registration / Trade License where required
│
├── 6.5 Readiness Checklist
│   ├── REQUIRED (applicable): 100% PASS to submit
│   ├── RECOMMENDED: finish when relevant
│   ├── OPTIONAL: may finish after approval
│   └── Overall Applicable Configuration target ≈ 90%
│
├── 6.6 Final Property Summary
│   ├── Profile & Location
│   ├── Types / Categories / Actual Physical Units
│   ├── Rates, Calendar and Existing Reservations
│   ├── Enabled Operations / Team
│   ├── Payment Methods and Website Draft
│   └── Confirm Accurate Details & Commercial Terms
│
└── [SUBMIT PROPERTY FOR BINGI APPROVAL]
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
07 — BINGI SUPER ADMIN PROPERTY REVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── Verify Owner / Property / Required Documents
├── Validate Real Inventory / Category / Location / Rates
├── Check Current Reservations / Booking Conflicts
├── Review Accepted Plan, Price, Terms and Required Status
│
└── Decision:
    ├── NEEDS CHANGES → Named correction → Owner edits exact step → Resubmit
    ├── ON HOLD       → Explanation / Required Action
    ├── REJECTED      → Reason / Review Path
    └── APPROVED
         └── Check required contractual / payment activation conditions
              └── ACTIVATED PROPERTY
│
▼
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
08 — PLAN-SPECIFIC HMS DASHBOARD
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── STARTER Dashboard (permitted core modules)
├── BUSINESS Dashboard (eligible added operations)
└── ULTRA Dashboard (eligible advanced operations)
│
├── Authorized Property Only
├── Actual Room / Accommodation Inventory
├── Bookings / Guests / Date-based Unit Status
├── Enabled Plan Modules, Staff Roles and Permitted Finance
├── Website Management & Publishing Status
├── Billing, Training and Service Order History
└── Settings → Appearance (global six-control APP-01)
│
▼
SEPARATE ONLINE GO-LIVE WORKFLOW
├── Property Website Publication → channel-specific readiness
├── BinGi Marketplace Publication → channel-specific readiness
└── Each Supported OTA Publication → channel-specific integration/readiness
~~~

## Type-specific rules (shared onboarding components)

| Type | Location saved once | Category details | Actual Unit entry | Inventory accounting |
| --- | --- | --- | --- | --- |
| Room | Building > Floor | Beds, guests, bath, size, view, amenities | 101 → Save; 103 → Save | 1 room = 1 physical unit |
| Cottage | Zone > optional Block | Bedrooms, beds, bathrooms, amenities | C01 → Save; C03 → Save | 1 whole cottage = 1 physical unit |
| Villa | Zone > optional Block | Bedrooms, pool, kitchen, beds, bathrooms | V01 → Save; V03 → Save | 1 whole villa = 1 physical unit |
| Apartment | Tower / Building > Floor | Studio/1BR/2BR, beds, kitchen/living | TA-101 → Save; TA-103 → Save | 1 whole apartment = 1 physical unit |

**Important distinction:** Whether all four physical unit types also count equally for *subscription* pricing is a **recommended policy that has not yet been confirmed**. Bedrooms inside a Villa/Apartment are not additional sellable Units in V1.

## Owner-facing UI/UX contract

1. **One-time configuration:** save property, operating defaults, hierarchical locations, numbering and category-level settings so subsequent units do not repeat these forms.
2. **No Bulk Unit Creation:** explicitly save each real Unit number, preserving existing category/location; preview exactly what was saved.
3. **Only relevant steps:** plan-based module entitlements and optional departments determine which forms appear.
4. **Autosave & resume:** draft progress is recoverable per property. Save a physical Unit only after a clear Save action.
5. **90% targeted completion:** denominator includes applicable tasks, not irrelevant modules. All mandatory safety checks must pass.
6. **Property isolation:** authorization enforced in frontend and server/data layer; no access to other hotels' guests, staff, units or invoices.
7. **Commercial honesty:** subscription, one-time activation, training, current waivers, domain/provider costs, commissions and taxes shown separately.
8. **Consistent BinGi Pearl Light Figma UI:** reuse uploaded Foundation components, fixed Back/Continue, one task per screen, readable Bangla/English and responsive behavior.
9. **Read-only preview while pending:** owner sees drafts, status, corrections, quote and safe preview, not live bookings or financial transactions.
10. **Public go-live separated from HMS activation:** Website, Marketplace and supported OTA have independent readiness gates.

## Open decisions — MUST NOT be silently converted into production policy

- Does monthly "per room" price apply equally to one whole Cottage, Villa and Apartment? Recommended 1 physical Unit = 1 billable accommodation unit, pending approval.
- Does minimum 10 mean *minimum billable* units (7 real cottages can register with 10-billed) or at least 10 real eligible units? Open.
- Restaurant & Bar entitlement per plan, Business/Ultra precise feature limits, and the meaning of "Ultra Restaurant Limited". Open.
- Activation waiver eligibility/expiry and truthful standard-reference-price policy. Open.
- Remote Training shift duration, eligibility/number of current free shifts and discount limits. Open.
- Onsite Training service duration/trainer count, transport charges/cancellation terms. Open.
- First subscription payment timing vs approval, trials, refund/renewal/proration and taxes. Open.
- Guest payment gateway availability, domain provider/renewal cost, OTA integrations and commission calculation base. Open.
- Exact owner/business verification documents, security and retention requirements for each jurisdiction. Open.

## Figma and implementation references

- [V4 Workspace Index](README.md)
- [Four-Type Smart Accommodation Engine](02-ACCOMMODATION-ENGINE.md)
- [Guided Unit Registration — Latest Decision](13-GUIDED-UNIT-REGISTRATION.md)
- [Plan Entitlements](04-PLAN-ENTITLEMENTS.md)
- [Subscription & Promotions](03-PRICING-COMMERCIAL.md)
- [Approval/Payment/Publishing State Machines](05-APPROVAL-ACTIVATION.md)
- [36 Screen / 14 Prompt Design Scope](14-FIGMA-COMPLETE-SCOPE.md)
- [Figma Make Prompt Series](figma/prompt-series/README.md)
- [Open Decisions](11-DECISIONS-REGISTER.md)

**Do not interpret this document as proof that the features are already implemented in the live HMS. No code, database schema or production settings were changed by this documentation.**

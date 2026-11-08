# 04 — Figma Make: Website, Guest Payments, Quote & Final Review
Status: batch 4. Build P05-01..03 and P06-01..04. Use Base Prompt and [Pricing](../03-PRICING-COMMERCIAL.md).

## Section 05 screens
**P05-01 / Guest Payments**: cash/pay at property, mobile wallet/bank transfer, supported gateway conditional. Show only allowed integration status, no live transfer/payment functionality. Advance/deposit/refund and receipt defaults; gateway required docs conditional.

**P05-02 / Website Management**: property name/logo/address inherited; choose plan-permitted theme; website layout draft and contact/map. Current extra Website Management module fee zero where entitled; distinguish domain registration/renewal/provider extras from included website software. Preview mock uses Room/Cottage/Villa/Apartment categories from saved inventory; public publish toggle OFF during onboarding.

**P05-03 / Photos and Listing Text**: property gallery/cover/reorder, up to three highlights and editable description; category gallery already belongs to P02-06, don't ask to upload it again. "Save website as Draft" action; independent website/marketplace/OTA readiness.

## Section 06 screens
**P06-01 / Subscription Quote**: Plan Starter 30, Business 50, Ultra 116 BDT per room/month, minimum custom billed quantity 10; show actual configured physical Unit count separately. Month 1 (0%), 6 months 10% subscription discount, 12 months 25%. Example Starter Q10 6m = 1620; Business Q10 6m = 2700; Ultra Q10 annual = 10440. These are before taxes. Respect unresolved mixed inventory billing rule with visible design annotation.

**P06-02 / Setup & Training Breakdown**:
- Starter Activation N/A.
- Business/Ultra Activation reference 29,500, CURRENT waiver to 0 with transparent note and no invented expiry.
- Remote 500/shift currently free (show accepted shift quantity and eligibility as draft/undefined where needed).
- Onsite 12,500 payable, property provides team meals and stay; require explicit acknowledgement. Travel, duration and number of staff not invented.
- Website Management currently zero extra module fee; Restaurant/Bar zero only if plan entitlements, Bar scope unresolved.
- Subscription discounts do NOT reduce activation, onsite, provider charges or commissions. Quote requires explicit accepted terms and version.
- Example quote: Starter Q10 six months 1620 + free remote = 1620 before taxes; don't include old 1500 setup fee.

**P06-03 / Ownership & Business Verification**: masked demo identity fields, document upload placeholders, permission to continue according to approved required docs; never use real NID numbers/photos or personal IDs. Explain required vs optional.

**P06-04 / Readiness & Submit**: three checklist groups Required, Recommended, Optional; exact item and Fix link. Before submit show accepted quotation, module inclusions, no surprise fee, and independent website draft status. Submit confirms "Property submitted to BinGi" mock and routes WAIT-01.

## Interaction and states
~~~text
P05-01 -> P05-02 -> P05-03 -> P06-01 -> P06-02 -> P06-03 -> P06-04 -> WAIT-01
~~~
Invalid Q9 shows minimum billing warning rather than creating fake Rooms. Switch billing term recalculates correctly; switch plan changes entitled features without deleting physical unit count. Onsite selection reveals stay/meals obligation checkbox. Missing required booking conflicts block Submit; missing optional highlight does not.

## No live integration claim
Payment is a prototype quote/acceptance, not a gateway charge; photo upload and verification are local mock state; websites are DRAFT and never publicly published by this prototype.

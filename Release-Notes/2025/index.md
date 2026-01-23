---
title: 2025
parent: Release Notes
nav_order: 1
layout: default
has_toc: true
---

# Release Notes 2025

## Date 16/01/2026  
## Release 1.2601.3.0

---

## [NEW]

### Movements - Causes - Stock
- Added new stock state, which manages completely wrecked products stock.

### WEB
- Added BuyBook web application that allows creating and editing products linked to a BuyerPlan.
- Products created or modified in BuyBook are immediately visible in IPOS.

### POS
- Added the possibility to reprint the store credit barcode (voucher code) when reprinting a return receipt.

---

## [IMPROVEMENTS]

### Vouchers
- Removed **"HYBRID"** Isolation Level from Voucher Generators.
- Added new property **"Can Issue on Local DB"**, which specifies if the voucher can be issued without having connection to the Central HQ Server in order to define the true Isolation Level of the Voucher.

### POS
- The Reduced Prices as promotion now displays the percentage of the discount applied besides the value (visually only, not saved).
- The search for receipts can now be done by receipt number, besides the date of issue.  
  This is available only if the receipt number does not reset daily  
  (app parameter: `ResetReceiptNumberDaily = False`).
- StoreDayClose improvement.

### BackOffice
- In the Promotions Management section, the brand of products is now displayed, only if the store has `storeBrand` set on at least one store.
- Receipt import improved to recognize products also by product code.
- Optimized discount handling during receipt import: movement discounts are no longer created when no discount is present.
- Changed Zebra Labels print default extension to `.zpl`.
- Added a new button on the **BuyerPlanDetailsForm** with the standard **Generate Labels** functionality.
- Improved the query for viewing **Product Selector – Price Lists** tab.
- Improvement on Incoming Document **Generate Labels**.

---

## [FIXES]

### Promotions with Maximum Season Start Date
- Fixed an issue where the Max Season Start Date was also being included as a trigger when applying a promotion.  
  Now the promotion applies only for dates **before** the selected date.
- Fixed an issue where disabled manual movement causes were still proposed during manual movements.
- Fixed movements import from Headquarter to Stores where `CreateStoreId` was not populated, causing synchronization issues.  
  `CreateStoreId` is now automatically set to `1` when no value is provided in the import procedure.
- Removed the association between the Order and Receipt on XPO.
- Changes for THUN File Manager

## Version 1.2502.0.0 Date 12/02/2025

### FIXES
##### POS:
- Fix timeout issues on StoreDayCloses. 
##### BO  -> 	Health Insurance
-	Fixed Health Insurance 
-  Removed rowType : Pending 
- Verification of an already sent receipt to TS
- Feature: Implemented the Variazione type

##### BO -> Electronic Invoices
-	Correctly added rounding loss as discount

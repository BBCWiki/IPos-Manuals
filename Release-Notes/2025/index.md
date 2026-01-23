---
title: 2025
parent: Release Notes
nav_order: 2
layout: default
has_toc: true
---

# Release Notes 2025

## Date 12/12/2025  
## Release 1.2512.4.0

## [NEW]

### BO
- **Delivery Document Details**: Added a new column that shows the product stock based on the selected Cause `WarehouseTypeId`.
- Added Excel import for receipts in emergency situations where the store PC is not functioning.
- **Inventory Details**: Display and distribution of product quantities at the warehouse level.
- **EntranceGoodsDeliveryDetail**: Block adding new products in DDT  
  (StoreSetup parameter `AllowAddNewProductsToEntranceGoods`).
- **Delivery Document Report**: The report now shows the stock based on the selected Cause `WarehouseTypeId`.
- Extended the **Sales by Hour** report to include sales and usage of external vouchers.

### POS
- Integrated with the Spanish fiscalization system **VeriFactu**.

## [IMPROVEMENTS]

### POS
- Added new index on column `VatCode`, table `Contacts`, to make searching by VAT code faster.
- Fixes on promotion triggers with Dynamic Level.
- Minor improvements on refund warning/block logic and messages.

### BO
- **Season planning**: Improvements on automatic season planning (UI and value computation).  
  Added reference sales period and support for multiple reference seasons.
- **Stock Analysis report**: Added product barcode.
- **Promotions**: Fixes on promotions with multiple conditions on the same row.
- **Delivery Document Report**: The report now shows the stock based on the selected Cause `WarehouseTypeId`.

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

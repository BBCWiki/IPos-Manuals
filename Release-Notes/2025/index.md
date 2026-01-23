---
title: 2025
parent: Release Notes
nav_order: 2
layout: default
has_toc: true
---

# Release Notes 2025

## Date 18/12/2025  
## Release 1.2512...

### [NEW]

#### BO
- Added Notes on the Electronic Invoice; in the XML export, notes are stored in the **Causale** field.
- **Inventory Details**: Generates movements when physical quantity > 0 and accounting quantity does not exist; price list is returned by `GetProductB2CPrice` function.

#### POS
- Added Notes on the invoice print user control; notes are saved in **Invoices** and added to the invoice header layout.
- Added IT translations in the Store Day Close.

---

## Date 12/12/2025  
## Release 1.2512.4.0

### [NEW]

#### BO
- **Delivery Document Details**: Added a new column showing product stock based on selected Cause `WarehouseTypeId`.
- Added Excel import for receipts in emergency situations where the store PC is not functioning.
- **Inventory Details**: Display and distribution of product quantities at warehouse level.
- **EntranceGoodsDeliveryDetail**: Block adding new products in DDT  
  (StoreSetup parameter `AllowAddNewProductsToEntranceGoods`).
- **Delivery Document Report**: Stock is now shown based on selected Cause `WarehouseTypeId`.
- Extended **Sales by Hour** report to include sales and usage of external vouchers.

#### POS
- Integrated with the Spanish fiscalization system **VeriFactu**.

### [IMPROVEMENTS]

#### POS
- Added new index on column `VatCode` (table `Contacts`) to improve VAT code search performance.
- Fixes on promotion triggers with Dynamic Level.
- Minor improvements on refund warning/block logic and messages.

#### BO
- **Season planning**: Improvements on automatic season planning (UI and value computation).  
  Added reference sales period and support for multiple reference seasons.
- **Stock Analysis report**: Added product barcode.
- **Promotions**: Fixes on promotions with multiple conditions on the same row.
- **Delivery Document Report**: Improved stock visualization based on selected Cause `WarehouseTypeId`.

---

## Date 28/11/2025  
## Release 1.2511.8.0

### [NEW]

#### POS
- Added possibility to create (but not use) vouchers without HQ connection  
  (`VoucherGenerator.IsolationLevel = "HYBRID"`).
- Reduced price lists (type **P**) can now be managed as discounts  
  (`POSUseReducedPriceListsAsDiscounts`, `ListPriceDiscountCauseId`).
- Advance payments rounded to nearest higher multiple of 5 (NAU).
- Payments rounded to 5 cents (IDEXE).
- Modified receipt printed text (IDEXE).
- Added refund-related StoreSetup parameters:
  - `POSRefundMaxDaysExceededMode`
  - `POSRefundMaxDays`
- Added **TotalQuantity** on default Dashboard.

#### BO
- **Season Planning**: Automatic proposal of quantities based on previous seasons.
- **Store Order**: Added available stock visibility (IDEXE).
- **Conformity**: Updated default layout and added missing details.

### [IMPROVEMENTS]

#### POS
- Warning messages improvements.

### [BUGFIX]

#### POS
- **StoreDayClose**: Fixed missing SafeBoxRevealedValue.
- **NumericKeyboard**: Fixed clear button.

---

## Date 14/11/2025  
## Release 1.2511.2.0

### [NEW]

#### POS
- **Barcode Printing Feature** for non-fiscal Epson receipts:
  - Enabled via `NonFiscalSalePrintProductBarcodeOnReceipt`
  - Mapping via `NonFiscalSaleProductBarcodeMappings`
  - Mapping format: `{SubfamilyCode}{VatRate}`
  - Barcode format: `{MappingString}{Price}`

#### BO
- Automatic export of receipts to Health Insurance (Tessera Sanitaria).
- GDPR improvements: anonymization or deletion of sensitive data via StoreSetup parameters.

### [IMPROVEMENTS]

#### POS
- Updated StoreDayClose template (Lush CR).
- Combo Promotion enhancements (kits, trigger value and quantity).

### [FIXES]

#### POS
- Fixed lot split issue for products with stock < 1.
- Fixed Engage Voucher consumption across cash registers.

#### BO
- Fixed visibility/editing of trial lenses without prescriptions.

---

## Date 17/10/2025  
## Release 1.2510.13.0

### [FIXES]
- **InvoiceDate (Quietanza)**: Fixed incorrect payment dates.
- **DDT duplication**: Fixed stock movement logic.
- **Optical Module**: Fixed prescription and Work Order visibility issues.
- Fixed BO DDT certification null reference error.
- Fixed POS login constraint error.

---

## Date 14/10/2025  
## Release 1.2510.11.0

### [NEW]
- IPosWebApi voucher codes now prefixed with **"Barcode:"** in JSON.

### [FIXES]
- Allow `discountValue` to be null.
- Fixed EntranceGoods product deletion issues.
- Fixed Engage CRM voucher consumption sync.

### [IMPROVEMENTS]
- Store Day Close text and layout improvements.
- Store Credit sales marked as **NOT PAID** in mixed transactions.
- Fiscal printer ticket payments mapped as **DISCOUNT**.

---

## Date 09/10/2025  
## Release 1.2510.9.0

### [NEW]
- New promotion type applicable after exclusive promotions.

### [FIXES]
- EntranceGoods product deletion bug fixed.

---

## Date 07/10/2025  
## Release 1.2510.6.0

### [IMPROVEMENTS]
- StoreDayClose parameter renamed to `StoreDayCloseCashBoxValueRequired`.

### [FIXES]
- Fixed voucher activation without fixed value.
- Fixed fidelity points redemption discounts.

---

## Date 26/09/2025  
## Release 1.2509.11.0

### [FEATURES]
#### BO
- DDT: Added **Save layout** functionality.

### [IMPROVEMENTS]
- POS: StoreDayClose row visibility options.
- BO: Reduced Delivery Document certification time.

### [FIXES]
- POS: Cross-store refund fix; removed minimum age limit.
- BO: Fixed Pegaso SEL OPTICAL order status issue.

---

## Date 24/09/2025  
## Release 1.2509.9.1

### [FEATURES]
- Multi-use vouchers with operator-assigned codes.

### [IMPROVEMENTS]
- BackOffice: Store brand/coordinates, Store Selector enhancements.
- Receipts: Detailed discounts grid.
- Promotions: Auto-focus on newly added products.

### [FIXES]
- DDT certification with defective stock.

---



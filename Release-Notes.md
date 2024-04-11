---
callouts:
  Release Notes:
    title:  Release Notes
    color: blue
---

# Release Notes

## Version 1.24.4.0 - Date 28/03/2024

### Changes

BO → Goods Redistribution: Added new fields and functionality

- Added % sold, supplier name, supplier code, main (sale) price, ordered + loaded quantities from orders columns on the left (by product).
- Added ordered + loaded quantities on the right (by style).
- Added totals for quantities and average for % sold below the left grid (by product).
- Fixed calculation of totals for "in arrival from orders" (by product).
- Added % sold by color on the right.
- Sum the totals of sales if only sales is selected as a row type on the filter on the right (by style).
- Block the user to move a specific product+style to another store if the destination store already has the item in redistribution.

BO → Goods Flow → Picking Lists

- Added the feature for the user to view for each picking list the generated packing lists.
- Management of Picking List states - allow to generate a packing list only in state NEW

BO → Goods Flow → Incoming Documents
	
- Added the feature for the user to view for each entrance of goods the generated picking lists.
- In delivery documents details the user can only add Containers Type Packing Lists with the same destination as the delivery document or without destination

BO → Goods Flow → Outgoing Documents

- Create containers without destinations type Packing lists from Entrance Goods

### Fixes

- Fixed a bug in which the generic article was losing its custom name upon saving an entrance of goods.

## Version 1.24.3.1 - Date 15/03/2024 

### New Features


BO → Work Order → Kit Configurator

- Added "Default Service" row type for kit configuration which allows adding a single product as a mandatory item inside the kit.
- User will be prompted to add the default service automatically when saving the glasses configurator if not added manually and will add the minimum quantity required in the kit.
- Sync in download contact
- Download of a contact created in other store than the current one will now download the contact's prescriptions as well.

## Version 1.24.3.0 - Date 15/03/2024

### Distribution feature rework

BO → Goods Flow → Incoming Documents → Distribution Button

The "Distribution" feature allows users to distribute merchandise proportionally across multiple stores, with two distribution types:
     
- 'PF' (based on product family) and 'FR' (without product family restrictions).
- After selecting the percentages, users can manually adjust percentages for each store.
- The distribution type cannot be changed from the "Distribution Form", but percentages can be modified.
- After verifying the distribution, users can generate picking lists for each store using the "Generate Picking Lists" button.

## Version 1.23.11.0 - Date 20/12/2023

### New Features


POS → Payment → E-Receipt

- NewPaymentUserControl: Added functionality to send the receipt via email to a registered contact with an email.
- MainPosForm: Checking the new parameter StoreSetup PosEReceiptEnabled to enable the new functionality.
- EpsonFiscalPrinterIntelligent & EpsonFiscalPrinterIntelligentRT: Added validations for the e-Receipt.

### New Form


BO → Catalog → Optical Products

Description:

The Optical Products Form allows users to efficiently retrieve information about Frames, Contact Lenses, Pre-assembled Glasses, Accessories, and Ophthalmic Lenses.

1. Product Search and Display:

   - Added functionality for searching and displaying product details.
   - Barcode, product ID, or product code can be entered for quick lookup.

3. Product Selector:

    - Introduced 5 buttons for quick access to major product categories (Frames, Contact Lenses, Pre-assembled Glasses, Accessories, Ophthalmic Lenses).
   - Each button opens a specific selector for the chosen product type.

4. Product Details:

   - In the middle of the form, all characteristics of the selected product are displayed based on its type.
   - For contact lenses, variations are also presented.

5. Grids for Sales, Orders, and Movements:

    - Added 3 grid controls to display information about sales, orders, and movements of the selected product.
   - Information is updated in real-time based on the selected product.


## Version 1.23.10.3 - Date 07/12/2023

### New Form


BO → Catalog → Optical Products

Description:

The Optical Products Form allows users to efficiently retrieve information about Frames, Contact Lenses, Pre-assembled Glasses, Accessories, and Ophthalmic Lenses.

1. Product Search and Display:
 
   - Added functionality for searching and displaying product details.
   - Barcode, product ID, or product code can be entered for quick lookup.

2. Product Selector:

    - Introduced 5 buttons for quick access to major product categories (Frames, Contact Lenses, Pre-assembled Glasses, Accessories, Ophthalmic Lenses).
   - Each button opens a specific selector for the chosen product type.

4. Product Details:

    - In the middle of the form, all characteristics of the selected product are displayed based on its type.
   - For contact lenses, variations are also presented.

6. Grids for Sales, Orders, and Movements:

   - Added 3 grid controls to display information about sales, orders, and movements of the selected product.
   - Information is updated in real-time based on the selected product.

### Changes

 POS

- ApplyNxMEffects: Renamed to Promo N x M.

 BO

- Facit - FACIT - Error Credit Note for BUONO REGALO + Resources → 'Voucher manuale': Resolved error of credit note for Gift Voucher.
- Buyer Plan: Blocking editing as certified (from the list).

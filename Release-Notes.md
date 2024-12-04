---
layout: default
title: Release Notes
nav_order: 6
---

# Release Notes
## Version 1.2412.1.0 Date 04/12/2024

### Features

Added the option to include free-of-charge items in shipping invoices.
Introduced the ability to add shipping charges to shipping invoices.
Added a procedure to force the download of a specific work order from HQ (SyncInThisWorkOrder).

### IMPROVEMENTS

Ipos Android WS: Added the ability to delete dining tables and updated with Name support.
ElectronicInvoices: Included missing data for electronic invoices.

### FIXES

BO -> Work Order: Resolved an issue with the discount division for vouchers in work orders.
Scorpion Bay Connector: Fixed a bug in the export of invoices.
Fixed an issue with progressive product increments during the import process.



## Version 1.2410.4.0 Date 28/10/2024


### IMPROVEMENTS
SYS -> Hotfixes:
Hotfixes will now be automatically applied, regardless of the DBUpdate parameter setting.
Increased the hotfix command timeout to 2 minutes.

### FIXES
Fixed an issue where the work order (WO) was not marked as modified .Now, changes to the work order are correctly saved.


## Version 1.2410.3.0 Date 17/10/2024

### IMPROVEMENTS
BO-> Goods Flow -> PickingLists: Users can now create picking lists for other stores exclusively from HQ, provided they have the required role permision.

### FIXES
BO-> Goods Flow -> PickingLists:
- Picking lists are now editable even if the CreateStoreID is null.
- Fixed a bug where incorrect quantities were displayed in the Picking List Report for the picking lists with the "Include All Product Stock" flag enabled.
- Added a new permission that governs the creation of picking lists for other stores


## Version 1.2410.1.0 Date 08/10/2024

### Features
BO-> Contacts
- Implemented a condition that ensures a new fidelity card for a person begins with the specific card's prefix, if one exists.

SYS
- Updated license configuration to replace the config license when a different license is detected in the database.

BO -> GoodsFlow -> PickingLists
- Added the ability to create a generic picking list for all stores directly from HQ, as well as the option to create a picking list containing all stock for selected products. 

### FIXES

POS:
- Fixed the problem when creating a buono omaggio



## Version 1.2409.2.0 Date 25/09/2024
### FIXES
POS:
- Updated the display of percentage values in the application. Percentages will now show only the whole number part without rounding (e.g., 12.69% will be displayed as 12%).

BO -> Buyer Plans
- Saves correctly the change (replace) of the Color of a product, and also the change of the supplier color code
- Report prints correctly the supplier color code present in the current buyer plan.
- Adding a new product will load correctly the current supplier color code of the product

BO -> Sync Log Viewer 
- show the time in 24h format

  
## Version 1.2409.1.0 Date 20/09/2024
### Features
BO -> Delivery Documents
- Added possibility to see if a delivery document would bring stock for products into negative as a report upon saving the DDT - Enabled by a Store Setup parameter.
- Added possibility to block certification if the DDT would bring stock for products into negative - Enabled by a Store Setup parameter.

### IMPROVEMENTS
BO -> Buyer Plans
-Now a BuyerPlan is impossible to be created/open if it's categoryCluster has no stores assigned + InfoMessage

BO -> Contacts (Prescription)
- Added a warning that informs the user if they are not allowed to add a new occulist

BO -> Delivery Documents
- Added the possibility to edit the Delivery Document headers before certification

### FIXES
BO -> Work Orders
-Fixed the problem where the voucher were not applied if the WO was modified after the endDate of the Voucher
-Fixed an issue where the (WO) creation button did not display the information indicating that the client information verification had failed
-Fixed the inseration of a new treatment
-Fixed the inseration of a Discount maxValue for treatment

BO -> Buyer Plan
-Fixed the colorId and the colorName in the Store-Product and Product-Store Reports

BO -> Accountant Registration
- Set higher timeout for Accountant Registration

BO -> Products
- Disabled visibility for barcodes that are not enabled

BO -> Vouchers
- Display error when a product's specifications are being edited after the voucher applied on it has expired

## Version 1.2409.0.0 Date 06/09/2024
### Features
POS
- Added the option to choose whether to print the reasons for returned products or not.
- Added the option to specify the barcode type (CODE39 or CODE128) for printing the barcode.
- Added the ability to download store history from the settings interface.

### IMPROVEMENTS
POS
- Adjusted the barcode position by moving it to the center
- When a product is refunded, the Return Product Reason interface will now appear.

BO
- Added a regulation on RepositoryType when creating a VoucherGenerator
- Disabled label types will no longer be displayed in the Products Form

SYS
Improved the automatic application of hotfixes:
 -Automatically retries executing failed procedures when the application is reopened.
Reworked the synchronization procedures responsible for downloading movements.


### FIXES
POS
- Fixed a bug where you could add as many voucher generated by a voucherGenerator with an exisiting cumulativeCount
- Fixed the total calculation in Receipt Details.
- Prevented activation and value insertion for vouchers that are already activated.


## Version 1.2408.1.1 Date 27/08/2024
### IMPROVEMENTS
POS
- Added the possibility to configure the editing of quantity for the selected product.
- When entering the payment screen, a list of out-of-stock products will appear. The option to allow or block the transaction can be configured
 
## Version 1.2408.1.0 Date 22/08/2024
### FEATURES
Login
- License verification when performing Log In action

### IMPROVEMENTS
POS
- Added the possibility to configure the editing of prices and discounts for the selected product.

### FIXES
BO -> DeliveryDocuments
- Fixed an issue where DDTs could not be printed if the DocumentNumber contained other characters than numeric ones.

## Version 1.2408.0.0 Date 13/08/2024
### IMPROVEMENTS
 POS
- Added a new mode for promotion NxM, promotion NxM mode Split(S), In this mode, the promotion discounts the least expensive items in the entire transaction and splits the discount proportionally across all N item(s) in the promotion.
- Added an option to configure warnings or block sales of out-of-stock products.

### FIXES
BO -> Vouchers
- Fixed a bug where cumulative box was unchecked for all the cases
BO -> BuyerPlans
- fixed the styles view after printing the raport

## Version 1.2407.3.0 Date 31/07/2024 
### New Interface - Customer Display
This feature enhances the customer experience by providing a dedicated display at the point of sale (POS) that shows real-time transaction details, including scanned items, quantities, discounts, and any special orders. Additionally, it offers the capability to display targeted ads and the company logo.
Key Features:

- Real-time Transaction Display:
Shows scanned items with full details, such as quantities, discounts, and special orders.

- Ad and Logo Display:
Ads appear on the left side of the screen, while a custom logo is displayed above the product list.

- Flexible Screen Configuration:
Users can configure the display to appear on any screen 

### FEATURES
POS -> Reserve
- Added possibility of reserving products into an order for a specific contact in POS.

### FIXES
BO -> Labels
- Fixed an issue where custom labels did not show the percentage discount correctly.

## Version 1.2407.2.0 Date 26/07/2024
### FEATURES
Applying Hotfixes from SBSoftware Portal:
- Hotfixes will be automatically applied directly from the portal, tailored specifically for the database version that the application opens.

 ### IMPROVEMENTS
BO -> Delivery Document Details
- Made Product Id (ICode) visible by default.
  
BO -> Analytic Accounting
- Finish Estimate dropdown visual improvement.
  
POS -> Store Day Close
- Made totals column wider in order to fix a visual issue which showed ###### if the number was too large.
  
Switch user
- Users not associated with the current store can no longer be used for transactions.

### FIXES
BO -> Products
- Fixed a bug in which semi-online and online stores could not see the correct stock on the Styles tab below the products.
  
## Version 1.2407.1.0 Date 24/07/2024
### FEATURES
BO -> Analytic Accounting:
- Finish estimate: Added new column which displays either the Budget or the Actual values based on the user selection

BO
- Added StoreVisitors to the Reports and Analysis section.

BO -> Goods Moving:
- Product containers can now be modified when impersonating a store from HQ, provided the impersonated store has a database level of LH or H
	
### IMPROVEMENTS
BO -> Analytic Accounting:
- Chart Of Accounts, Cost Revenue Centers, Subtotals Detail forms are now in the context of the selected company from the main page
  
BO -> Utility -> Users -> User Details
- Maximum user code length in characters is now parametrizable in Store Setup (Default = 5, Maximum = 10)
  
BO -> Goods Moving:
- Prevents opening the same product container multiple times
  
Deadlock Prevention
- Enhanced stability by preventing deadlocks during container saves and FiscalDayClose save

### FIXES
BO -> Analytic Accounting
- Fixed a bug which prevented the user from creating new subtotals
- User is now being warned if no month is selected on the report
  
BO -> Base Informations -> Carriers
- Fixed a bug where the dropdown of the Company column on the Carriers page did not show data correctly
  
BO -> Promotions Management -> Promotion Details
- Fixed an issue where the Product Supplier Code column showed the Product Code of the supplier instead of the Supplier Code
  
Sync Download Store History
- Fixed an issue where the sync of Clinical Status was not functioning when downloading Store History
  
BO / POS -> Request User Code
- It is no longer possible to change to a disabled user
  
BO/POS
- Fixed an issue where the database level was incorrectly changed from LH to L after an update
  
POS
- Fixed issue with lot assignment when changing the style of substituted products

  
## Version 1.24.7.8 Date 17/07/2024
### FIXES
POS:
- Corrected the IsVoucherSaleEnabled column in the PosPaymentTypes table to be set to 1 where it was previously null.
BO -> Packing lists:
- The functionality for printing the packing list labels
- PickingLIsts can now be modify only by the create store

### IMPROVEMENTS
BO -> Labels
- Allows user to select if discount is printed on the label through a checkbox enabled from StoreSetup.

BO -> Analytic Accounting
- Added filter by company on Chart of Accounts, Accounting Movements and Cost Revenue Centers.
- Improvements on Chart of Accounts display for more clearness on the levels of the accounts.
- Added Cost Revenue Center Type on the report.
- Report name is automatically completed with the account or subtotal selected but can still be edited by the user.
- Report editor allows only Master Accounts to be selected.
- Small Layout improvements on the report.
- Added missing captions.

### FEATURES
BO -> Analytic Accounting
- Added editor of subtotals formulas for the custom report.

## Version 1.24.7.7 Date 11/07/2024
### FIXES
BO -> Goods Moving 
- Fixed an issue in which the user was prompted to select the quantity when moving the grand total
- Fixed an issue in which the store which was receiving the goods could send them to another store

BO -> Entrance Goods
- Fixed the message of missing product when you add it into an entranceGoods (now it will be shown only when the button 'Add Quantity as a new Row' is disabled)
		
BO -> Goods Moving:
- Fixed an issue in which the Grand total could not be moved.
	
POS:
- Fixed an issue in which the voucher expiration date was not printed on the receipt.
- Show only the used PaymentTypes to StoreDayClose

### FEATURES
- Created the possibility to select which payment method will be shown when paying a voucher
- Added Procedure to sync missing users from local to HQ
- Added Procedure to Sync Schema s Procedures

### IMPROVEMENTS
BO -> Accounting -> Analytic Accounting
- Added possibility of selecting multiple months for the reports at once
- Added custom report row editor
- Import of budget movements: The date column is now split in 2 different columns: Year & Month


## Version 1.24.7.6 Date 05/07/2024
### FIXES
BO -> Product Container Details:
- Fixed the validation of products with quantity 0 when saving a productContainer.

BO -> Goods Moving:
- Fixed an issue in which the Grand total could not be moved.
	
Voucher Validity:
- Fixed an issue in which the voucher expiration date was not printed on the receipt.

### NEW MODULE
BO -> Accounting -> Analytic Accounting
- Analytic Accounting module

## Version 1.24.6.5 Date 25/06/2024
### IMPROVEMENTS
BO -> Buyer Plans
- Added 'PaymentDate' in all the buyerPlan Reports

## Version 1.24.6.4 Date 20/06/2024
### FIXES
POS -> Tax-Free
- Added the possibility to activate GlobalBlue after selection of paymenttype

## Version 1.24.6.1 - Date 07/06/2024
### Fixes
BO -> Goods Moving
- Validation and minor bug fixes
### NEW FEATURE
POS Payment
- Added the possibility to activate and generate a tax-free invoice without a preselected contact from the payment interface with the press of a button.


## Version 1.24.6.0 - Date 03/06/2024
### Fixes

Custom fiscal printer
- Fixed an issue where the discount was not calculated correctly on the XML sent to the printer

Store Selector
- Fixed a bug where some stores remained unselected after pressing “ALL” on the store selector.
- Corrected an issue where only half of the stores were selected alternately when filtering by unselected and pressing “ALL”.

### Improvements

BO -> Work Order
- Disabled the “Print Conformity” button for contact lens Work Orders.
BO -> Active Promotions
- Added "Supplier Product Code" column to the Active promotions form.
BO -> Products Redistribution (Goods Moving)
- Displays a message when all available stock quantities are already in redistribution from the selected source store.
POS -> Product Families Fidelity points
- Changed the logic for checking product membership in the “SPESE SARTORIA” or “BUONO REGALO” families to use product codes instead of names.

### Changes

BO -> Contacts -> Prescriptions
- Users can no longer modify prescriptions without proper permission.

## Version 1.24.5.1 - Date 24/05/2024
### Improvements

BO -> Goods Flow -> Goods Moving
- Added new field for sold percentage (Sold / all colors / store %)
- Captions improvements

BO -> Buyer Plans
- Prohibited changing the BuyerPlan status to "certified" while in edit mode.
- Implemented a restriction preventing changes to the BuyerPlan status if it is already certified.
- Improved system functionality to prevent users from accessing BuyerPlans that are already open.

StoreDayClose
- Fix saving of POS Terminal balances on MoneyMovement with Cause CC_PT_VENDITAPRODOTTI

## Version 1.24.4.7 - Date 07/05/2024
 
### Fixes

- When the RequestUserCode parameter is set to true, a fix has been implemented to ensure that the Order.CreateUserId is updated with the UserId provided by the user

## Version 1.24.4.6 - Date 30/04/2024

### Changes

BO -> Goods Moving
- Addressed an inconsistency in the sold percentage calculation

### Fixes
BO -> EntranceGoods
-  Resolved an issue preventing products with a quantity of 0 from being visible within EntranceGoods
 
## Version 1.24.4.5 - Date 26/04/2024
 
### Fixes

- Fixed a bug which prevented the user to print a DDT if the description of a product contained lens graduations (e.g. -5.00)
- Fixed a bug which blocked the user interface while "Check All" button was pressed when store selector drop down menu was opened
- Fixed a bug which was not showing correct fidelity points on buono di reso (Punti Sulla Spesa and Client's total points)
- Fixed quantities not being seen when creating a DDT with defective products.

### Changes

BO -> Goods Flow -> Delivery Documents
- Creating a DDT from a store to a contact now allows choosing from all contacts instead of only the ones which are visible for the store.
 
BO -> Goods Flow -> Goods Moving
- changed the percentage calculation to be sold / loaded from orders
- made the supplier code and supplier name columns visible by default
- made possible to see percentage by store and also by total sales
BO -> Goods Flow -> Movements
- made notes of a DDT visible in ManualMovements
 
BO -> Registry -> Base Information -> Companies
- Providing the ability to set one of the Alternative Addresses of the company as the delivery address of the company.
- If a delivery address is set, that selected address will be displayed in the buyer plan report "Print Document by Product" as Destinazione Merce.

### Improvements

- Delivery Documents, Entrance Goods improvements on the processes of loading, saving and sync.

## Version 1.24.4.4 - Date 12/04/2024

### Changes

BO → Reports A4 → Ricevuto x classe x prezzo
 - Changed report to be able to see goods received even if not ordered or from entrances/orders made without a buyer plan.
  
BO → Active promotions
 - Added the possibility to see the price variations made for products in a specific day alongside the promotions on the active promotions form.

##  Version 1.24.4.3 - Date 10/04/2024

### Fixes

- The issue where the revealed quantity of a new product did not accumulate correctly when a container was added in an entrance of goods has been rectified.

- Users can now access the details of a product container even when it does not have a specified destination


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

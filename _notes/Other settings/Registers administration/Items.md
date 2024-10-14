

#MeasureUnits
#Registers
### Catalog of Items 
#CatalogOfItems 


> [!NOTE] Duplicate validation
> takes into consideration Code + Purchase or Sale. It is possible to save two registers with the same code: one for purchase, and another for sale. But it’s only possible to save via Imports and API due to external ID, as it can’t be duplicated


**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Category" selector:
	* Categories are being created in #CatalogCategory 
	* Each category is displayed with the name and the description
	* full text search
* "Description input" - required, max 300 symbols
* "Supplier" selector
	* functionality is the same as in when "+" is clicked #Partners 
	* each partner is displayed with the name, address, ID, VAT
*  "Price without VAT" number input (0,00 is by default)
* "VAT type" selector, required (empty ), rates are displayed according to the legislation. For CZ:
	* Basic (21%)
	* Reduced (12%)
	* Exempt (0%)
* "Currency" selector. Full text search. Validation for unknown value
* "Unit of measure" selector. This registers can be created in #MeasureUnits 
* "Purchase/Sell" checkboxes. Both true by default
* "Valid" toggle - if true, register will be available throughout organization in [[Document types]], [[Document detail. Accounting fields]], [[Bulk actions]]
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is  required
* "IsValid" - TRUE or FALSE, is required
* "MeasureUnit"
* "Category"
* "Partner"
* "UnitPrice"
* VATType: FirstReduced, Basic, Exempt
* Currency
* Purchase: TRUE/FALSE
* Sales: TRUE/FALSE
* Updated: date

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics

**Columns:
* Code. Has sorting
* Category. Has sorting
* Description. Has sorting
* Supplier
* Price without VAT. Has sorting
* VAT type. Has sorting
* Currency. Sorting
* Measure Units
* Updated. Sorting
* Valid
* Recycle bin. Removes the register

---

### Catalog Category 
#CatalogCategory 

Created category can be assigned to the items

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is not required
* "Valid" checkbox - if true, register will be available in #CatalogOfItems 
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is not required
* "IsValid" - TRUE or FALSE, is required

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics

**Columns:
* Code. Has sorting
* Description. Has sorting
* Valid
* Recycle bin. Removes the register

### Measure Units 
#MeasureUnits 

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is not required
* "Valid" checkbox - if true, register will be available in #CatalogOfItems 
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is not required
* "IsValid" - TRUE or FALSE, is required

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics

**Columns:
* Code. Has sorting
* Description. Has sorting
* Valid
* Recycle bin. Removes the register

---

### Document Items Template 
#DocumentItemsTemplate 

Document items template are used throughout application in:
[[Rossum. Lines]]
[[Document detail. Lines]]
[[Orders]]
[[Outgoing Invoice]]


**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Name" input - must be unique, required field
* "Method of use" selector:
	* Percent
	* Values
* Kebab menu: Import
* "Add item" button. Opens the template creation dialog window

#### Template creation dialog window

"Name" input - is already filled in the previous dialog window
"Method of use" selector - is already filled in the previous dialog window
Lines:
* each item represents one line, each line has an order number
* "Business item" selector is the first column. Can be selected from existing registers #CatalogOfItems or custom value can be inserted
* "Description" input - can be filled automatically from selected item or custom value can be inserted as well
* Accounting fields, VAT type is the last one
* "Amount", number input, includes 4 decimals (VALUE MODE)
* "Unit of measure" selector #MeasureUnits (VALUE MODE)
* "Price per unit"  number input, includes 4 decimals (VALUE MODE)
* "Total amount" read only number input, includes 2 decimals and can be rounded (VALUE MODE)
* "Percent" number input, includes 2 decimals. Has validation when value is 0 or more than 100
	* Error message "Check the percentages on the items, they can be from 0.01 to 100"
* Copy button
* Remove button
"Add item" button adds new empty line
 Kebab menu:
 * Delete all
 * Import. The same excel template as in #CatalogOfItems 
 * Export

> [!important] Value vs Percent 
Value:
> * each line in template has certain selected amount, price per unit and total amount
> * the exact amounts are transferred to the document detail
> 
Percent:
> * each lines in template has only selected percent of the total amount (which is unknow)
> * when the template is applied to the document, lines will get the amounts based on the calculation of its percent from the total amount of the document and recapitulation



> [!NOTE] Copying values by dragging the cell
> Value of each cell can be copied to another lines. You just need to hover the cursor the right bottom corner of the cell until + icon appears and drag the cursor over the same cells in other lines


**Search bar
* full text search by code and description, ignores diacritics



**Columns:
* Name. Has sorting
* Method of use. Has sorting

---



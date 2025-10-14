
##### Lines visibility

Can be hidden/unhidden with the help of:
* lines icon on the left panel
* "close" button

"Lines" icon displays the count of the lines
The height of the lines section is adjustable by dragging the section header

##### Lines stretching

* Lines section has stretching button (two arrows)
* Stretching of the lines applies automatically on "Files" section
* User can stretch the lines along the width of the document
	* Save and Cancel buttons will be above the lines section on the left

---


##### Lines columns

The widths of the columns is memorized within the kind (mobile version - the width is by defult)
Columns settings for Lines contains the accounting fields columns:


> [!important] Visibility of the columns
> Visibility of accounting columns depends on the settings in [[Customization. Field settings for ERP]] . If the accounting field is excluded from organization it's not being displayed in the column settings for lines

Accounting fields inputs:
* selectors
* full text search by code and description
* there is button "Next" when there are more than 10 values 
* search ignores diacritics

The list of the columns:
* Business item (default)
* Description (default)
* Accounting rule (default)
* Cost Center (default)
* Contract (default)
* Activity (default)
* Unit of measure
* Commitment type
* Cash document type
* Cash register
* Contra Account (MD/D)
* Employee
* Payment method
* Use the VAT reduction coefficient
* VAT control statement line
* VAT fixed assets (VAT line 47)
* VAT return line
* VAT reverse charge code
* VAT supply mode code
* Vehicle


> [!NOTE] Fixed columns
> There are several columns that can not be found in columns settings as they are fixed in their order and can not be moved around:
> * VAT type (has sorting)
> * Amount (has sorting)
> * Price per Unit (has sorting)
> * Total amount (has sorting)
> * Measure unit (only for Orders) (no sorting)


==**VAT type==
Can not be empty

Selector with three options (Czech legislation).
* Basic (21%) (default value)
* Reduced (12%)
* Exempt (0%)

To see the other supported country legislations go to [[Legislations]]
Organizations that are not VAT payers don't have VAT type column. Detailed info about not VAT payers can be found in [[Not VAT payer organizations]]

==**Amount

By default has value 0,0000 (can contain 4 decimals)

==**Price per Unit

By default has value 0,0000 (can contain 4 decimals)

==**Total amount

Read only. But can be edited in case of Validation warning or error [[Document detail. Validations]]
Automatically calculated from Amount x Price per Unit

==**Measure unit

- if the item has prefilled MU, it (MU) will be automatically filled on lines but it’s still possible to change it afterward
- ***is the default column only for Orders***
- is always displayed after the field “Amount”
- doesn’t have validation
- in items template as well

---

### Working with lines

##### Copy, Delete
* Each line has "Copy" and "Delete" buttons
* Buttons appear on hover or when the line is focused
* "Copy" button creates identical copy of the line with all values
* "Button" removes the line and the order of the lines is automatically recalculated
	* e.g. if you have three lines and you delete the second one, the third line automatically gets the order number "2"

##### Value stretch
* User can stretch the values in the columns to another lines (same as in EXCEL table)
	* it helps to copy the same value for the same column for other lines
* Stretching can be done vi dragging the right bottom corner of the cell 


##### Add item
* Button that adds a new line 
* If the total amount is filled: line will be added with corresponding amount, price per unit and total amount + VAT type
* if the document's total amount consists of the different VAT types - the separate line will be created for each VAT type
* if the total amount fully matches to the added lines, the next added line will be with Total amount = 0


> [!NOTE] Manual Outgoing Invoice and Order
> The lines are not automatically filled with amounts based on the total amount and recapitulation. It works vise versa: Total amount and the recapitulation are being filled on the base of the added lines, as this document kinds have recapitulation and total amount fields read only [[Document detail. Orders]] 

##### Add from spreadsheet
* Button that is hidden in the button selector
* Button opens the "Import" dialog window
	* 1. Export your template - "Export" button (exports template)
	* 2. Edit the exported file and save. The file must be saved in .xlsx format
	* 3. Select the modified file to import from the directory
	* Warning "Importing will overwrite all existing items."
	* Upload section with the text "**Upload a file by clicking** or dragging and droppingSelect the format .xlsx, .xls" 
	* Button "Import", not active when template is not selected
* The lines from the spreadsheet substitute the existing lines 

##### Add from template
* Button that is hidden in the button selector
* Button opens the "Pick template" selector
* Selector input is required and has validation for empty value
* Drop down displayed the list of the templates (10 per page)
	* each template is displayed with the name and the method of use
		* Values 
		* Percent 
	* Button "Next" is displayed to upload the further templates
	* full text search is implemented
* Button "Pick" is always active but it doesn't work when the template is not selected
* The lines from the selected template are being added to the existing lines

> [!important] Value vs Percent 
Value:
> * each line in template has certain selected amount, price per unit and total amount
> * the exact amounts are transferred to the document detail
> 
Percent:
> * each lines in template has only selected percent of the total amount (which is unknow)
> * when the template is applied to the document, lines will get the amounts based on the calculation of its percent from the total amount of the document and recapitulation
> * E.g. We have percent template with two lines with the Basic VAT type. We set 70% for the first line and 30% for the second. When we apply the template for the document that has total amount 1000 czk with the Basic VAT type - the first line will get the Total amount = 700, the second line Total amount = 300


Detailed info how manage lines template  can be found in [[Items]] in section #DocumentItemsTemplate 


##### Choose from the catalog
* Button that is hidden in the button selector
* Allows to select several items at once from the #CatalogOfItems 
* Opens the dialog window "Select an item from the catalog"
	* "Description" search field - search by code and description
	* "Supplier selector":
		* filters the items by Partner
		* values are displayed as Partner name, Address, ID, VAT
	* "Category" selector 
		* filters the items by category
		* values are displayed as code and description
	* Items:
		* for each document kind items displayed based on purchase/sale settings:
		    - Incoming Invoice: purchase
		    - Outgoing Invoice: sell
		    - Receipts: purchase
		    - Incoming Receipts: sell
		    - Orders: purchase
		    - Other: purchase and sell
		* checkbox (stick to the table)
		* Code
		* Description
		* Supplier
		* Category
		* Price without VAT
		* Currency
		* Quantity
			* number input 
			* default: 0.000
		* Measure unit
	* Pagination
		* 20 values per page is default
* Checked items will be added as the document lines with the total amount calculated on the base of the price per unit times quantity that user inputs in the dialog window


##### Delete all
* option hides in the kebab menu
* deletes all lines at once

##### Save as template
* option hides in the kebab menu
* opens the dialog window of  "Document items templates". 
	* template can be edited and saved. The same behavior as in [[Items]] #DocumentItemsTemplate 

##### Lines approval

Detailed info can be found in [[Document detail. Approval]]

##### Empty state

When there is no any line, the following things are displayed
* icon of the lines
* text "the document doesn't contain lines'"

#Registers 

##### Automatic document numbering
#AutomaticDocumentNumbering

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Kind of document" selector - required, tooltip "Select the type of document for which the number range can be used". Only three options:
	* Order
	* Outgoing Invoice
	* Contract
* "Description" input - is required, tooltip "The name of the number series in the code list in the form of manually created document"
* "Fixed part" input, is not required, tooltip "The fixed part of the number series in uncharged"
* "Counter" input, is not required, tooltip "The value from which to start counting the number series for the new document. For example, if you enter "3", the new document will have the values "4". If you leave it blank, it will start numbering from the last free number."
* "Alignment" number input , is not required, tooltip "Number of digits - if you enter eg "5", then the new document will have a number series in the format "00001". If left blank, the number of digits will be 1 and will automatically extend."
* "Fixed part's position" selector, tooltip "Position of the fixed part from the numerical one. It is most often used on the left":
	* On the left - is preselected by default
	* On the right
* "Create" button - creates register

**Search bar
* full text search by description, fixed part and counter

**Columns:
* Kind of document. 
* Description. Has sorting
* Fixed part. Has sorting
* Counter. Has sorting
* Recycle bin. Removes the register
---


##### Document Series 
#DocumentSeries

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is not required
* "Kind of document" selector, required
* "Invoice type" selector - can be empty (in this case created document series can be used for all invoice types )
* "Valid" checkbox - if true, register will be available throughout organization in  [[Document detail. Incoming Invoice]] 
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
* "InvoiceType" - is not required
* "Kind" - is required

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics
* When searching in the register, prioritize showing exact matches (from the beginning). Display priority:

1. Exact match
2. Starts with
3. Full text

**Columns:
* Code. Has sorting
* Description. Has sorting
* Kind of document. Has sorting
* Invoice type. Has sorting
* Valid
* Recycle bin. Removes the register
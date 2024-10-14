
### Outgoing invoice

When the button "Add document" is clicked dialog window "Document creating" appears
* "Document type" selector - current document type is displayed
* "Invoice type" selector - selected type will be displayed in the manual form, by default is Tax invoice
* button "Continue" - launches the manual form

##### Document data section

* "Invoice type" selector (required)
	* Tax invoice
	* Credit note
	* Debit note
	* Proforma
	* Tax invoice payment
* "Sequence" selector (required)
	* sequences can be managed in [[Number series]] #AutomaticDocumentNumbering 
* "Customer" selector (required)
	* Partner selection (full text search) #Partners 
* "Currency" selector (required)
	* by default organization's currency is selected
	* can be changed according to the selected partner
* "Variable symbol" text input
* "Description" text input
	* inside scroll
* "Date of issue" (required)
	* current date by default
* "UZP date" (required)
	* current date by default
* "Due date" (required)
	* 14 days from the current date by default
* "Date of case" (required)
	* current date by default


##### Lines

Line section is the same as in [[Document detail. Lines]]


##### Recapitulation

* Recapitulation net
	* cells are read only
	* Recapitulation net is filled with values based on the selected lines
* Rounding amount
	* read only
	* format is 0,00
	* filled with value based when the total amount has decimals and the button "Round" is clicked
	* when there is no decimals button is displayed as "No rounding"
	* when the rounding is selected button is displayed as "No rounding". It cancels the rounding
* Total amount (excluding VAT)
	* read only
	* format is 0,00
	* automatically calculated based on the recapitulation
* Total amount
	* read only
	* format is 0,00
	* automatically calculated based on the recapitulation


##### Accounting

The principle of work is the same as in [[Document detail. Accounting fields]]

##### Optional fields

The principle of work is the same as in [[Document detail. Custom properties]]


##### Buttons

* **==Create an invoice==**
	* active when all required fields are filled
	* when button is clicked "Generate PDF" dialog window appears
		* "Print template" selector
		* default template is selected
		* availability of the templates can be managed in [[Customization. Print templates]]
	* "Generate" button
		* contains image of PDF icon
		* generates PDF and creates an outgoing invoice
		* user is redirected to the document detail [[Document detail. Outgoing Invoice]]

* **==Save as template
	* active when all required fields are filled
	* when button is clicked "Create a document template" dialog window appears
		* "Name" text input (required)
		* "Save" button 
			* active when the name has value
	* template will save all values of the manual form beside the Accounting and Optional fields

* **==Load from template
	* is always active
	* when button is clicked "Document templates" dialog window appears
	* "Template" selector
		* placeholder "Select a template"
		* full text search
		* 10 items per page
		* "Show more" button is present when there are more than 10 templates
	* "Manage template" button
		* opens the list with templates
		* 10 items per page
		* each template can be removed via "Bin" button
		* "Show more" button is present when there are more than 10 templates
	* "Use a template" button
		* active only when template is selected
		* fills in the manual form with saved values

---

### Orders

When the button "Add document" is clicked dialog window "Document creating" appears
* "Document type" selector - current document type is displayed
* button "Continue" - launches the manual form

##### Document data section

"Sequence" selector (required)
	* sequences can be managed in [[Number series]] #AutomaticDocumentNumbering 
* "Supplier" selector (required)
	* Partner selection (full text search) #Partners 
* "Currency" selector (required)
	* by default organization's currency is selected
	* can be changed according to the selected partner
* "Description" text input
	* inside scroll
* "Date of issue" (required)
	* current date by default
* "Date of delivery" 
	* by default is empty
	* filled with the value automatically based on Partner's delivery period setting #Partners 
* "Place of delivery"
	* selector of  the registers #DeliveryLocations 
* "Contact person"
* "Contact person's email"
	* is automatically filled with current user's data

##### Lines

Line section is the same as in [[Document detail. Lines]]

##### Recapitulation

* Recapitulation net
	* cells are read only
	* Recapitulation net is filled with values based on the selected lines
* Total amount (excluding VAT)
	* read only
	* format is 0,00
	* automatically calculated based on the recapitulation
* Total amount
	* read only
	* format is 0,00
	* automatically calculated based on the recapitulation

##### Accounting

The principle of work is the same as in [[Document detail. Accounting fields]]

##### Optional fields

The principle of work is the same as in [[Document detail. Custom properties]]



##### Buttons

* **==Create an invoice==**
	* active when all required fields are filled
	* when button is clicked "Generate PDF" dialog window appears
		* "Print template" selector
		* default template is selected
		* availability of the templates can be managed in [[Customization. Print templates]]
	* "Generate" button
		* contains image of PDF icon
		* generates PDF and creates an outgoing invoice
		* user is redirected to the document detail [[Document detail. Orders]]]

* **==Save as template
	* active when all required fields are filled
	* when button is clicked "Create a document template" dialog window appears
		* "Name" text input (required)
		* "Save" button 
			* active when the name has value
	* template will save all values of the manual form beside the Accounting and Optional fields

* **==Load from template
	* is always active
	* when button is clicked "Document templates" dialog window appears
	* "Template" selector
		* placeholder "Select a template"
		* full text search
		* 10 items per page
		* "Show more" button is present when there are more than 10 templates
	* "Manage template" button
		* opens the list with templates
		* 10 items per page
		* each template can be removed via "Bin" button
		* "Show more" button is present when there are more than 10 templates
	* "Use a template" button
		* active only when template is selected
		* fills in the manual form with saved values

---


### Contract

When the button "Add document" is clicked manual form "Document creating" appears
* "Document type" selector (required) - current document type is displayed
* "Date of issue" (required) - current date is selected by default
* "Sequence" selector (required)
	* sequences can be managed in [[Number series]] #AutomaticDocumentNumbering 
* Supplier" selector (required)
	* Partner selection (full text search) #Partners 
* "Subject" text input 
	* inside scroll
* "Create" button 
	* is active when all required fields are filled
	* creates the Contract [[Document detail. Contracts]]
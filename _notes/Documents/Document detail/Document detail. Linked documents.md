
It is impossible to link documents when the document is locked or in the edit mode:
* button "+" disappears and "No linked documents" message is displayed (if there is no such)

### Manual linking

Button  "+" opens dialog window "Link documents":
* "Kind of document" selector
	* filters the document list according to the document kind
	* if the document kind is not selected documents of all kinds are displayed
* "Document" selector
	* has validation
	* documents are displayed as:
		* document number (Document kind: document type)
		* Partner name
		* Total amount
		* Date of issue
* "Link" button 
	* is active when the required fields are filled


### Automatic pairing

Automatic pairing works only for linking Orders with Incoming Invoices.
How the automatic pairing works can be found in [[Pairing]]


### Linked document view

When the document is linked it is displayed as:
* document number (Document kind: Document type)
* Partner name
* Partner address
* Partner ID
* Partner's local VAT number
* Total amount
* Date of issue


Each linked document has two buttons:
* button that redirects user straight to the linked document detail itself (in separate tab)
* Remove button (confirmation message)

**When the incoming invoice is linked with the order
* From the view of the ==incoming invoice document detail==:
	* Approval status
		* Approved
		* Not approved
		* Disapproved
		* Returned
	* Delivery status
		* Delivered
		* Partially delivered
	* Remains to deliver
		* calculated on the base of "Total amount without VAT" of the order minus "Total amount without VAT" of the incoming invoice minus "Paid by deposit" if such presented
		* amount is displayed with the currency of the document 
		* if invoice type is "Proforma" - remains to deliver is not being calculated 
* From the view of the ==order document detail==:
	* Remains to deliver

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
		* indicators if document is already linked and delivered in case of orders
	* "Advanced search" button
* "Link" button 
	* is active when the required fields are filled


 **Advanced search**
 Dialog window "Search document" appears:
* "Search" - filters by total amount, partner and document number
* "Document kind" filter
* "Invoice type" filter - appears when incoming or outgoing invoice is selected in "Document kind" filter
* "IC","DIC" chips -
	* are visible if corresponding fields are filled in
	* not active by default
	* when user clicks on them - they become active (IC/DIC number appears withing the chip) and filter launches
* "cross" button to cancel all active filters (is not visible when no filter is used)
* Table columns:
	* Partner
	* Total amount
	* Currency
	* Document number
	* Document kind
	* Document type
	* Invoice type
	* Creation date
* Pagination [[Pagination]]


### Automatic pairing

Automatic pairing works only for linking Orders with Incoming Invoices.
How the automatic pairing works can be found in [[Automatic pairing order with incoming invoice]]


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
		* when equals to 0 - is not being displayed
		* exists as the column only for order
* From the view of the ==order document detail==:
	* Remains to deliver
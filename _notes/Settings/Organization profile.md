Buttons: 
* Cancel (is always active)
* Save ( is not active unless changes are made)

##### "Organization settings" section:

* Description "Set details about your organization here"
* "Organization name" required field. User can insert custom name. 
* "Default application language" selector (each language is displayed in original language):
	* Czech
	* Slovak
	* English
	* German
	* Polish
	* Spanish
	* Romanian
	* Ukrainian
	* Vietnamese
* "State of VAT registration" selector. Can be preselected in [[wflow.com WIKI/Organization management/Organizations]] of Admin page or during New customer [[Onboarding]]. Countries are displayed in original languages.
	* Austria
	* Belgium
	* Czech Republic
	* Germany
	* Denmark
	* Greece
	* Spain
	* France
	* Hungary
	* Italy
	* Latvia
	* Luxemburg
	* Poland
	* Romania
	* Sweden
	* Slovakia
	* UK
	* Kosovo
	* South Africa
* "VAT Payer" checkbox. Can also be preselected during New customer [[Onboarding]]
	* when is true, organization has recapitulation
	* when is false, organization doesn't have recapitulation and several attributes. More detailed information can be found in [[Not VAT payer organizations]]
*  "Allow access to wflow.com support" toggle:
	* tooltip ("Allowing access allows wflow to access all information in the organization")
	

##### "Contact info" section

* Description "Fill in your organization's contact information"
* "Search by ID number or VAT number" search panel: #ARES 
	*  the same search panel can be found in [[Partners]]
	* search is carried out with the help of [[ARES]] service API 
	* when organization is found the following fields are automatically filled:
		* Legal name
		* Address
		* ID
		* VAT ID (if such registered, can not be in Not VAT payer organizations)
		* Bank account number (if such registered in ARES)
* Legal name. Can be automatically filled with ARES
* Address. Can be automatically filled with ARES
* ID.  Can be automatically filled with ARES
* VAT ID. Can be automatically filled with ARES
* Registration in business register
* Phone number
* Email address. Must be filled in order to send the #files

##### "Bank Connection" section

* Description "Fill in the details of your bank connection"
* Bank account number. Account + bank code. Can be automatically filled with ARES
* Currency selector. Is required field. When is empty it's impossible to save any other changes. Field has validation.
* IBAN
* BIC

##### "Documents settings" section (toggles)

*  Description "Advanced document behavior settings"

* "Allow approval on items":
	* tooltip - "Approvers of the document can also comment on specific items"
	* Items on the lines in document detail can be approved [[Items approval]]
	
* "Automatically sort documents into organizations": detailed info [[Automatic sorting to the organization]]
	* tooltip - "Documents can be automatically sorted based on the customer's ID within all organizations that fall under one customer account. The organization must have this option active. In the profile of the organization, you have filled in your ID number"
* Automatically match documents to a partner record
	* tooltip - ""
* Automatically pairing incoming invoices with orders
	* tooltip - "If you check, the action will take place if the order number, the supplier and the amount on the order and the invoice match"
	* when the toggle is turned on the following toggles unfold 
		* Only the order number should be taken into account when matching
			* tooltip - "The invoice is matched with the order only based on the match of the order number. The invoice is matches to the last order with the same number"
		* Automatically transfer billing numbers on the header to the received invoice
		* Automatically transfer items of paired order to incoming invoice
		* Automatically accept approval flow from order to incoming invoice
			* tooltip - "If you check, the invoice will be approved automatically if the order has already been approved" + *remark: order must be in status delivered as well*
		* Consider the amount for taking over the approval route
			* tooltip - "An invoice paired with an order will take approval from the order only if the difference between the amount of the invoice and the order does not exceed the set tolerance. The tolerance is automatically converted from the organization's main currency to other currencies according to the current exchange rate"
			* when is turned on the field appears "Tolerance for the difference between the order and invoice amounts to take approval from the order". By default the value is 0. CZK currency is displayed (even when organization's currency is different)
		* When the "Only the order number should be taken into account when matching" toggle is turned off the field is displayed "The tolerance of difference between the amounts of orders and invoices for automatic pairing". By default the value is 0. CZK currency is displayed (even when organization's currency is different)
		* More detailed information about pairing can be found here [[Automatic pairing order with incoming invoice]]

* Automatically transfer the last used accounting fields and cost objects to the document:
	* tooltip - "When checked, the last used cost objects and accounting fields will be transferred to the document if the previous document had the same partner and document type. It is used primarily when no accounting fields and cost objects are extracted"

* Use document creation date as date of acceptance 
	* tooltip - "If checked, the "Date of receipt' of the document will be automatically filled in with the date of its creation"
	* applies to Rossum as well

* Selection of number series at the document level
	* tooltip - "If checked, the number series will be optional in the Document Detail for each document separately. The current number series setting on Document Type will no longer respected"

* Automatically process data from [[ISDOC]]
	* tooltip - "Document metadata is automatically taken from the ISDOC file immediately upon acceptance into the application, and the document's processing status changes to "Extracted"
	* has additional toggle "Take over items"
	* has additional toggle "For an ISDOC without a PDF file, a template will be automatically generated"

* Automatically process receipts with QR code
	* only for Slovak legislation
	* tooltip - "For receipts  with a readable and valid QR code, the metadata will be automatically downloaded from the eKasa public portal (reading depends on the availability of the portal)"
	* has the addition toggle "Take over items"

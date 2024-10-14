
It is possible to upload/create document being in any folder

There is no default selected document type when document is being uploaded from the following contexts:
* Documents in "For approval" folder
* To review
* Comments
* All documents
* All approvals

There is default selected document type when document is being uploaded from the following contexts: (The default document type can be selected in [[Document types]])
* In each document kind in "To review" folder
* In each document kind in "All documents" folder

\When document is uploaded in the context of the specific document type, the current document type is selected

#### Document creating dialog window:

*The following description is for the kinds such as Incoming Invoice, Outgoing Invoice (not manual), Receipt, Income Cash Receipt, Contracts (not manual), Others*

* Document type selector (Required)
* Invoice type selector:
	* only for Incoming Invoice and Outgoing Invoice
	* if document type doesn't have assigned series with fixed invoice type -> tax invoice is default choice [[Document types]] [[Number series]] and possible to select other options:
		* Tax invoice
		* Credit note
		* Debit note
		* Proforma
		* Tax invoice payment
	* if document type has fixed invoice type - corresponding invoice type is preselected, impossible to change into another one
	* ISDOC - if document type has fixed invoice type ISDOC with other invoice type can not be uploaded to this document type
* "Browse device" button - allows to select files from the local device
* "Browse storage" button - allows to select files from the [[Storage]]
* "You can drag files here" - the are where files can be dragged and dropped (some clients drag files directly from emails)
* "Create" button - is active when all required steps are done

*Manual Outgoing Invoice, Order*
Document creating dialog window for this kinds contains only:
* Document type selector
* Invoice type - only for Outgoing Invoice
* Button "Continue"


*Manual Contract*
* Document type selector - required
* Date of Issue selector - contains inserted calendar, required
* Sequence selector - required, can be created in [[Number series]]
* Supplier selector - the list of the #Partners that can be set in [[Contacts]]
* Subject input - description of the contract
* "Create" button - is active when all required fields are selected
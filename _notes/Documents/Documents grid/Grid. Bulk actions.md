

> [!info] Fast bulk selection with the help of SHIFT key
> In order to select/unselect multiple documents you can use SHIFT key:
> 	1. Select one document
> 	2. Press and hold SHIFT
> 	3. Select another document -> all documents between the selected ones are gonna be automatically selected/unselected as well
> 
> 


> [!important] 
> Bulk actions are always available with the full set (single actions always depend on the context of the document). Some selected documents can be unappropriated for the action that user wants to call. In this case, the requests for these documents gonna fail, while the rest documents will go successfully under the action.
> Detailed information about failed requests can be found here [[Error notifications]]
> 

> [!warning] Dependency between the actions and workflow automations
> * Certain flow actions are not going to be available in single and bulk actions if the corresponding action is turned off in the workflow [[Workflow automations]]
>


> [!NOTE] Dynamic actions display
> Actions are linked to specific kinds, and if a selected document's kind does not match the action, the action is hidden.
> The check is performed not only based on the kind but also on what actions are allowed from a workflow perspective. If the selected list of documents includes one for which, for example, data extraction is disabled, then this option will also disappear from the list of actions.

+
### Restrictions (without user rights):

- merge - kind ISN’T SupplierOrder
    
- changeaccounting - kind ISN’T Contract
    
- documentsetasdelivered - kind IS SupplierOrder
    
- paypaymentrequest - kind IS IncomingInvoice OR OutgoingInvoice
    
- requestpayment - kind IS IncomingInvoice
---
#### Approve

* Confirmation message 
* Progress the approval for one level

#### Return
* Confirmation message
* Comment dialog window, where users/teams can be tagged (not required)
	* input "State the reason for the return", placeholder "Reason"
	* tooltip "This reason will be added as the comment to the item being processed"
	* button "Return"
* Returns the approval (approval process stops)

#### Reject
* Confirmation message
* Comment dialog window, where users/teams can be tagged (required)
	* input "State the reason for the rejection", placeholder "Reason"
	* tooltip "This reason will be added as the comment to the item being processed"
	* button "Reject"
* Rejects the approval (approval process stops)

#### Approval reset
* Confirmation message: Approval - Clear Status. Do you want to clear the approval status of selected items?
* Can be used when approval status is "Return" or "Rejected"


#### Return back to the previous level
* Confirmation message: Approval - Return back to the previous level. Do you want to return back the selected items to the previous level?
* Returns back the approval on one level


#### Set approval path
* Dialog window with approval path selector: 
	* full text search
	* possible to add additional level with users and teams
	* button "Set"

#### Remove approval path
* Confirmation message
* Removes approval paths

---

#### Lock
* confirmation message
* locks selected documents

#### Unlock
* confirmation message
* unlocks selected documents

---
#### Edit header accounting values
* this component allows to update accounting fields
* dialog window with accounting fields selectors:
	* if field is empty = none of the selected documents have selected value for this field
	* if field has a value = all selected documents have this value for the field
	* if field displays "Different values" = selected documents have different values for this field
	* it is possible to rewrite "Different values" but the action can not be canceled
	* Dot will appear beside the edited fields


> [!NOTE]
> * The set of accounting fields depends on [[Customization. Field settings for ERP]]
> * Accounting rules and payment methods of incoming invoices are available for Orders
> * PDP can be selected alone when VAT return line is empty
> * PDP can not be selected when selected VAT return line is not assigned for PDP [[Accountant]] #VatReturnLines 
> 


---

#### Update tags
* dialog window:
	* Add labels: select a label selector (full text search)
	* Remove labels: select a label selector (full text search)
	* inputs offer only existing tags
	* it's is possible to create a new tag in "Add label" section
	* if both inputs have the same tag, the selected is not going to be added to the documents
	* selected tags are displayed as the chips

---

#### Move documents #moveDocuments

* dialog window:
	* "Kind of document" selector
	* "Document type" selector, required, is being filtered according to the selected document kind
	* "Preserve document data" checkbox (it is possible to preserve data only for moving document between the main kinds (Incoming Invoice, Outgoing invoice, Receipt, Income Cash Receipt)):
		* is READ ONLY and TRUE when document is moved within the same document kind
		* is READ ONLY and FALSE when document is moved from the main kinds to Orders, Other and Contract
		* is EDITABLE when document is moved from the main kind to another main kind (Incoming Invoice, Outgoing invoice, Receipt, Income Cash Receipt)
		* when checkbox is FALSE, information message appears "Document data will not be preserved when changed. Data can only be saved when moving between invoices and receipts"
	* "Move" button

**What happens when document is being moved to another kind**:
1. all metadata will be removed (if preserve document data is FALSE)
2. all attachments will remain including the mark of the main file
3. event log remains + new event about change kind will be added 
4. impossible to move document to another kind in the middle of the approval process
5. this action can carried out only by Admin or user with the right to manage documents


**What happens when document is being moved to another type:
1. If the target document type has preselected accounting fields, they will not be assigned to the moved document

**Preserve document data:
1. it is possible to preserve data only for moving document between the main kinds (Incoming Invoice, Outgoing invoice, Receipt, Income Cash Receipt)
2. Data that will be preserved:
	1. metadata + lines [Link]([https://docs.google.com/spreadsheets/d/1aU4QfdIJDK-2n2dMa9_p7nAg7oN5zYkbhiitlpRL2-U/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1aU4QfdIJDK-2n2dMa9_p7nAg7oN5zYkbhiitlpRL2-U/edit?usp=sharing))
	2. approval path
	3. comments
	4. custom properties (if exits for the target kind)
	5. event log
	6. tags
	7. linked documents
	8. accounting fields (only those that not fixed to the certain kinds)
	9. flow status


> [!important] Flow status
> * flows status changes according to the workflow of the target document type/kind
> * in case of flows statuses Waiting for sending to extraction/ERP/Review - all requests must be killed and the status "Error sending..." must be set with the message "Request can not be finished, document kind is changed"

* Outgoing invoice with status "Sent by email" will change its status to the "Filled" (when moved to another document kind with data preserve)
* If document is in Rossum, it will be moved in Rossum as well with updated scheme (when moved to another kind with data preserve)


> [!NOTE] Moving to another kind from the context of All documents
> *  When mix kinds are selected - button "Move" is disabled + error message "Impossible to combine several kinds"
> 


---

#### Merge documents #mergeDocuments


> [!info] 
> It is possible to merge documents from different document types and kinds
> 


> [!important] Title
>Impossible to merge locked documents
>


Select on the grid documents you want to merge and select which file gonna be the main one. 
Here are the rules how files are displayed during the merge:

* When there is Partner's name and the name of the file => display format is: "Partner, Main file name"
* When there is Partner's name + the name of the file and they are the same => display format is: "Partner"
* When there is Partner's name and there is no the name of the file => "Partner" is displayed
* When there is no Partner's name and there is the name of the file => "Main file name" is displayed


---

#### Download #download

[Prototype](https://www.figma.com/file/ZvvQRtlHHlnWYUvLMpY3xO?embed_host=share&kind=file&node-id=0%3A1&t=N5IxSY2a7OSBoG1t-1&type=design&viewer=1)

There are two options for the bulk download (radio buttons):

1. Main files only (Only download files marked as master file)
2. Main files including document attachments (Download all attached files)

Button "Download"

**Naming of the downloaded files**:

* Internal number +Partner's name + VAR symbol(if absent - document number) + Document type
* If some of the data is missing, then this part in the naming is being avoided
* if there is duplicates then file is being numbered as (1), (2)...
* this format is used for all download actions and for all three export methods of ISDOC 
* Exceptions is for Orders, Contracts and Others. Their naming format is:
	* Document number + Partner's name + Document type

**Download bar

* Download bar appears during the first download withing the new session. Download icon appears as well with the first download and it can be clicked in order to open the download bar
* Download bar contains:
	* Count of downloaded files
	* Download status: success, fail, downloading
	* Name of the file
	* The size of the file (number + Kb, Mb)
	* Pause button (if the downloading process is still going on). It cancels the download, impossible to resume. Status fails and "Canceled" message appears
	* Download scale bar with percentage (if the downloading process is still going on)
	* If file is waiting its queue, there is the message "in line"


---


#### Delete documents #deleteDocuments

* Impossible to delete locked documents
* Confirmation message appears if the user really wants to delete selected documents: YES and NO buttons
* Deleted documents are being moved to the #RecycleBin
* Documents can be restored from the Recycle Bin, this action will be logged in the document events. Detailed information about document restore you can find in [[Recycle Bin]]
*


> [!important] Delete of the document type
> * Clients very often complain that they can not remove the whole document type even when the document type doesn't contain any documents.
> * The problem is that Recycle Bin can contain removed document from the document type the client wants to delete.
> * In this case, removed documents must be restored back to the document type and moved to another document type. After these steps document type can be rdeleted


---

#### Unlock and delete in one step 

When user has rights to delete and unlock documents, he can do both actions in one step (system doesn't allow to delete locked documents)

1. When locked and unlocked documents are selected:

Dialog window "Remove":
* message "Some of the selected documents are locked. To delete locked documents, confirm that they are unlocked."
* checkbox "Delete locked documents"
	* false - removes only unlocked documents -> intelligent error message about locked document will appear, text adapts to the single or plural form
	* true - unlocks locked documents and removes them
* button "No" - cancels the action
* button "Yes" - removes the documents

2. When only locked documents are selected

Dialog window "Remove":
* message "The selected document/s is/are locked. Deleting the document/s will unlock it/them and then move it/them to the trash."
* checkbox "Delete locked document/s"
	* false - disables button "Yes"
	* true - unlocks locked documents and removes them
* button "No" - cancels the action
* button "Yes" - removes the documents if checkbox "Delete locked document/s" is true

3. When user doesn't have right to lock/unlock documents

Dialog window "Remove":
* when locked and unlocked documents are selected:
	* message "Some of the selected documents are locked. Only unlocked documents will be deleted." 
* when only locked documents are selected:
	* message "The selected document/s is/are locked. You do not have sufficient permissions to unlock the document/s."
	* button "Yes" is disabled
* button "No" - cancels the action
* button "Yes" - removes the documents -> intelligent error message about locked document will appear, text adapts to the single or plural form

> [!NOTE] Kebab menu
>The following described bulk actions are hidden in the kebab menu


#### Set access #setAccess

Set access action is closely connected to the [[Users and permissions]] settings

When selected, dialog window "Add access" appears:
* description "Select the users you want to add access to the document"
* "Teams and Users" search bar + selector
* Full text search by User/Team name and email/description
* Users are displayed first then teams (icon, name, description)
* Selected user/team is added to the access. It can be removed by clicking on the cross
* For now the list is not decreasing by already selected users/teams
* Added user/team is displayed as the name only without email or description
* Button "Cancel" and "Confirm"

> [!warning]
> Access that is set via bulk action rewrites the access settings of each document. It means if document had access for User1 and User2 is selected via bulk action => User2 will replace the User1


---

#### Send for automatic data extraction

---

#### Send for review

---

#### Send for ERP

When the document has an approval path that is not completed yet special warning should appear (it's only a warning, document still can be sent to ERP)
	* "This document has not yet been approved" (for single actions on the grid and in document detail)
	* "Some documents with an approval path do not have completed approval" (for bulk actions)
	
---

#### Mark as Sent to ERP #markAsSentToERP

Works only for documents that were already sent to ERP

Dialog window with warning message appears when the action is selected:
 "By ticking, you change the status of the document to "Sent to ERP". This promotion is non-refundable" + Information "Suitable for manual entry into ERP, the document will no longer be able to be sent"
 * "Cancel" button
 * "Mark as Sent to ERP" button

---

#### Create time stamp

Stamps the main files

---

#### Mark for payment #markForPayment 

Dialog window appears:
*  "Date". Date picker to set the date for the payment
* "Use due date first if valid" checkbox - set the due date for payment if it's no in the past
* Number of documents count
* Amount: the total sum of all selected documents
* button "Mark for payment"

When document is marked for payment:
* payment order status is changed
* payment order is created in document detail

---

#### Pay #pay 


> [!important] Bulk payment
> Bulk payment considers payment via bank API. Not only documents that are marked for payment can be paid.

Detailed information how to connect bank account to wflow and how to manage bank connection can be found in [[Bank connections]]

Supported banks:
- Ceska sporitelna
- FIO banka
- CSOB
- KB
- 
Dialog window appears:

* "Payment from account" selector:
	* default account is automatically selected
	* account balance is displayed
	* other account can be selected
* "Date of pay". Three chips are available and clickable:
	* Own, Due date, Today
	* the last selected option is memorized for the further payments (only "today" and "due date")
* Main file preview
* Payment order status
* Date of pay. Date picker. Can be set according to the selected chip
* "Amount". Can be edited
* Currency
* Recipient
* IBAN
* Variable symbol
* Constant symbol
* Specific symbol
* "Message for recipient" text input
	* input value depends on selected chip (the last choice is memorized):
		* "Document description" - field inherits description of the document (validation for 140 symbols max.)
		* "Custom" - empty input with the placeholder "Write a message for the recipient"
* Recycle bin
* "Total to be pay": amount + currency
* "Mark as paid" - ignores payment via bank API, just marks the document as paid
* "Pay by transfer": contains two buttons:
	* 1. "Pay by transfer" - if all conditions are correct, user is redirected to the third party banking page.  When payment is being processed the dialog window with pending info is displayed "Confirming your payment, please wait"
	* 2. "Export ABO"
		* has validation on filled account number in Organization profile (when there is no Bank API connection):
			* when account number is not filled - account number field is highlighted with red in bulk payment dialog window and there is tooltip on hover "Fill the account number in Settings-> Organization profile to export ABO" and button "Export ABO" becomes red
		* supports only CZK payments 
			* when another currency is selected:
				* validation within bulk payments dialog window appears (when there is bank API connection)
				* validation appears in dialog window of "Export ABO", "Confirm" button is disabled
		* dialog window appears "Export ABO"
			* Batch date (date picker)
				* current date is selected by default"
				* impossible to select date in the past
			* Toggle "Mark invoices as paid" - is false by default
			* Button "Cancel"
			* Button "Confirm"
			* Dialog window has close button
		
***Validations

* When IBAN belongs to not VAT payer or is not found in VAT register the corresponding validation message appears beside the IBAN (appears immediately). 
* When IBAN belongs to the unreliable VAT payer


* Validations that appear after the button "Pay by transfer" is clicked:
	* Amount. When is 0 or less
	* Currency. When is not filled
	* IBAN. When is not filled
	* VS. When is not filled
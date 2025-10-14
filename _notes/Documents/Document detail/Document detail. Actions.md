
Can be found in kebab menu on the top right corner


> [!important] 
> Single actions always depend on the context of the document. Several action can be not available if the flow or lock status don't correspond to the action

> [!warning] Dependency between the actions and workflow automations
> * Certain flow actions are not going to be available in single and bulk actions if the corresponding action is turned off in the workflow [[Workflow automations]]
>

#### Set approval path

* dialog window appears with the selector
* approval path in selector can be managed in [[Approval paths]]
* full text search
* when approval path is selected, all level with all approvers are displyed
* it's possible to change the order of the levels using drag and drop and add new level with new approvers using button "+"
* it's impossible to edit the approvers in predefined levels
* button "Set". When clicked, approval path is assigned to the document
* action is available only when document doesn't have assigned approval path and when is unlocked
---


#### Remove approval path

* confirmation message appears
* action is available when document contains approval path and when is unlocked
---


#### Move document #moveDocuments 

dialog window:
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



---


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
---


#### Send for automatic data extraction

---

#### Send for review

---

#### Send for ERP

* When the document has an approval path that is not completed yet special warning should appear (it's only a warning, document still can be sent to ERP)
	* "This document has not yet been approved"
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

#### Sign
---

#### Linked documents 

Allows to manually link any document
* Document kind selector
* The list of the documents:
	* document number (Document kind: document type)
	* Partner name
	* Total amount
	* Date of issue

When document is linked, its possible to go straight to the linked document or delete it

---


#### Download #download 

Downloads all the files: main and attached ones

---

#### Copy #copy

Dialog window appears with the message
"The following parts are transferred to the copied document:
	* Document header
	* Document items
	* Accounting"

User is redirected to the document detail of the copy

---

#### Delete #deleteDocuments 

Deletes the document
Confirmation message appears

* user gets redirected to the documents grid after document removal if automatic transition is turned off

---

### Set as delivered #setAsDelivered

Available only for orders when the order is confirmed
Available when document is locked
Changes flow status of the order into "Delivered"
When action is selected, blue button appears with corresponding status and selector:
* Cancel delivery

### Mark as partially delivered

Available only for orders when the order is confirmed
Available when document is locked
Changes flow status of the order into "Partially delivered"
When action is selected, orange button appears with corresponding status and selector:
* Cancel delivery
* Confirm delivery
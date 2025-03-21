
### General info

* Changes that are made in document detail reflect in the event log
* Each log record displays:
	* name of the action
	* date and time when the action was carried out
	* name of the user who carried out the action:
		* can be user name
		* Rossum
		* wflow support
		* wflow automation
	* the field and the value that were changed
* Event card by default displays only two events, to see the rest actions you have to click on “show more". "Show more" contain the number of hidden actions
* Unfolded record can be folded via button "Hide"

### Events

###### ==Created== 
* when document is created

###### ==Updated==
* when document is updated
* displays the field and the value that were updated
* each custom property is always displayed as separate log even when they are edited at once but without specific details
* editing recapitulations:  log shows new total amount and quantity of edited VAT types
* editing lines: log shows:
	* the quantity of edited lines, 
	* number of the line + the description of the item (if it is filled)
	* action: edited, added, removed
	* field and the value
* when flows status is updated - corresponding icon is displayed


###### ==Deleted==
* when document is deleted

###### ==Restored
* when the document is restored from the bin

###### ==Approved
* when one of the level is approved
* also displays how many levels are approved out of the general quantity

###### ==Unapproved
* when one of the approved, rejected, returned level is reset
* in event log is displayed with the name "Not approved"
* also displays how many levels are approved out of the general quantity

###### ==Locked
* when the document is locked

###### ==Unlocked
* when the document is unlocke


###### ==Rejected
* when the document is rejected
* displays "rejected" icon, levels

###### ==Returned
* when the document is returned
* displays "returned" icon, levels

###### ==Returned back
* when the approval is returned to the previous level
* displays levels

###### ==File added
* when the new file is added
* displays the name of the file

###### ==File deleted
* when the file is deleted
* displays the name of the deleted file

###### ==Task added
* when the document is sent to Extraction, ERP

###### ==Task processed
* when the document is successfully sent to Extraction and ERP


###### ==Change property
* when the custom property is changed
* displays the name of the property and value
* goes along with the "Updated" record

###### ==Time stamped
* when the document is time stamped

###### ==Signed
* when document is signed via electronic signature (not Signi)

###### ==Add document payment request
* when document is marked for payment\

###### ==Delivered
* when the order is marked as delivered or partially delivered

###### ==Deliver canceled
* when the delivery of the order is canceled

###### ==Sent by email
* when the document is sent by email (manual outgoing invoice, order, manual contract)
* displays: receiver's email address, subject, message, attached files

###### ==Changed kind
* when the document is moved to another document kind

###### ==Sent for signing to Signi
* when the contract is sent to counterparties

###### ==Confirmed
* when the document is Confirmed (manual outgoing invoice, order, manual contract)
* "Flow status - filled" icon is displayed

###### ==Unconfirmed
* when confirmed document is revised
* "Flow status - new document" icon is displayed

###### ==Document approval setting
* when approval path is assigned

###### ==Delete approval path on the document
* when approval path is removed

###### ==Added payment
* when the document is paid

###### ==Payment order added
* when payment order is created

###### ==The payment has been deleted
* when the payment is removed

==Merged with the document (39)
* when documents are merged
* displays documents that were added:
	* document type name
	* document number

==Linking documents
* when the documents are linked (e.g order with incoming invoice)
* displays:
	* \<Kind>\<Number of the linked document>
	* with each update the whole bunch of linked documents is displayed

==Access updated
* when the access is updated manually or via workflow automations
* displays the whole list of the actual users/teams with the access to the document 
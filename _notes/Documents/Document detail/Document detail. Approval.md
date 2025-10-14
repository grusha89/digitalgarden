
##### Approval path assignment

Approval path can be assigned via [[Document detail. Actions]] or via the button "Set approval path" in the section Approval path. 
Process of the assignment is totally the same

dialog window appears with the selector
* approval path in selector can be managed in [[Approval paths]]
* full text search
* when approval path is selected, all level with all approvers are displyed
* it's possible to change the order of the levels using drag and drop and add new level with new approvers using button "+"
* approvers added via button "+" have icon of recycle bin, they can be removed until the changes are saved
* it's impossible to edit the approvers in predefined levels
* button "Set". When clicked, approval path is assigned to the document
* action is available only when document doesn't have assigned approval path and when is unlocked


##### Approval process

* the name of the approval path is displayed
* levels of the approval are numbered
* Approvers (users or teams) are displayed
* Plus button:
	* to add new levels 
	* change the order of the levels

Approval button options:
* Approve
* Reject
* Return
* Return back to the previous level
* Approval reset
###### Single approval path
*(When one level contains only one approver)*

When approval path is assigned "Approval" button appears:
* initial state - blue color "Approve" button
* When "Approve" button is clicked:
	* the first level becomes approved
	* user name of the approver appears
	* the level number turns into tick and becomes dark blue
* When "Reject" button is clicked:
	* dialog window "Reject" appears with the input "State the reason for the rejection" and tooltip "The reason will be added as a comment to the item being processed"
	* placeholder "Reason"
	* user can be tagged using "@"
	* stated reason will be displayed as comment in [[Document detail. Comments]]
	* Button "Reject" becomes valid when the reason is input.
	* It's impossible to reject without stating the reason
	* Level is rejected, approval can not be continued
* When "Return" button is clicked
	* the same dialog window appears as in for Reject action
	* button "Return" is always active
	* it is possible to Return approval without stating the reason
	* Level is returned, approval can not be continued
* Approval reset
	* is available only when approval is returned or rejected
	* cancels the rejected and returned status, approval can be continued
* Return back to the previous level
	* is available when at least one level is approved
	* dialog window is the same as for Reject and Return
	* Button "Return" is always active
	* it is possible to Return back to the previous level  without stating the reason
	* Approved level is canceled


###### Parallel approval path

* Each level can contain more than one approver
* Level is completely approved when all approvers approved
* Approval process is the same as for single approval path
* When "Return to the previous level" is selected the whole level is canceled (not only the last approver)
* The order of the approvers doesn't matter, approvers can approve the level parallelly 

###### Lines approval
#LinesApproval

* Can be turned on/off in [[Organization profile]]
* when approval path is assigned, each line obtains checkbox "Approve"
* lines that are selected will be approved (rejected, returned) along with approved (rejected, returned) level:
	* when approval action is carried out, checkbox disappears and corresponding icon appears with the name of the Approval
* when approval is reset, the latest rejected/returned line obtains checkbox again
* when the approval is returned to the previous level, the lates approved lines obtain checkbox again
* when approval is complete, checkboxes of not approved lines disappear
* when document is locked. checkboxes of not approved lines are not available


###### Approval with errors

* it is possible to not allow for certain level to approve when the document contains errors. This option can be set in [[Approval paths]]
* when the document contains an error button "Approve" becomes disabled and there is tooltip on hover "Cannot be approved - the document contains errors" and approval checkboxes on lines disappear
* error must be fixed in order to approve

###### Approval and lock status

* it is impossible to approve when document is locked
* when document is locked, button "Approve" becomes disabled and there is tooltip on hover "Locked document cannot be approved" and approval checkboxes on lines disappear

###### When approval is not completed

When the document has an approval path that is not completed yet special warning should appear (it's only a warning, document still can be sent to ERP)
	* "This document has not yet been approved" (for single actions on the grid and in document detail)
	* "Some documents with an approval path do not have completed approval" (for bulk actions)


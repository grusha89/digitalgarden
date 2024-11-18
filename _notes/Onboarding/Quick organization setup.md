
Quick organization setup launches when user opens the brand new organization:
1. when organization is created after new customer onboarding
2. when Admin created new organization via [[Organizations]]

### Setup process

1. When user goes to the organization that was recently created:
	* He appears on the All documents page and the dialog window "Set up your organization in 4 simple steps" appears:
		* Robot image
		* "Set up an organization" button
		* "Skip the setup wizard" button
2. When user selects "Set up an organization"
	* user is redirected to the setup page
	* on the top there is the setup flow stages:
		* Organization
		* Users
		* Control
		* Approval
		* Summary
	* the current stage is highlighted
	* if the stage contains several steps, user can see the loading circle bar 
	* if the stage is passed it's ticked

#### Organization 

Automatic search works only for CZ and SK organizations. The corresponding country legislation must be selected on customer's creation page. If CZ legislation is selected then SK organization are not going to be found and vice versa

**==Step 1==**
IC or DIC organization
"Enter IC or DIC" input and "VAT payer" checkbox:
* "VAT payer" checkbox is true by default
* Becomes true/false and read only automatically based on the searched organization 
* When the IC or DIC of VAT payer is inserted, found organization's data is displayed:
	* legal name
	* address
	* legislation country
	* IC
	* DIC
	* green box if result is valid
* When the IC of not VAT payer is inserted found organization's data is displayed:
	* Name
	* address
	* legislation country
	* IC
	* green box if result is valid
* When invalid IC or DIC is inserted:
	* Subject not found - please check the entered IC or DIC
	* red box

Button "Continue"

==**Step 2**

What accounting system do you use?
"Select an accounting system" selector:
* Money S3
* Money S4/S5
* Pohoda
* PREMIER
* Dynamic 365 Business Central
* Vario
* Other (selected by default)
* Not determind
* None

Selected option will be displayed in organization settings

Buttons "Back" and "Continue"

**==Step 3**

What documents do you process?
The list of document kinds is displayed. Each kind has its own image and checkbox that includes/excludes the kind for organization
* Accepted invoice (doesn't have checkbox)
* Invoices issued
* Bills
* Income cash receipt
* Orders
* Contracts
* Other

Buttons "Back", "Continue"

#### Users

Invite your colleagues to "organization name" 
"Enter new user's emails" (tooltip on hover: Separate email addresses with a comma):
* has a validation for invalid format
* added emails are displayed as the chips

Buttons "Back", "Continue"


#### Control

Who will control the mined data?
By checking, you can verify that the data from the document has been extracted correctly and you can also make manual adjustments

"Specify the users who will have access to the review":
* current user's email is selected by default
* clicking on the input shows other users' emails that were added during the "User" stage
* selected emails are displayed as the chips

Buttons "Back", "Continue"


#### Approval 

==**Step 1

Do you have approval processes in your organization?
Example of an approval process: Managers must approve the reimbursement of an invoice before it is paid

Buttons:
* Yes
* No

If Yes is selected:
* user will continue with the step 2
* default approval path will be created in organization

If No is selected:
* user will continue with the "Summary" stage

Buttons "Back", "Continue"

==**Step 2

Can all users in your organization approve documents?

Buttons:
* Yes
* No

If Yes is selected:
* user will continue with the "Summary" stage


If No is selected:
*  user will continue with the step 3


Buttons "Back", "Continue"


==**Step3

Who approves documents?
Create a single-level or multi-level approvals. Users at the same level are interchangeable and it is enough if only one approves the document (from Olga: this text described incorrect logic)

"Select users who can approve documents" input:
* The same input as for [[Approval paths]]
* by default: the first level is filled with the current user's email
* clicking on the input shows emails that were added during the "Users" stage
* possible to add more than one user on each level
* impossible to Continue if one of the inputs is empty

Selected users will have assigned teams according to its level and these teams will be the part of approval path 

Buttons "Back", "Continue"

==**Step 4

When do you want to approve documents?

Two radio buttons are offered:
* "Before checking the mined data":
	* You approve the document immediately after adding it to your organization. Then the document is sent to review the extracted data
	* if selected - on "Summary" stage and in workflow "approval" will be before "review"
* "After checking the extracted data":
	* You only approve the document after checking the extracted data.
	*  if selected - on "Summary" stage and in workflow "approval" will be after "review"

Buttons "Back", "Continue"


#### Summary

You have successfully set up your organization
Each added document is automatically submitted for mining data review, then waits for approval. After approval, you can export it to the accounting system.

Document flow is displayed:

Document -> Control -> Approval (position depends on Step 4) -> Accounting system

Info message:
"You can change or modify your organization settings at any time. For detailed information on settings, see [help center](https://support.wflow.com/en), and if you need help with anything, contact our user support"


Buttons "Back", "Complete"

When "Complete" is clicked user is redirected to the start page of the organization

---



#### What to check after setup

1. Organization info (Name, IC, DIC, address) is filled in "Organization profile"
2. That all selected users are added 
3. Users have Admin roles
4. Users are the part of the corresponding teams:
	* 1. approval level
	* 2. approval level and so on
5. "Approval" approval path is created and contains corresponding teams on corresponding levels
6. The documents types are created
7. Selected ERP system is selected in ERP settings
8. "Workflow 1" is created:
	* for Incoming Invoice, Outgoing Invoice, Receipt
	* All main sections are turned on and have automatic mode (Extraction, Data check, Approval, Send to ERP)
	* the order of Approval and Data corresponds to user's choice in Step 4 in Summary section


---

### Skip the setup wizard

User has an option to cancel the quick setup process and go directly to the organization and set everything up manually

1. When "Set up your organization" dialog window appears user must click on "Skip the setup wizard"
2. Then "Exit setup wizard?" confirmation message appears
	 * "If you exit the wizard now, you cannot return to it"
	 * button "End"
	 * button "Back to wizard"
3. User clicks on "End" button
4. Dialog window of filling IC appears:
	* Please fill in IC or DIC organization for the app to work properly
	* "Enter IC or DIC" input and "VAT payer" checkbox:
		* "VAT payer" checkbox is true by default
		* Becomes true/false and read only automatically based on the searched organization 
		* When the IC or DIC of VAT payer is inserted, found organization's data is displayed:
			* legal name
			* address
			* legislation country
			* IC
			* DIC
			* green box if result is valid
		* When the IC of not VAT payer is inserted found organization's data is displayed:
			* Name
			* address
			* legislation country
			* IC
			* green box if result is valid
		* When invalid IC or DIC is inserted:
			* Subject not found - please check the entered IC or DIC
			* red box
	* button "Save and go to organization" is valid when IC or DIC are inserted
5. When user click on "Save and go to organization" he appears on the All document page
6. Selected organization info is filled in "Organization profile"
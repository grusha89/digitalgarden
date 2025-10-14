
### The structure of the context navigation panel

* customer logo + current organization name
	* arrow down appears on hover
	* when organization name is clicked - organization selector opens up with the search panel 
	* search panel is autofocused
	* selected organization is ticked 
	* search panel has a placeholder "Search organization"
	* only twenty organization are displayed, the rest can found via search
	* on the bottom of the selector there is "Overview of organizations" that redirects to the [[Dashboard]]

* Search bar to find the needed folder, document type, any navigation folder
	* the first item in the list will be selected by pressing "Enter"
* Bookmarks - to reach quickly the frequently used folders, can be set via the [[context menu]] of the folder
* My tasks
* Documents
* Storage
* Finance
* Marketplace
* Settings
* External links
* [[Help]]
* [[User Account menu]]

### Navigation tree structure


##### My tasks

For approval
		* Documents
		* Storage
To review
		* Incoming Invoices
		* Outgoing Invoices
		* Receipts
		* Orders
Comments
Custom views [[Custom views]]

---

##### Documents

All documents
		* Incoming Invoice
			* document types [[Document types]]
		* Outgoing Invoice
		* Receipts
		* Income cash receipts
		* Orders
		* Contracts
		* Other
	* All approvals
	* Recycle bin


---

##### Storage
 
Folders
		* storage folders
	* All approvals
	* Recycle bin

---

##### Finance

Employee expenses
	  * Personal expenses
		  * Overview 
		  * Expenses
	* Employee expenses
	* Accounts and cards

Bank
	* Bank connection
	* Account movements


---

##### Marketplace

Marketplace
Active integrations
Designer


---

##### Settings

User name
	* Notifications
	* My profile

Organization name
	* Organization profile
	* Security
	* Users and permissions
	* Register administration
		* Cost objects
			* Cost centers
			* Contracts
			* Activities
			* Projects
			* Business cases
			* Vehicles
			* Employees
		* Number series
			* Document series
			* Automatic document numbering
		* Organization
			* People from the organization
			* Delivery locations
		* Contacts
			* Partners
			* External people
		* Accountant
			* Accounting rules
			* Chart of accounts
			* VAT return lines
			* VAT control statement lines
			* VAT reverse charge codes
			* Commitment types
		* Items
			* Catalog of items
			* Catalog category
			* Document items template
			* Measure units
		* Payments
			* Cash registers
			* Cash document types
			* Payment methods
	* Approval paths
	* Document types
	* E-mails
	* Customization:
				* Optional fields
				* Appearance
				* Field settings and validations
				* Print templates
	* Integrations
				* API accesses
				* Extraction
				* ERP
				* Export
				* Signi
	* Workflow automations


---

##### External links 
 custom links that can be created in [[Account settings]]


---

### Navigation behavior

**Default state** – the workspace navigation (contextual, e.g., Documents, Storage, or Finance) is closed.

**When the page is reloaded** (e.g., F5 or browser refresh) – navigation menu appears immediately with loading skeleton, the last state is remembered.

**When clicking a link in the navigation panel** (that changes the context) – redirection occurs and the workspace navigation opens.

**When clicking a link within the same context as the current one** – the navigation opens.

**When redirected (without interacting with the navigation panel) to a different context** (e.g., Search) – the navigation opens.

**When redirected (without interacting with the navigation panel) to the same context** (e.g., Search) – the navigation does not open.

**When manual document creation form is opened** - the navigation panel collapses
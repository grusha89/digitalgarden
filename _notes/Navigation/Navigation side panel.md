
### The structure of the navigation panel

##### Header

* customer logo + current organization name
	* arrow down appears on hover
	* when organization name is clicked - organization selector opens up with the search panel 
	* search panel is autofocused
	* selected organization is ticked 
	* search panel has a placeholder "Search organization"
	* only twenty organization are displayed, the rest can found via search
	* on the bottom of the selector there is "Overview of organizations" that redirects to the [[Dashboard]]

##### Navigation panel tree structure


1. **My tasks
	* For approval
		* Documents
		* Storage
	* To review
		* Incoming Invoices
		* Outgoing Invoices
		* Receipts
		* Orders
	* Comments
	* Custom views [[Custom views]]
2. Documents
	* All documents
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
3. Storage
	* Folders
		* storage folders
	* All approvals
	* Recycle bin
  4. Employee expenses
	  * Personal expenses
		  * Overview of cards
		  * Expenses
	* Transaction
	* Accounts and cards
5. External links
	* custom links that can be created in [[Account settings]]
6. Settings
	* Marketplace
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
		* Notifications
		* Settings
			* My profile
			* Organization profile
			* Security
			* Users and permissions
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
				* Bank
				* Signi
			* Workflow automations



#### Navigation side panel behavior

1. When of the section is clicked and the subsections are not visible enough - auto scroll launches 
2. It's possible to click with mouse roll - the section opens in the new tab
3. The navigation panel width is based on the display width
	* min. width -260px, dynamic due to display width is 18%, max. width is 400 px
4. To solve the problem with navigation width - there is a restriction on document type name (max. 35 symbols)
5. Navigation panel and document detail
	* default state: navigation on the grid/document detail is opened
	- changes are saved in the scope of local storage
	- navigation state in document detail is not affected by the navigation state on the grid and vice versa
6. Badges are hidden for unfolded sections. For example section "To review" looses its badge when it's unfolded
7. Folded and unfolded states are saved to the database associated with their user profile, with each saved state having an 'expiration' date set to 30 days from the current date.
8. Users can resize the navigation bar between a minimum of 200px and a maximum of 400px.
9. Automatically hide the navigation bar when its width is reduced to 200px or less.
10. resizing actions and button toggles store the current width and visibility state in local storage to maintain consistency across sessions.


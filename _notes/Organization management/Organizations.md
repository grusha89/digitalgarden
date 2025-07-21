
* Search bar
	* full text search by organization name

* Table
	* Name
		* organizations are listed in alphabetical order
	* Domain (redirects to the organization)
	* Pricing plan
	* Active
	* Deposit
	* Copy
	* Delete

*  [[Pagination]]
	
### New organization

Dialog window appears:

* Organization name (required)
* Domain (required)
	* must be unique
	* will be the part of organization URL
	* URL is displayed, reflects the changes immediately
* State of VAT registration
	* selector of available country legislations [[Legislations]]
	* Czech Republic is by default
* Add an administrator
	* tooltip "Add the emails of users who should access the organization as administrators. You can also add users later in the organization settings"
	* required
	* added users are displayed as the chips
	* current user email is automatically added
* Pricing plan
	* tooltip "Select the appropriate organization pricing plan. If you are unsure about which plan to choose, please contact our sales department"
	* radio buttons:
		* Mini
		* Profi (selected by default)
		* Business
* Create backup data for download
	* tooltip "Regularly prepare a complete backup for download at the turn of the month. The backup contains ISDOCX files with document metadata, all attachments, audit trail, comments, approval history and more. The file is saved as a .zip in the wflow-backup folder in the repository. The feature is paid. Please contact our user support for more information"
	* toggle
* Save button
	* active when all required fields are filled

### Edit organization

Fields that are not editable anymore:
* Domain
* Pricing plan

New toggle appears
* The organization is active

"Add an administrator" is not displayed anymore

### Copy organization

User can select one of two options that are displayed as the radio buttons:
1. Copy settings (Creates a copy of the organization with the same organization settings (users, approval paths, and more))
2. Copy settings and data (Duplicates the organization, including the organization's settings and data (documents, files in storage, code lists, and more).)

* Organization name is copied (can be the same is not required to be unique)
* Domain is empty (must be unique)
	* is auto filled when user inputs new organization name
* Legislation is read only
* Pricing plan can be changed
	* plan "mini" is not selectable
* Create backup data can be edited

Warning dialog:
- The **warning dialog** that appears when attempting to close the window during the copying process has different text and red color than usual warning dialog:
	- Copy is not finished (Closing the dialog will stop the copying)  
- The **confirmation dialog** (displayed when trying to close during copying) should **automatically close** if the copying process finishes **before** the user makes a choice (clicks anything).
- During the copying process, **all input fields** must be **disabled**.
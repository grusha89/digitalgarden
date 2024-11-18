Dashboard is the overview of all organization where user has the access to.


### Select an organization

* Customer's logo (by default there is wflow logo)
* When "Select an organization" is clicked - search panel with the drop down list appears
* Search panel
	* placeholder "Search organization"
	* full text search
	* when nothing is found - "No organization" message is displayed
	* drop down list displays only 20 organizations in alphabetical order
	* clicking on the found organization, user is redirected to the organization's home page. 

### Last organization

* The last opened organization is played on the top of the page


### List of organizations

* The quantity of organizations is displayed in the brackets
* Infinite scroll is implemented
* Organization is displayed by:
	* Organization name (is editable in Organization profile or in Admin page)
	* Organization's URL


### Search panel

* Search panel is located between the last organization and the list of organizations
	* placeholder "Search organization"
	* filters the list of organizations:
		* the list updates with each inserted/removed character
		* inserted value can be removed at once by clicking on the cross that appears in the input
	* when no results are found - "You don't have access to any organization" message is displayed instead of the list of organizations


### Settings

Allows user to select what organization data to display

**Pricing plan: 

Checkboxes have a strict order, it's impossible reassemble them
The name of the sections appears as the tooltip on hover

* Statistics for last month 
	* Documents: the quantity of the processed documents
	* Extracted (data is taken from Rossum): the quantity of documents extracted by Rossum
* Statistics for this month
	* Documents: the quantity of the processed documents
	* Extracted (data is taken from Rossum): the quantity of documents extracted by Rossum
* Storage
	* Used storage: used space in MB
	* Backup: yes/no

---
How to check Rossum statistics:
1. Go to elis.rossu.ai
2. Go the customer you need
3. Click on profile menu
4. Select Billing
5. Select "Usage"
6. Click on "Queues" and select the organization you need
7. Click on "Save"
8. Select radio button "Documents"
9. Select "Months"
10. Check the statistics for the current month and the last month
11. The same amount of documents must be displayed on the dashboard




**Document flow overview

The order of the sections can be changed via drag and drop
Each data has corresponding icon + the quantity of the documents
The name of the sections appears as the tooltip on hover
Each separate data has its own tooltip on hover: "Name of the data: quantity of the documents"
If the quantity of the documents equals zero, the data becomes light grey and is not interactable 

* My approvals
	* amount of documents that needed to be approved by me
* All approvals
	* all approval statuses (not approved, approved, returned, rejected)
* Validations
	* validation errors
	* validation warnings
* Flow status
	* new documents
	* Waiting to be sent to extraction
	* Sending to extraction error
	* Successfully sent to extraction
	* Extracted
	* Submitted for review
	* Reviewed
	* Waiting to be sent to ERP
	* Sending to ERP error
	* Sent to ERP
* Contracts
	* Contracts that had to be reviewed 
* Custom views
	* custom filters  that can be set in [[Custom views]]
	* custom views that have active badge are displayed on the dashboard

### Filters

Filters the organizations based on the selected conditions. Checkboxes
Name of the selected filter is displayed as a chip on the left side at the very beginning of the organizations list. It can be canceled by clicking on the cross of the chip
When checkbox is selected button "Apply filter" becomes active

* Documents for approval
* Contracts for review
* Submission errors
* Documents to review
* Comments to resolve
* Validation

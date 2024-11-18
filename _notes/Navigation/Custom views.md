

Custom views is the function that allows user to create his own folder that contains selected filters. It is located at the bottom of the "My tasks" section

"Add view" button

Each custom view in navigation has a context menu:
* Edit
* Delete
* Set start page [[Context menu]]

When the filters of the custom view launches:
* chips of the used conditions appear on the grid
* the main filter is turned on with the corresponding conditions

Custom views are displayed in the order of creation time

##### Own
"Create your own view. Make your documents easier to access with custom views"

* Icon selection. If not selected, abbreviation of the name will be instead
* "Name" input:
	* required
	* placeholder "E.g. Pay, Check..."
	* validation for being empty
* "Description" input:
	* optional
	* stretches
* "Display a label with the number of documents" checkbox
* "Add a condition":
	* contains the same component as filters [[Grid. Filters]]
	* selected conditions are displayed in the dialog window
* "Save" button:
	* is active only when changes are made
	* stays inactive if there is no condition added
* "Cancel" button:
	* warning about unsaved changes appears
	

##### Ready-made views
"Choose from ready-made views. You can customize the conditions for displaying documents in the next step"

**Returned and rejected documents:
* returned and rejected documents during approval*
* Condition: 
	* approval status equals to Declined OR Returned

**Approved invoices for payment:
* Approved invoices marked as outstanding
* Condition: 
	* Payment status equals Unpaid OR Partially paid
	* Approval status equals Approved

**No approval path
* Documents that do not have an approval path
* Condition: 
	* Approval path name equals Blank


**Submission errors
* Documents with a submission error status
* Condition: Flow status equals Sending to ERP error OR Sending to extraction error


### Custom views on the dashboard

* Custom views in the navigation panel can be displayed on the Dashboard too
* In order to display custom view on the dashboard it must have active badge
* On dashboard it will be displayed as the selected icon and badge count
* In Dashboard settings “Custom views” checkbox must be selected [[Dashboard]]
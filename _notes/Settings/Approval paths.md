Connected topics: [[Approval process]]

* Button "Add". Calls "New approval path" dialog window
* Search bar. Full text search by approval path name
* Column "Name". Has sorting 
* Button "Copy". Copies approval path with the original name. Name must be edited in order to save the copy
* Button "Remove". Removes approval path. Possible to remove approval path that is already assigned to the document

```
graphQL“: approvalPath { name } → approval { pathName } GET/api/{organization}/documents/{documentId}/approvals: template.name → name GET/api/{organization}/storage/files/{fileId}/approvals: template.name → name
```

##### "New approval path" dialog window

* "Name" - text input. Has validation that the input is empty and that is duplicated
* Dialog window has the warning about unsaved changes
* Button "Save" is active when changes are made and unique Name is filled


* " A document can only be approved without validations error" toggle #approvalWithErrors 
	* has selector "Select a level that cannot approve a document if it contains an error"
	* the selector displays the levels that are set in the approval path
	* the selector memorizes the level not the users
	* the selector has a placeholder "Select a level"
	* 
* "Approval path" section:
	* Input with level number:
		* Has a placeholder "Select a team or user"
		* Has a drop down list.
		* Has a full text search by the name and by description
		* The list contains users and teams: teams are displayed first, then users.
		* Teams and user have different colors
		* The list is expanded by clicking on the "Show more"
		* Scroll is inside the list
		* When user/team is selected it turns into chip. inside the input 
		* Multiple users/teams can be added to the one level
		* Chips can be removed by "cross"
		* Input has recycle bin in order to delete the level
	* Button +. Adds the next level input
	* All levels can be dragged and dropped between each other

* "Access" section:
	* Selector "Select a team or user":
	*  Has a full text search by the name and by description
	* The list contains users and teams: teams are displayed first, then users.
	* Teams and user have different colors
	* The list is expanded by clicking on the "Show more"
	* Scroll is inside the list
	* Already contains users/teams that are the part of the approval path. They can not be removed
	* Selected users/teams are displayed as the chips under the input
	* Chips can be removed by "cross" (only those teams/users that were added only for the access)

* "Storage" section
	* Button "Add folder". When is clicked dialog window "Pick folder" appears
	* Selected folder is displayed as the chip under the label "Folders". Chip can be removed
	

 

> [!Empty approval path]
>  It's is possible to save empty approval path (without any approvers). Such approval path is not going to be available in [[Workflow automations]] settings. Detailed information about the behavior of empty approval path on the document detail can be found in [[Approval process]]
>
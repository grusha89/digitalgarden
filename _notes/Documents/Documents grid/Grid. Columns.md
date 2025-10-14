
Each main folder has its own separate column settings:
* Documents in "For approval" folder
* Storage in "For approval" folder
* To review
* Comments #comments 
	* displays the icon with comments count + tooltip on the hover "Comments: 1"
	* if there are comments to resolve, red dot is displayed + tooltip on the hover "Comments to resolve: number"
	* when the icon is clicked, dialog window appear when the comment can be inserted and user can be tagged. The same behavior as in [[Document detail. Comments]]
* All documents
* Separate document kinds

Subfolders in the listed above main folders have the same column settings as their parent folder:
* if column settings are changed in the main folder -> changes apply to all subfolders
* if column setting are changed in the subfolder -> changes apply to the main folder and to the rest subfolders

##### Column settings dialog window
* Search bar - 
	* full text search, depends on diacritics, not case sensitive
	* searches only column names (not the names of categories)
	* search works by column key name as well
	* category unfolds if column name in it is being searched
* Columns selector:
	* Columns divided by categories
	* Each column has checkbox
	* When checkbox is clicked to be true -> corresponding column chip appears in the active list, it's being added to the end of the list and automatic scroll to the end of the list is being applied
	* When checkbox is clicked to be false -> the corresponding column chip disappears from the the active list
	* folded state of the categories is memorized and kept across the column settings of other document kinds and folders
	* folded state of the categories is not memorized during the session, if user closes the settings and opens again -> all categories would be unfolded again
* Active list: 
	* each columns goes as the separate chip with close button
	* columns can be dragged and dropped
	* column can be removed from the active side via close button -> corresponding checkbox in columns selection becomes false automatically
* Order of the columns applies to the order displayed on the grid
* "Default settings" button. Reset the columns to the default setting. 
	* Default setting is set in [[Customization. Columns settings]]

##### Sorting
Columns that don't have sorting:
* Accounting fields
* Special columns:
	* Approval status
	* Comments
	* Payment order status
	* Payment status
	* Lock status
	* Flow status
	* Links
	* Main file preview
	* Validation status
	* Tags
	* Custom properties

##### Column names

* Columns such as "Lock status" and "Comments" don't display its names on the grid

##### Stick to the table feature
It allows to certain elements to stay visible during the horizontal scroll:
* checkboxes 
* kebab menu

##### Persistence column width settings in database

* When the column width is changed it's saved in database
* Changes are saved only on URLs without UUID:
	* YES - https://apptest.wflow.com/org/6k-test/documents/list/kind/0
	* NO - https://apptest.wflow.com/org/6k-test/documents/list/kind/0/66eb9131-3b26-4c5f-badb-05c82ae68107
* Column width adjustments made by a user should be saved to the database with identifiers for the user, their organization, and the specific grid context (e.g., "Document grid," "File storage grid," or "To approval").
* The system must load and apply the user's column width settings from the database when any of the before mentioned grid views is accessed.
* Persistence of settings is available across sessions and devices, adhering strictly to the user's last saved preferences per grid view.

### Unique cases

##### Validation column

It’s possible to have an overview of the validations from the grid.
User must have active column “Validations” on the grid

When validation is clicked the dialog window appears with the list of validation warnings and errors that document has:
- validation cards must be in the same order as in document detail
- it’s possible to fold and unfold validation cards
- for duplicate validation: when user clicks on the duplicate document, document opens in the new tab
- validation cards have button “Solve”
    - it redirects user to the document detail and the corresponding field will be autofocused
- when document is locked button “Solve” is not visible


https://www.figma.com/design/9L5eiV91azH3SQMkJamfwk/Automation?node-id=1348-11669&t=gkRCSkMvIr0O9Zyi-0

### The grid

When the organization doesn’t have any workflow - the grid is empty and contains the text and “New workflow” button

- DEMO workflow is only for DEMO organizations. [[Demo organization]]
- Toggle changes its position (Aktivni/neaktivni)
- Description
- The user who last edited the workflow is displayed on the card (User name)
- The date of the last update is displayed
- Chips of selected document types are displayed

Logic:

1. The last updated workflow is displayed at the top
2. Copying workflow, the name is copied and the number is added one more time. Workflow 1 → Workflow (1) (1)

---


### New document section

- The name is automatically filled with “Workflow” + the corresponding number
- Description contains placeholder
- The first card is “New Document”
- When user clicks on “Select document type” - dialog window appears
- When extraction type is selected - non extraction types become read only
- PPD, Others - are in one group
- Order is separated
- Contract is separated
- Checkboxes states: ticked - when the whole document kind is selected, minused - when at least one document type within document kind is not selected
- Selected types/kinds are displayed liked the chips 
- Button “Plus” unfolds into menu: Approval and The further action
- Only the first Plus button is active
- When the Plus button is clicked, two options appear: Approval and Further action
- When Approval is selected: new card appears that by default has the chip “Manual”

---



### Approval section

- “Manual” is by default and read only. It changes to automatic as soon as approval path is selected.
- Default flow status is displayed
- Selector “Approval path: full text search works (not case sensitive, possible to search by any word, by last and the following letter)
- Dynamic approval path is not displayed in the list
- When plus button is clicked, dialog window of approval path creation appears
- Created approval path via plus button, immediately appear in the selector
- Conditions, operators and values are in the table below
- Buttons “Bin” :  removes added condition
- Button “Add condition”
- Button “Or” adds further conditions + by default flow status
- Kebab menu:
	- Copy (copies the whole bunch of the conditions)
	- Remove the bunch of conditions
- The button “Assign approval path” adds settings for another approval path. It is possible to select the same approval path
- Button “Cancel”
- Button “Use”
- Button "Close"

---


### Extraction, Review, ERP sections

- Toggles turn on/off the sections
- “Manual” chip is by default
- When the chip “Automatic” is on, “Advanced settings automatizations” appears
- When “Advanced settings automatizations” is clicked, the dialog window appears
- Corresponding Flow status is by default and not editable
- Conditions, operators and values  are in the table below

---


### New sections

- There is default corresponding flow status condition that is not editable
- New section by default always have “Automatic mode”. It can not be changed for manual
- The list of the action is not reducing along with selected actions. One action can be used several times within on workflow
- when plus button is clicked there are two options: approval and further action
- When approval section already exists in the workflow only “further action” is available
- When “further action” is clicked, the list of action appears:
- When action are carried out they do not influence on the flow status of the document:
	- for example in general scenario when user adds lines to the NEW DOCUMENT - document changes its status to "Filled". But with automatization to replace the lines - document will stay in status "new"

##### Update registers on the headers

- The value field of accounting is read-only
- Accounting and value fields are selectors. It has full text search, is not case sensitive
- There is VAT mode accounting field
- There is no connection between accountings fields in workflow and accounting fields in main settings (it means if in organization settings accounting field “Contract” is turned off - it will be available within workflow settings)
- If the workflow has the mix of document types - how accounting rules and payment methods are displayed? PRODUCT WILL DECIDE
- One register can be used multiple times
- the second selection of the accounting field appears automatically when the first input is filled. Can be saved as empty
- All conditions can be used for this section are in the table below
- Button “recycle bin” removes the corresponding condition
- Button “recycle bin”: when there are several conditions it will remove the corresponding one, if there is only one condition - it will empty inputs
- Button “Or” add another condition
- Button “Add the set of conditions” add another accounting conditions

##### Change document types

- Selector “Document type”: all types even from other kinds are displayed but action will work only for the document types within one kind (this principle will be in the description to this section)
- document type selector, full-text search, is not case sensitive
- All conditions can be checked in this section are in the table below

##### Replace the lines from the template

- Template selector: full text search, is not case sensitive
- all conditions can be used in this section are in the table below

##### Assign the tag

- tag selector: fulltext search, is not case sensitive
- all conditions can be used in this section are in the table below

##### Set the access to the document

- search bar for users and teams
- search by email, user name, team name, team description
- all conditions can be used in this section are in the table below

##### Change the description of the document type

* text input: it is impossible to save an empty description field or with spaces only
* it’s possible to insert dynamic dates

**Dynamic values can be inserted:

- manually, using the following forms
    {day} - the current day
    {month} - the current month
    {year} - the current year
    {day-vat-date} - the day of UZP date of the invoice
    {month-vat-date} - the month of UZP date of the invoice
    {year-vat-date} - the year of UZP date of the invoice
- from the selector clicking on {+}
---

### Not extraction kinds

* Workflows for orders and contracts are always isolated and can not be mixed with another kinds
* PPD and Others can be grouped into one workflow
* Even though workflow of Contract has similar structure to the workflow of PPD and Others, they can not be mixed due to the special flow status of Contract ("Not confirmed") while PPD and Others have status "New document"

Contract workflow:
1. New document
2. Data fill
3. ERP section

Order workflow:
1. New document + Confirmation
2. Review
3. ERP section

PPD, Others workflow:
1. New document 
2. Data fill
3. ERP section


---

### The table of conditions
|Sections|Conditions|Operators|Value|
|---|---|---|---|
|Extraction, Approval, Review, ERP|Document kind|equal, not equal, in the list, not in the list|selector|
|Extraction, Approval, Review, ERP|Document type|equal, not equal, in the list, not in the list|selector|
|Extraction, Approval, Review, ERP|Document series|equal, not equal, in the list, not in the list, filled, not filled|selector|
|Extraction, Approval, Review, ERP|Contract|equal, not equal, in the list, not in the list, filled, not filled|selector|
|Extraction, Approval, Review, ERP|Cost Center|equal, not equal, in the list, not in the list, filled, not filled|selector|
|Extraction, Approval, Review, ERP|Activity|equal, not equal, in the list, not in the list, filled, not filled|selector|
|Extraction, Approval, Review, ERP|Sender’s email|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Approval, Review, ERP|Currency|equal, not equal, in the list, not in the list, filled, not filled|selector|
|Approval, Review, ERP|Partner|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Approval, Review, ERP|Partner’s DIC|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Approval, Review, ERP|Partner’s IC|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Approval, Review, ERP|Partner’s Local VAT|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Approval, Review, ERP|Total amount|equal, not equal, equal or more than, more than, equal or less than, less than, between||
|Approval, Review, ERP|Links count|equal, not equal, equal or more than, more than, equal or less than, less than, between||
|Approval, Review, ERP|Data source|equal, not equal, in the list, not in the list, filled, not filled|selector (Rossum, isdoc, eKASA, public API)|
|Extraction, Approval, Review, ERP|Created by user|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Extraction, Review, ERP? Approval|Order number|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Extraction, Approval, Review, ERP|Accounting rule|equal, not equal, in the list, not in the list, filled, not filled|selector|
|Extraction, Approval, Review, ERP|Description|equal, not equal, in the list, not in the list, contains, not contains, filled, not filled||
|Extraction, Approval, Review, ERP|Validation warnings|contains, does not contain||
|Extraction, Approval, Review, ERP|Validation error|contains, does not contain||
|Extraction, Approval, Review, ERP|Tag|equal, not equal, in the list, not in the list, filled, not filled|selector|
|For the section that goes after Approval section|Flow status|equal, not equal, in the list, not in the list|selector (New document, Filled, Extracted, Reviewed)|

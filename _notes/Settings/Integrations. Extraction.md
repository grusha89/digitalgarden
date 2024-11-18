
Choose a provider that will automatically extract data from your documents


### Extraction settings

[Extraction settings design](https://www.figma.com/design/PmBAKoagQs1VDxoJGkT8x7/Integrations?node-id=115-3141&node-type=canvas&t=WUevE3vHJvEVepvu-0)

#### Description

Button “Cancel”

- cancels all unsaved changes

Button “Save”

- saves all the changes
- is active only when at least one change was made
- warning dialog about unsaved changes appears when user exits the page without saving

#### Incoming invoice section

Set options for extracting received invoices

- Toggle “Extract”
    - when the toggle is turned off, the settings disappear, only toggle is displayed
    - when the toggle is turned on, the settings appear
- Settings:
    - “Rossum” box
        - Rossum logo + name + radio button (is always true)
        - Text “Extraction with the ability to review data. By checking, the system learns and improves”
    - Toggle “Extraction of items”
        - when the toggle is turned on Rossum extracts the lines
    - Toggle “Predicate billing codes”
        - when the toggle is turned on Rossum predicts the accounting registers
    - “Add an optional field” selector [[Customization. Custom properties]] 
        - the list of all optional fields is filtered by document kind
        - a selected custom property is added as the chip
        - the list is decreasing on the value that was selected
        - the list is increasing on the value that was removed
        - full-text search
        - values can be added with “Enter”
        - values can be removed with the “Backspace”
        - there is a validation on the unknown value

#### Outgoing section

Set options for extracting issued invoices

- Toggle “Extract”
    - when the toggle is turned off, the settings disappear, only toggle is displayed
    - when the toggle is turned on, the settings appear
- Settings:
    - “Rossum” box
        - Rossum logo + name + radio button (is always true)
        - Text “Extraction with the ability to review data. By checking, the system learns and improves”
    - Toggle “Extraction of items”
        - when the toggle is turned on Rossum extracts the lines
    - Toggle “Predicate billing codes”
        - when the toggle is turned on Rossum predicts the accounting registers
    - “Add an optional field” selector
        - the list of all optional fields is filtered by document kind
        - a selected custom property is added as the chip
        - the list is decreasing on the value that was selected
        - the list is increasing on the value that was removed
        - full text search
        - values can be added with “Enter”
        - values can be removed with the “Backspace”
        - there is a validation on the unknown value

#### Receipt

Set receipt mining options

- Toggle “Extract”
    - when the toggle is turned off, the settings disappear, only toggle is displayed
    - when the toggle is turned on, the settings appear
- Settings:
    - “Rossum” box
        - Rossum logo + name + radio button
        - Text “Extraction with the ability to review data. By checking, the system learns and improves”
    - “wflow AI” box
        - wflow logo + name + radio button (when the radio button is true “Predicate billings” and “Custom properties” are not displayed
        - text “wflow AI extracts data from receipts using artificial intelligence”
    - Toggle “Extraction of items”
        - when the toggle is turned on Rossum extracts the lines
    - Toggle “Predicate billing codes”
        - when the toggle is turned on Rossum predicts the accounting registers
    - “Add an optional field” selector
        - the list of all optional fields is filtered by document kind
        - a selected custom property is added as the chip
        - the list is decreasing on the value that was selected
        - the list is increasing on the value that was removed
        - full text search
        - values can be added with “Enter”
        - values can be removed with the “Backspace”
        - there is a validation on the unknown value

 * Rossum language is taken from the organization language
* When ***registers***  and ***items templates*** are updated, synchronization is not needed, they will be updated automatically in Rossum
---


#### PROD and PREPROD stages

Information for testers

In order to use Rossum properly on PROD stage you have to do the following steps:
1. Go to PROD stage of your organization
2. Go to Rossum settings
3. Deactivate Rossum integration
4. Turn on Rossum integration again

And vise verse with PREPROD STAGE:
1. Go to PROD stage of your organization
2. Go to Rossum settings
3. Deactivate Rossum integration
4. Turn on Rossum integration again

---


### OLD!!! Extraction settings

**Provider selector:**
* ROSSUM (direct integration of wflow.com) RECOMMENDED
* ROSSUM (Dativery integration) 
* None

**ROSSUM (direct integration of wflow.com) RECOMMENDED**
 * Connections status. Shows whether the access is granted or not
 * Predicate billing codes. Toggle. 
 * Documents: Incoming Invoice, Outgoing Invoice, Receipts
	 * Each document kind has a turn on/off toggle and toggle for turning on/off the items extraction
	 * If toggle of the document kind is turned off, toggle of item extraction is turned off automatically
* Optional fields: Add an optional field selector: 
	* full text search by name and description
	* selector offers all custom properties and those that are not active on the document detail 
	* selected custom property disappears from the list
	* selected custom property is being added as the chip that can be removed by clicking on the cross on the chip
	* Detailed behavior of custom properties in Rossum can be found in 
* "Recycle bin" button - removes the whole integration. Has a confirmation message 
* "Cancel" and "Save buttons" - appear when changes are made
* "Synchronization" button - is displayed by default and after the changes were saved
	* button is needed in order to synchronize the changes made in wflow with Rossum settings
		* for example when organization language is changed 
		* or any changes in organization profile and in Rossum setting itself
		* custom properties are changed 


* Rossum language is taken from the organization language
* When ***registers***  and ***items templates*** are updated, synchronization is not needed, they will be updated automatically in Rossum

---


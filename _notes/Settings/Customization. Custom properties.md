#CustomProperties

> [!NOTE] Behavior on document detail
> Detailed information about how custom properties behave on document detail and in Rossum can be found here [[Document detail. Incoming Invoice]] and [[Rossum]]
> 


Custom properties a.k.a. Optional fields

* each custom property has displayed *identifier, name and the order, copy and settings button*

##### "Optional field" dialog window (Documents)
Dialog window has warning about unsaved changes

* "Identifier" input 
	* tooltip "Technical identifier of the field, the identifier is not visible to the user"
	* special symbols are not allowed
	* all spaces gonna be replaced with the low dash
	* required field
	* must be unique
	
* "Name" input
	* required field

* "Show a field in document or file detail" toggle
* "Enable field editing in document or the file detail" toggle

* "Document kind" selector:
	* "All documents" chip is by default. It doesn't have "cross"
	* Selector options: the list of document kinds
	* Select document kind is added as the chip and "All documents" chip disappears. Added chips can be removed via "cross"
	* multi selection

* "Data type" selector. 
	* Checkbox (Yes/No)
	* Date
	* Number
	* Text
	* Link
	* List: 
		* when selected, input "Value" appears, where different values can be added.
		* values are added as the chips
		* input is possible with the bulk values (using copy paste)
			* cell from the excel
			* ";"
			* when the text with breaking lines is pasted

* "Display order in document or file detail" input"
	* Input accepts only number, positive and negative
	* tooltip "Set the display order of the field in the document/file detail. Fields with the same rank values will be displayed alphabetically by identifier"

##### "Optional field" dialog window (Storage files)

It's almost the same as for documents but here are the differences:
* "Document kind" selector is absent
* Data types doesn't have the list

---

**ROSSUM**
* For each kind, only corresponding custom properties are displayed

**COLUMNS**
* For each kind only corresponding custom properties are displayed in column settings [[Customization. Appearance]]


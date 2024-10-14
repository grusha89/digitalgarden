
##### The grid
- "Create document type" button
- Search bar: by document type name, is not case sensitive, partial words
- Kebab menu for each document type: 
	- Edit document type
	- Set as default type (is shown only for not default types)
	- Default type is marked with the star close to kebab menu
	- Duplicate
	- Remove
- Columns:
	- Name (has sorting)
	- Document type (has sorting)
	- Access to own (has tooltips)
	- Access to all (has tooltips)

##### Dialog window (create new document type)

* Dialog window has warning about unsaved changes

###### Basic data
- Name: has a placeholder, has the restriction on 35 symbols, validation when the field is empty 
- Document kind: selector
- [[Number series]]: selector with the full text search
	- if series are assigned to the certain invoice type (e.g. proforma) then the documents will be allowed to be created only as proforma
	- if series are not assigned to the certain invoice type then user will be able to choose any invoice type for the document he wants to created
- [Automatic numbering series] (only orders and for manual outgoing invoices and contracts): selector with the full text search 
- Toggles "File upload"/ "Manual document creation" (only for outgoing invoices and contracts)
- Toggle "Timestamp":
	- after creating the document
	- after approval of the document
- [Access] to all documents in the type
- [Access] to own documents in the type
- When one user is already added to the section "Access to all documents" and then the same user is added to the section "Access to private documents, he is automatically removed from the section "Access to all documents"

###### Billing presets
- Accounting fields inputs that depend on the [ERP fields] settings 
- "VAT apply reduction coefficient" and "VAT fixed assets (VAT line 47)" are checkboxes
- "VAT supply mode code" is selector with the predefined following options (this field can not be empty):
	- "Normal supply"
	- "Special scheme for travel service"
	- "Special scheme for used goods"
* "VAT regime" is the selector with the predefined following options (this field can not be empty):
	* "Standard"
	* "PDP"
	* "Reverse charge"
	* "Excluded from VAT"
	* "Domestic in foreign currency"
* "Business item" is the selector when user beside the existing registers can insert custom value and validation will not appear
* Other fields have the same behavior: selectors where only existing valid registers can be insert, they also can be empty, validation appears when invalid value is inserted
* Registers: full text search by code name and by description, ignores diacritics
* Selected registers will be automatically assigned to the new document being created in the corresponding document type

##### Edit document type dialog window

* All behaviors remain the same as in new document type dialog window **BUT** 
	* "Document kind" selector is no longer editable, it can not be changed

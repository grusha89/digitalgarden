
Validation settings are managed in [[Customization. Validations]]

Validations appear in the separate section.
Section has count

Validation types:
* Errors (red)
* Warnings (yellow)

Validation card:
* validation type indicator (error or warning)
* validation name
* Button "Solve"
	* when button is clicked autofocus appears on the field that needs to be solved
	* button disappears when the document is locked
* each card can be folded (only validation name is displayed)
* when the validation is fixed, validation card disappears


### Document is duplicate

* has title "Number"
* displays the list of the duplicate documents
	* each document has link and the date of creation
* "Number" field is highlighted, has tooltip
* "Solve" button creates autofocus the "Number" field


### The partner is an unreliable VAT payer

* "Partner VAT" is highlighted, has tooltip
*  "Solve" button creates autofocus the "Partner VAT" field

### Filling in the mandatory ERP fields

* has title of the accounting field validation refers to, for example "Cost Center"
* Corresponding accounting field is highlighted  + tooltip
* "Solve" button creates autofocus the corresponding accounting field

### Disagrees Total amount compared to VAT recapitulation

* doesn't have highlighted field
* "Solve" button add the line that will balance the difference

### Disagrees Lines compared to VAT recapitulation

* doesn't have highlighted field
* "Solve" button add the line that will balance the difference

### Error in VAT calculation

* doesn't have highlighted field
* "Solve" button creates autofocus on the first cell of the recapitulation

### Unknown VAT rates

* when unknown VAT rate is extracted
* validation indicator appears next to the unknow rate in the recapitulation net
* button "Solve" creates autofocus on the first cell of the unknown VAT 

### The date is out of range

* has title of the date validation refers to, for example "Due date"
* corresponding date field is highlighted + tooltip
* button "Solve" created autofocus on the corresponding date field

### The document does not belong to your organization

* only for incoming invoice
* doesn't have highlighted field
* button "Solve" calls the confirmation dialog "Solve. The solution will undisplay the validation. We recommend checking whether the document belongs to your organization. Do you really want to solve the validation?"
* When "Yes" is clicked validation is being resolved


### Line item amounts do not match

* when the amount of the line is extracted incorrectly
* highlights the total amount field of the line + tooltip
* button "Solve" created autofocus on the total amount of the line


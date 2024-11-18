
Here we can set validations for different document kinds. 

Each validation has turn on/off toggle

Each validation has the selector where user can choose the type of the validation: Warning or Error
* Warnings will always allow to send document to ERP and and to approve the documents
* Errors will not allow to send document to ERP and not allow some levels to approve the document. Conditions for this behavior can be found in [[Approval paths]] and in [[Approval process]]  #approvalWithErrors

##### Description of each validation
Detailed information about validations behavior can be found in [[Document detail. Incoming Invoice]]

***Document is duplicate*** 
* tooltip "Document duplication check by number, amount and ID/VAT ID"
* has additional settings "Validation duplicates by fields" (Mark a document as duplicate if it matches). If several checkboxes are selected, condition will be AND:
	* "Variable symbol" checkbox
	*  "Document number" checkbox
	* "Partner ID or VAT number" checkbox
	* "Total amount" checkbox
	* by default all checkboxes are selected
	* when validation is turned off, the setting wheel is read only

***The partner is an unreliable VAT payer
* tooltip "An unreliable VAT payer is identified in the national register of VAT payers registered in the Czech Republic, which is published on the website of the Ministry of Finance of Czech Republic"

***Filling in mandatory ERP fields
* tooltip "Checking the obligation to fill in accounting fields. The obligation to fill in is set in the ERP settings for the accounting system" [[Customization. Field settings for ERP]]

***Disagrees Total amount compared to VAT recapitulation
* tooltip "Checks the consistency of the sum of the amounts in the recapitulation of VAT and the total amount"

***Disagrees Lines compared to VAT recapitulation
* tooltip "Checks the consistency of the sum of the amounts in the VAT recapitulation and the sum of the amounts in the items"

***Error in VAT calculations
* tooltip "Check whether the tax base of the rates with the calculated VAT fits. Tolerance +/-"

***Unknown VAT rates
* tooltip "Checking whether the VAT rates match the standard rates (taken on the basis of the organization's VAT number"

***The date is out of range
* "The date on the document is more than 2 years away from the date of creation. Dates are checked: UZP date, Issue date, Received date, Case date and Due date"

***The document does not belong to your organization
* tooltip "Checking whether the document belongs to your organization. It is assessed using ID number"
* only for Incoming Invoices

***Line item amounts do not match
* The basis amount on the item does not match (Quantity x Unit Price)


##### Validations according to the document kinds

|                                                       | Inc | Outg | Rcpt | Incoming cash receipt | Order | Contract | Other |
| ----------------------------------------------------- | --- | ---- | ---- | --------------------- | ----- | -------- | ----- |
| Document is duplicate                                 | +   | +    | +    |                       | +     |          |       |
| The partner is an unreliable VAT payer                | +   | +    | +    | +                     | +     | +        | +     |
| Filling in mandatory ERP fields                       | +   | +    | +    | +                     | +     |          | +     |
| Disagrees Total amount compared to VAT recapitulation | +   | +    | +    | +                     | +     |          | +     |
| Disagrees Lines compared to VAT recapitulation        | +   | +    | +    | +                     | +     |          | +     |
| Error in VAT calculations                             | +   | +    | +    | +                     | +     |          | +     |
| Unknown VAT rates                                     | +   | +    | +    | +                     | +     |          | +     |
| The date is out of range                              | +   | +    | +    | +                     | +     | +        | +     |
| The document does not belong to your organization     | +   |      |      |                       |       |          |       |
| Line item amounts do not match                        | +   | +    | +    |                       |       |          |       |

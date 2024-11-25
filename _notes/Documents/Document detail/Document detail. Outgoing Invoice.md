

---

### Outgoing invoice fields

##### General info

* Data source (is not displayed if the data source is not the following type)
	* ISDOC
	* Rossum
	* wflow Api
* "Document type" - read only
* "Document series" selector #DocumentSeries 
	* can be read only, it depends on the settings in  [[Organization profile]]
	* when it's active - the list of values is available. Values are created in [[Number series]]
	* full text search by code and description
	* the list can be filtered by the invoice type selection and vice versa
* "Invoice type" selector
	* Tax invoice
	* Credit note
	* Debit note
	* Proforma
	* Tax invoice payment
* "Description" 
	* stretches up to 6 lines
	* inner scroll
* "Number"
	* text input
* "Variable symbol"
	* text input
	* VAR symbol is automatically cleaned of all non-numeric characters during manual invoice issuance. 
* "Constant symbol"
	* max. 10 symbols
* "Specific symbol"
* "Order number"
	* when is filled can trigger the [[Automatic pairing order with incoming invoice]]
* "Tax document number"
	* text input
* Internal number 
	* can be filled via import [[Grid. Internal number import]]
	* text input 
* External designation
	* text input


##### Customer section

Customer
	* partner selector
	* full text search
	* button "Next" to upload the further values
	* button "+" opens the dialog. The dialog window is the same as in [[Contacts]] #Partners
* Customer address
	* text input
	* can be automatically filled when partner is chosen from selector
* Customer ID
	* text input
	* can be automatically filled when partner is chosen from selector
* Customer VAT number
	* text input
	* can be automatically filled when partner is chosen from selector
	* has validation on unreliable VAT payer. More info can be found in [[Customization. Validations]]  and [[Document detail. Validations]]
* Customer local VAT
	* text input
	* can be automatically filled when partner is chosen from selector
 * ***Bank account number + bank code
	* text input
	* can be automatically filled when partner is chosen from selector
	* Validation tooltip "The account was found in the VAT register"
	* Validation tooltip "The partner was not found in the VAT register" 
* **IBAN
	* text input
	* can be automatically filled when partner is chosen from selector
	* Validation tooltip "The partner was not found in the VAT register"
	* Validation tooltip "The account was found in the VAT register"
	* IBAN is being validated when bank account number is not filled
* **BIC
	* text input

##### Supplier section

All inputs are read only
Displays the organization info that is filled in [[Organization profile]]

* **Supplier
* **Supplier address
* **Supplier ID
* **Supplier's VAT number


##### Dates

* Date of issue
* UZP date
* Due date
* Date of case

##### Financial data

* Currency 
	* currency code selector
* Exchange rate
	* number input
	* with 6 decimals??? must be checked #tocheck
* Exchange rate units
	* number input
	* without decimals

* ***Recapitulation
	* is editable if the outgoing invoice is created via document upload
	* is read only if the outgoing invoice is created via manual form
		* recapitulation and total amount are automatically filled on the base of the lines
	* automatic calculation
	* Columns: rate, tax base, Total with VAT, total of all rows
	* Rows: rates according to the legislation [[Organization profile]]

* Rounding amount
	* number input
	* placeholder 0,00
* Paid by deposit
	* number input
	* placeholder 0,00
* Total amount
	* number input
	* is read only if the outgoing invoice is created via manual form
	* is auto filled according to the recapitulation + rounding amount - paid by deposit
	* placeholder 0,00

---

### Outgoing invoice flow

Manual

1. Not confirmed
2. Filled
3. To review
4. Reviewed
5. Sent
6. Waiting to be sent to ERP
7. Sent to ERP


> [!important] Revise
> * Manual outgoing invoice can be revised at any flow level and to be confirmed again. When it's revised it gets the status "Not filled" again and the flow can be processed from the start
> * Button "Revise" is available when document is not locked as well as button "Generate PDF"




Extracted

1. New
2. Waiting to be sent to Extraction
3. Successfully sent to Extraction
4. Extracted
5. To review
6. Reviewed
7. Waiting to be sent to ERP
8. Sent to ERP

> [!important] Dependency on automation workflow
> * The presence of certain flow statuses and corresponding actions depends on automation workflow settings [[Workflow automations]]
> * If workflow has certain flow action turned off (e.g. sending to ERP), sending to ERP action is not available for the kind/type and ERP flow statuses are not displayed
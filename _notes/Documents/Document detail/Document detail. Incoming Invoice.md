

---

### Incoming invoice fields

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
* "Constant symbol"
* "Specific symbol"
* "Order number"
	* when is filled can trigger the [[Pairing]]
* "Tax document number"
	* text input
* Internal number 
	* can be filled via import [[Grid. Internal number import]]
	* text input 
* External designation
	* text input


##### Supplier section

**Supplier
	* partner selector
	* full text search
	* button "Next" to upload the further values
	* button "+" opens the dialog. The dialog window is the same as in [[Contacts]] #Partners
* **Supplier address
	* text input
	* can be automatically filled when partner is chosen from selector
* **Supplier ID
	* text input
	* can be automatically filled when partner is chosen from selector
* **Supplier VAT number
	* text input
	* can be automatically filled when partner is chosen from selector
	* has validation on unreliable VAT payer. More info can be found in [[Customization. Validations]]  and [[Document detail. Validations]]
* **Supplier local VAT
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

##### Customer section

All inputs are read only
Displays the organization info that is filled in [[Organization profile]]

* **Customer
* **Customer address
* **Customer ID
* **Customer's VAT number


##### Dates

* Date of issue
* Date of acceptance
* Date of case
* UZP date
* Due date

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
	* is editable
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
	* is auto filled according to the recapitulation + rounding amount - paid by deposit
	* placeholder 0,00
* Don't pay
	* checkbox
	* when is true it blocks the payment:
		* "Record payment" button become inactive
		* Payment order section has the message "Payment cannot be made in edit mode. Save changes for payment option" 
		* Detailed info about payments can be found in [[Document detail. Payments]]


---

### Incoming invoice flow


1. New
2. Waiting to be sent to Extraction
3. Successfully sent to Extraction
4. Extracted/Filled
5. To review
6. Reviewed
7. Waiting to be sent to ERP
8. Sent to ERP

> [!important] Dependency on automation workflow
> * The presence of certain flow statuses and corresponding actions depends on automation workflow settings [[Workflow automations]]
> * If workflow has certain flow action turned off (e.g. sending to ERP), sending to ERP action is not available for the kind/type and ERP flow statuses are not displayed


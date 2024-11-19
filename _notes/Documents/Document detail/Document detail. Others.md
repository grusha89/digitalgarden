

---

### Incoming invoice fields

##### General info

* "Document type" - read only
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
	* when is filled can trigger the [[Automatic pairing order with incoming invoice]]
* Internal number 
	* can be filled via import [[Grid. Internal number import]]
	* text input 
* External designation
	* text input


##### Partner section

* **Partner
	* partner selector
	* full text search
	* button "Next" to upload the further values
	* button "+" opens the dialog. The dialog window is the same as in [[Contacts]] #Partners
* **Partner address
	* text input
	* can be automatically filled when partner is chosen from selector
* **Partner ID
	* text input
	* can be automatically filled when partner is chosen from selector
* **Partner VAT number
	* text input
	* can be automatically filled when partner is chosen from selector
	* has validation on unreliable VAT payer. More info can be found in [[Customization. Validations]]  and [[Document detail. Validations]]
* **Partner local VAT
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


##### Dates

* Date of issue
* Date of acceptance
* Date of case
* UZP date
* Due date

##### Financial data

* ***Recapitulation
	* is editable
	* automatic calculation
	* Columns: rate, tax base, Total with VAT, total of all rows
	* Rows: rates according to the legislation [[Organization profile]]
	
* Currency 
	* currency code selector
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

---

### Others flow

1. New
2. Filled
3. Waiting to be sent to ERP
4. Sent to ERP

> [!important] Dependency on automation workflow
> * The presence of certain flow statuses and corresponding actions depends on automation workflow settings [[Workflow automations]]
> * If workflow has certain flow action turned off (e.g. sending to ERP), sending to ERP action is not available for the kind/type and ERP flow statuses are not displayed
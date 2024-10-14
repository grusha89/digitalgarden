

---

### Income cash receipt fields

##### General info

* "Document type" - read only
* "Document series" selector #DocumentSeries 
	* can be read only, it depends on the settings in  [[Organization profile]]
	* when it's active - the list of values is available. Values are created in [[Number series]]
	* full text search by code and description
* "Description" 
	* stretches up to 6 lines
	* inner scroll
* "Number"
	* text input
* "Variable symbol"
	* text input
* "Tax document number"
	* text input
* Internal number 
	* can be filled via import [[Grid. Internal number import]]
	* text input 
* External designation
	* text input


##### Customer section

**Customer
	* partner selector
	* full text search
	* button "Next" to upload the further values
	* button "+" opens the dialog. The dialog window is the same as in [[Contacts]] #Partners
* **Customer address
	* text input
	* can be automatically filled when partner is chosen from selector
* **Customer ID
	* text input
	* can be automatically filled when partner is chosen from selector
* **Customer VAT number
	* text input
	* can be automatically filled when partner is chosen from selector
	* has validation on unreliable VAT payer. More info can be found in [[Customization. Validations]]  and [[Document detail. Validations]]
* **Customer local VAT
	* text input
	* can be automatically filled when partner is chosen from selector


##### Supplier section

All inputs are read only
Displays the organization info that is filled in [[Organization profile]]

* **Supplier
* **Supplier address
* **Supplier ID
* **Supplier's VAT number


##### Dates

* Date of issue
* Date of case
* UZP date

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

---

### Income cash receipt flow


1. New
2. Filled
3. Waiting to be sent to ERP
4. Sent to ERP

> [!important] Dependency on automation workflow
> * The presence of certain flow statuses and corresponding actions depends on automation workflow settings [[Workflow automations]]
> * If workflow has certain flow action turned off (e.g. sending to ERP), sending to ERP action is not available for the kind/type and ERP flow statuses are not displayed


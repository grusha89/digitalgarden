#orders


---

### Order fields

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
	* auto generated on the base of the settings in #AutomaticDocumentNumbering 
* Internal number 
	* can be filled via import [[Grid. Internal number import]]
	* text input 
* Date of issue
	* automatically filled with the order's date creation
* Expected delivery date
	* automatically filled on the base of the selected Partner's  "Delivery period" (creation date + amount of days from Delivery period). Delivery period can be set in [[Contacts]] in section #Partners 


##### Supplier section

* ***Supplier
	* partner selector
	* full text search
	* button "Next" to upload the further values
	* button "+" opens the dialog. The dialog window is the same as in [[Contacts]] #Partners
* Supplier address
	* text input
	* can be automatically filled when partner is chosen from selector
* **E-mail
	* validation of the correct format
	* can be automatically filled when partner is chosen from selector
	* is being used for sending files to the supplier
* Supplier ID
	* text input
	* can be automatically filled when partner is chosen from selector
* **Supplier VAT number
	* text input
	* can be automatically filled when partner is chosen from selector
	* has validation on unreliable VAT payer. More info can be found in [[Customization. Validations]]  and [[Document detail. Validations]]
* **Supplier local VAT
	* text input
	* can be automatically filled when partner is chosen from selector
* Delivery period
	* read only
	* automatically filled when partner is chosen from selector


##### Customer section

All inputs are read only
Displays the organization info that is filled in [[Organization profile]]

* **Customer**
* **Phone No**
* **E-mail**
* **Customer address**
* **Customer ID**
* **Customer VAT number

##### Delivery data

* Place of delivery
	* selector
	* can be selected from the registers that can be managed in [[wflow.com WIKI/Other settings/Registers administration/Organization]] in the section #DeliveryLocations 
* Contact person
	* text input
	* can be automatically filled on the base of the the corresponding field during Order creation [[Manual forms]]
* Contact person's email
	* text input
	* validation of the correct email form
	* can be automatically filled on the base of the the corresponding field during Order creation
##### Financial data

* ***Recapitulation
	* is read only
	* automatic calculation on the base of the added lines
	* Columns: rate, tax base, Total with VAT, total of all rows
	* Rows: rates according to the legislation [[Organization profile]]

* **Currency 
	* currency code selector
	* is automatically filled 
* Total amount
	* read only
	* is auto filled according to the recapitulation
	* placeholder 0,00

---

### Order flow

1. Not confirmed
2. Filled
3. To review
4. Reviewed
5. Sent
6. Waiting to be sent to ERP
7. Sent to ERP
8. Partially delivered
9. Delivered

> [!important] Revise
> * Order can be revised at any flow level (beside "fully Delivered" status) and to be confirmed again. When it's revised it gets the status "Not filled" again and the flow can be processed from the start
> * Button "Revise" is available when document is not locked as well as button "Generate PDF"

> [!important] Dependency on automation workflow
> * The presence of certain flow statuses and corresponding actions depends on automation workflow settings [[Workflow automations]]
> * If workflow has certain flow action turned off (e.g. sending to ERP), sending to ERP action is not available for the kind/type and ERP flow statuses are not displayed


### General info

* It is possible to create payment when the document is locked
* It is impossible to create payment when the document is in edit mode
### Incoming Invoice

##### Payment status
* is displayed by default on the upper panel next to the flow status
* has three states:
	* unpaid
	* paid
	* overpaid


> [!NOTE] 
> * payment status is reconsidered when the total amount is edited
> * "paid by deposit" is taken into consideration as well for payment status
> * when incoming invoice has invoice type "Tax document payment" - payment status is automatically "paid" and payment section is not available

##### Payment order status
* appears on the upper panel only when is not null
* has two states:
	* marked for payment
	* payment order created

---


##### Payment order section

* Paid amount bar
	* displays how much of the total amount is paid
		* bar has orange color if the amount is partially paid
		* bar has green color if the amount if fully paid

* "Pay" button that allows to created payment via:
	* bank API
	* QR code

* "Mark for payment" 
	* marks the certain amount to be paid


#### *Payment via bank API*

Bank connection can be managed in [[Bank connections]]

Warning appears when the required field for the payment via bank API are not presented:
* Variable symbol
* IBAN
* Currency

==Warning dialog:==
* Message "Please fill in the missing data in the Incoming invoice section and repeat the action. Missing data: Variable symbol, Currency, IBAN"
* Button "Close and complete the data"
* Button "Pay via QR"

**Dialog window "Pay"
* "Payment from account" selector (required)
	* displays all the available to the user bank accounts
	* default bank account is automatically selected
	* bank accounts are displayed as **Account name + account number/bank code**
	* selected bank account displays the deposit in format "0.00 + currency"
* "Recipient" 
	* display Partner name
* "Bank account number"
	* displays the bank account of the Partner
* "IBAN"
	* IBAN can be automatically formed on the base of the bank account
	* has validation
		* The account was found in the VAT register
		* The account was not found or the VAT payer is not reliable
* "Currency"
* "Variable symbol"
* "Constant symbol"
* "Pay on the day" date picker (required)
	* has two selectable chips "Invoice due date" and "Today"
	* when date of marking for payment is in the past - date for payment is offered as today
	- when date of marking for payment is in the future - date for payment is offered as future date
* "Amount" (required)
	* number input
* "Message for recipient" 
	* text input
* "Priority" selector:
	* Standard
	* Immediate
	* Express
		* has warning "This option may be charged according to your bank's rate"
* "Pay by transfer" button 
* Button "To pay via QR"

***Due date
* by default document's due date is selected
* When the chip "today" is clicked -  due date will be changed to today
* when custom date is selected - all chips will be deselected
* when the document's due date is in the past - the chip "document's due date" will be disabled and the current date will be used
> [!NOTE] Validations 
> * emittanceInformation.unstructured 140 max charachters - **Message**
> * creditor name 35 max charachters- **RecipientName**
> * when document is not approved
> * when due date is weekend day
> * IBAN and account number do not match

When the payment is processed the dialog window with pending is displayed with the text "Confirming your payment, please wait"

##### Transaction detail

* Icon of the blue card + payment order is created + date of the transaction
* Amount + currency
* Created by: user name
* IBAN (sender)
* Input date and time
* Due date
* Created via
* Paid (Single/Bulk)

* IBAN (receiver)
* Variable symbol


---


#### *QR payment

When there is no bank integration, QR payment opens by default when "Pay" button is clicked
When there is bank integration QR payment can be reached via the dialog window of payment via bank API

"Payment" dialog window:
* QR code 
* "Pay on the day" date picker (required)
	* has two selectable chips "Invoice due date" and "Today"
	* when date of marking for payment is in the past - date for payment is offered as today
	- when date of marking for payment is in the future - date for payment is offered as future date
*  "Amount" (required)
	* number input
* Button "Mark as paid"

**Property v QR modelu
{ 
"payment": "string", 
"provider": "QRPayment"
}

***Due date
* when the document has due date in the past - due date is offered as the current date
* for actions "Pay" and "Record payment" is possible to set the due date in the past

---


#### Payment section


> [!NOTE] Pair the transaction
> This selector Is visible only for users with the rights of payment management [[Users and permissions]] and the owners of the bank connection. The overview of transactions can be found in [[Account movements]]
https://www.figma.com/file/J5SBwD5WRJG09r8FezNN8Q?embed_host=share&kind=file&node-id=53-2000&page-selector=0&t=vk0jW8OTmE1Su0Fy-1&viewer=1

"Record payment" button 
* opens dialog window
	* "Pair the transaction" selector 
		* placeholder "Select a transaction"
		*  offers individual probably matched  transactions represented by:
			* amount
			* Partner name
			* Variable symbol
			* Created
		* "Select another from the list" button
			* opens the dialog window "Select a transaction" where the user can filter and find the transaction he needs by filters: (filters are not displayed if the corresponding field doesn't have value on the document)
				* IBAN
				* Variable symbol - searches for the transaction by VS of the document
				* Total amount - searches for the transaction by amount of the document
				* search bar: by partner name, amount and variable symbol
			* documents are displayed in the table with the following columns:
				* Partner name (Supplier/Customer) depending if the transaction is incoming or outgoing
				* Total amount
				* Currency
				* Variable symbol
				* Document kind
				* Creation date
	* "Payment date" date picker
	* "Amount" number input - automatically filled with the document's total amount
	* "Record payment" button
* marks the document as fully or according to the amount of the paired transaction paid
* pay order is created:
	* status "Paid"
	* payment date
	* paid amount
	* payment order details:
		* Created by: user name who created the payment
		* Input date and time: date
		* "Delete" button
			* deletes the created payment order
			* cancels the payment
			* document becomes unpaid again


> [!NOTE] Record payment
> It is possible to user "record payment" for:
> * incoming invoice with total amount equals 0
> * incoming invoice with negative total amount
> * outgoing invoice

#### Do not pay

* checkbox is false by default
* when is true all payment section become disabled

#### Integration with Abra Flex ERP system

- Document that was sent to FlexiBee can be marked as paid via Dativery:
    - Send document to FlexiBee
    - Pay document in FlexiBee
    - In Dativery use function “Mark all paid invoices”
    - Document in wflow will be marked as paid

Detailed information how integration with Abra Flex works can be found here [[Abra Flex]]


---
### Outgoing invoice

Only "Reacord payment" is available with payment order status

### Receipts

- Each receipt is marked as paid as soon as it gets to wflow:
    - Payment status changes into “Paid”
    - bulk payment is absent
    - date of payment request is absent
    - date of payment is absent
    - paid amount is absent

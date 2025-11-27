Active filter is displayed on the grid as the chip. 
Each chip can be closed via its cross button. When the chip is closed, the corresponding filter is canceled
#### Simple filters
* conditions selected within one group have OR attribute
* conditions selected from different groups have AND attribute

***Dates***:
* Date of acceptance
* Date of case
* Created
* Due Date
* Date of issue
* Last action
* Payment date
* Payment request date
* Updated
* UZP date

Operators:
* Today
* Yesterday
* This week
* This month
* Last month
* Month before last
* This quarter
* Last quarter
* This year
* Last year

---
***Approval status**:
* No approval path
* To approve
* Approved
* Declined
* Returned

---

***Payment status:
* Unpaid
* Partially paid
* Paid
* Overpaid
---

***Payment order status:
* Payment order created
* Marked for payment

---

***Lock status:
* Locked
* Unlocked
---

***Flow status:
* New document
* Waiting to be sent to extraction
* Sending to extraction error
* Successfully sent to Extraction
* Filled
* Extracted
* Submitted for review
* Reviewed
* Sent (means by email)
* Waiting to be sent to ERP
* Sending to ERP error
* Sent to ERP
* Delivered
* Partially delivered
* Not confirmed 

---
***Validation status:
* The document contains a warning
* The document contains error



#### Advanced filters

Advanced filters allows to create more complex conditions for search.
To each selected condition it's possible to add another conditions with the following attributes as many times as possible:
* Or
* And

Selected condition must be saved via button "Save", then three following options appear:
* button "Apply filter" - launches the selected conditions
* button "Save filter" - save filter for future use. Dialog window appears "Save filter":
	* "Name" input - required
	* "Save for context" selector. Tooltip "Context where the filter would be visible":
		* Show everywhere - by default
		* The list of the document kinds
	* "Public filter" checkbox. Tooltip "If filter should be saved for everyone". 
	* Condition itself. Can be removed
	* "Add next option" button. Adds further conditions
	* "Save template" button
* button "Cancel filter" - cancel the selected conditions
* "Number of filters used" count

**Saved filters
* Only the creator can edit and remove the filter

***Partners:
* Partner address
* Partner VAT number
* E-mail
* Partner Id
* Partner's Local VAT
* Partner

Operators: is equal, do not equal, contains, does not contain, is blank, is not blank

---
***Dates:
* Updated
* Date of acceptance
* Date of case
* Due date
* UZP date
* Date of Issue
* Last action
* Created
* Date of signing (only for Contract)
* Effective from (only for Contract)
* Effective to (only for Contract)
* Expected delivery date (only for Order)
* Valid from (only for Contract)
* Valid to (only for Contract)

Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank, day range (negative or positive number), it is dynamic (today, yesterday, this week, this month, last month, month before last, this quarter, last quarter, this year, last year)

Current date is automatically filled when the date filter is selected
***

***Bank details:
* BIC
* IBAN
* Bank account number
* Bank code

Operators: is equal, do not equal, contains, does not contain, is blank, is not blank

---
 ***Financial data:
 * Total amount VAT
 * Total amount
 * Total amount excluding VAT
 * Total amount in foreign currency
 * Rounding amount
 * Exchange rate units
 * Exchange rate
 * Paid by deposit
 
"0,00" is filled by default
Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank

 * Currency
Operators: is equal, does not equal, is blank, is not blank

 * Don't pay (Yes or No)

---

***Registers:

Values to select are created in #Registers 

* Activity
* Document Series
* Business item
* VAT reverse charge code
* VAT supply mode code
* VAT regime (Operators: is equal, does not equal)
* Cash register
* Contra Account (MD/D)
* Accounting rule
* VAT control statement line
* VAT return line
* Cost Center
* Cash document type
* Commitment type
* Vehicle
* Contract
* Employee
* Payment method
* Project
* Business case
Operators: is equal, does not equal, is blank, is not blank

* VAT fixed assets (VAT line 47) (Yes or No)
* Use the VAT reduction coefficient (Yes or No)

---

***Files:
* Main file
Operators: is equal, do not equal, contains, does not contain, is blank, is not blank


---

***Status:
* Stamped (Yes or No)
* Signed (Yes or No)
* Lock status (Yes or No)
* 
* Extraction status:
	* Importing (deprecated)
	* Importing failed (deprecated)
	* Split (deprecated)
	* To review 
	* Reviewing
	* Confirmed
	* Rejected (deprecated)
	* Exporting
	* Exported
	* Export failed
	* Postponed (deprecated)
	* Deleted (deprecated)
	* Locked (deprecated)
* Flow status:
	* New document
	* Waiting to be sent to extraction
	*  Sending to extraction error
	* Successfully sent to Extraction
	* Filled
	* Extracted
	* Submitted for review
	* Reviewed
	* Sent (means by email)
	* Waiting to be sent to ERP
	* Sending to ERP error
	* Sent to ERP
	* Delivered
	* Partially delivered
	* Not confirmed 
* Signi status:
	* Contract not sent
	* The contract is waiting for an answer
	* Contract rejected
	* The contract has expired
	* Contract signed
	Operators: equal, does not equal
	
* The document contains a warning
* The document contains errors0
"0" is by default
Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank

---

***Document data:

* Number
* Tax document number
* Order number
* External designation
* Tag (has only one operator "is equal" + selector)
* Internal number
* Constant symbol
* Description
* Specific symbol
* Comments
* My comments (boolean)
* Unresolved comments (boolean)
* Document type
* Variable symbol
* Created by user
Operators: is equal, do not equal, contains, does not contain, is blank, is not blank

* Links count
* Comments
"0" is by default
Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank

* Data source:
	* ISDOC
	* ROSSUM
	* eKASA
	* public API
Operators: equal, does not equal

---

***Approval:

* Approvers
Operators: is equal, do not equal, contains, does not contain, is blank, is not blank

* Approval path name
	* selector. Approval path can be created in [[Approval paths]]
Operators: is equal, do not equal,  is blank, is not blank

* User approved
	* selector. Users can be created in [[Users and permissions]]
Operators: is equal,  is blank, is not blank

* Approval status:
	* No approval path
	* To approve
	* Approved
	* Declined
	* Returned
Operators: equal, does not equal

---

***Payments

* Payment status
	* Unpaid
	* Partially paid
	* Paid
	* Overpaid
Operators: equal, does not equal

* Payment order status:
	* Payment order created
	* Marked for payment
Operators: equal, does not equal

* Payment date
* Payment request date
Current date is filled by default
Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank, day range (negative or positive number), it is dynamic (today, yesterday, this week, this month, last month, month before last, this quarter, last quarter, this year, last year)

* Paid amount
"0,00" is by default
Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank


---

***Other

* Email of the sender
Operators: is equal, do not equal, contains, does not contain, is blank, is not blank

* To review
Current date is filled by default
Operators: is equal, is equal or greater than, is greater than, is equal or less than, is less than, is blank, is not blank, day range (negative or positive number), it is dynamic (today, yesterday, this week, this month, last month, month before last, this quarter, last quarter, this year, last year)

* Custom property. Custom property is created by users in [[Customization. Custom properties]]
	* Depending on custom property type the corresponding operators are displayed
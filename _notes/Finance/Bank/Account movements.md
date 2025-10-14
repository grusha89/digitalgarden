https://www.figma.com/design/J5SBwD5WRJG09r8FezNN8Q/p%C3%A1rov%C3%A1n%C3%AD-transakc%C3%AD?node-id=0-1&node-type=canvas&t=woWetO5IHLwUEuhX-0

In order to see the transactions user has to turn on the toggle “Update payment status for documents” in Bank connection section [[Bank connections]]
### Transactions filters

All filters are selectors. When filter is clicked the list of available options appears. The default option is marked with the blue tick

When the filter is selected:
* it gets blue color
* selected condition is displayed instead of the filter name
* clear button appears - it clears the selected filters
##### Period:
Filters the transactions that were made according to the selected period of time

* The whole period (default)
* Today
* Yesterday
* Last 7 days
* Last 14 days
* Last 30 days
* This month
* This quarter
* This year
* Custom
	* "Custom" dialog window appears:
		* "Date from" date picker (by default - current date)
		* "Date to" date picker (by default - current date)
		* "Confirm" button


##### Document
Filters the transactions according to the document connection state

* All states (by default)
* Connected
* Unconnected
* Do not link

##### Bank account
Filters the transactions according to the selected bank account
(This filter appears 3 seconds later than previous filters - FE can do nothing about it)

* All accounts (by default)
* available account number represented by IBAN

---


### Search bar

Search works by:
* Partner name
* Amount

---


### Transactions table

##### Partner 
* has sorting
* can contain Partner name + IBAN
* can contain only Partner name
* can contain only IBAN
* can be empty

##### Amount 
* has sorting
* contains number with two decimals
* has a green color if it's incoming transaction
* has a red color if it's outgoing transaction

##### Currency
* has sorting
* contains currency code

##### Variable symbol
* displays the variable symbol of the transaction

##### My account
* displays IBAN 

##### The date of the transaction
* has sorting
* displays the date in the format dd.mm.yyyy

##### Document
* has sorting
* displays the document connection state:
	* blue plus button - when the document is not paired
	* green ticket - when the document is paired
	* orange ticket - when is marked as "Do not link"

##### Kebab menu 
when the document is not paired
* Link document 
* Do not link 

when the document is paired
* Unlink the document

when is marked as "Do not link"
* Link to document


---

### Transaction detail

When user clicks on the transaction "Transaction detail" dialog window appears. It's read only

* Amount
* Transaction reference
* The date of the transaction
* Variable symbol
* Constant symbol
* Specific symbol
* Note
* Document link (if there is such):
	* document number (Document kind: document type name)


---

### Link document

When user selects "Link document" in kebab menu or when he click on the blue plus button - "Link document" dialog window appears

"Kind of document" selector:
* Incoming Invoice
* Outgoing Invoice

"Document" selector:
* has a placeholder "Select a document"
* offers individual matched documents represented by:
	* amount
	* Document kind: document type name, document number
	* Partner name
	* Variable symbol
	* Created
* "Select another from the list" button
	* opens the dialog window "Select a document" where the user can filter and find the document he needs by filters:
		* Kind of document: Incoming invoice/Outgoing invoice
		* Variable symbol - searches for the documents by VS of the transaction
		* Total amount - searches for the documents by amount of the transaction
		* search bar: by partner name, amount and variable symbol
	* documents are displayed in the table with the following columns:
		* Partner name (Supplier/Customer) depending if the transaction is incoming or outgoing
		* Total amount
		* Currency
		* Variable symbol
		* Document kind
		* Creation date

---

### Proposing probable matched transactions

This code gradually narrows down the criteria for finding documents until a result is found. In other words, it attempts to locate documents by relaxing the conditions step by step. The conditions can be described in natural language as follows:

1. Search with a Complete Set of Criteria:
Documents are searched for based on all provided parameters:  
`kind`, `isCreditNote`, `iban`, `variableSymbol`, `amount`, and `currency`.

2. **Ignoring the Condition for Amount:**
If no results are found, the search is conducted without the `amount` parameter, effectively ignoring this condition.

3. **Ignoring Conditions for Amount and Currency:**
If no results are still found, the search ignores both `amount` and `currency`.

4. **Ignoring the Condition for Variable Symbol:**
If no results are found, the search excludes the `variableSymbol` parameter but once again considers `amount` and `currency`.

5. **Ignoring Conditions for Variable Symbol and Amount:**
If no results are found, the search excludes both `variableSymbol` and `amount` but still considers `currency`.

6. **Search Based Only on `kind`, `isCreditNote`, and `iban`:**
If no results are found, only `kind`, `isCreditNote`, and `iban` are considered, while the other parameters are ignored.

7. **Search Without `iban`, But with Variable Symbol:**
If no documents are still found, the search is conducted using `kind`, `isCreditNote`, `variableSymbol`, `amount`, and `currency`, but `iban` is ignored.

8. **Search Without `iban` and Amount:**
If no results are found, the search ignores both `iban` and `amount`, using only the remaining parameters.

9. **Search Without `iban`, Variable Symbol, and Amount:**
If no results are found, the search excludes `iban`, `variableSymbol`, and `amount`, using only the remaining parameters.

10. **Search Without `iban` and Variable Symbol, But with Amount:**
Finally, documents are searched for based on `kind`, `isCreditNote`, `amount`, and `currency`, while ignoring both `iban` and `variableSymbol`.
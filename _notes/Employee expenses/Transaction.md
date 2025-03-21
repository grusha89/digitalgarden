
**Navigation menu:**

The section “Employees expenses” goes after the “Storage” section
The “Employees expenses” includes the following subsections:
- Own expenses:
    - Cards overview
    - Expenses
- Transactions
- Accounts and cards

## Transactions


> [!NOTE] Hidden transactions
> Transactions from the cards that don't have assigned user are hidden



Overview of all expenses of the employees that were made via connected cards

**Search field**
- filters by vendor’s name

**“Document” column**
- plus button - if there is no uploaded document
- green flag - document is uploaded
- orange flag - if user selected “Receipt no will be provided”
- sorting

**“Transaction” column**
- Icon of the trader (placeholder is used, if there is no image of the trader + icon of the expense type:
    - ATM
    - Pospayment
    - Other
- Name of the trader
- Date and time of the transaction
- sorting by transaction time

**“Approval” column**
- approval status + the approval path levels

**“Transaction status” column**
- Reserved
- Accounted for
- has sorting

**“Amount” column**
- negative spent amount with two decimals
- sorting

**“Private expenses” column**
- positive amount with two decimals
- sorting

**“Currency” column**
- currency code
- sorting

**“Card” column**
- card type icon (VISA, MasterCard etc.)
- Alias or card holder
- last digits of the card
- sorting by the alias

**“User” column**
- avatar
- user name
- user e-mail
- sorting

**Kebab menu**
- Edit the transaction
- Upload document - is displayed only if document is not uploaded

### Transaction detail

**Image of the document**
- text selector
- zoom in, zoom out, fit in
- file name
- download button
- delete button

**Transaction general info**
- Icon of the trader (placeholder is used, if there is no image of the trader + icon of the expense type:
    - ATM
    - Pospayment
    - Other
- Name of the trader
- Date and time of the transaction
- Transaction status
	- is taken from real bank transaction status
	- when paired with the receipt it has status "Reserved"
	- when real bank transaction is processed status chnages into "Accounted"
- Spent amount
- last 4 digits of the card

**Detailed transaction info**
* Paired document section
	* button "Pair the document"
		* opens the dialog window to pair Incoming Invoice or Receipt
		* paired document will contain paired transaction and payment status will be "Paid"
		* paired document will get the same accounting fields from the transaction
		* it is possible to comment on the paired document, open document in the new tab and remove the document from the transaction
- “Amount” input (read-only)
- “For private purposes” input
- “Address” (read-only)
- Document kind (becomes read-only when document is linked)
- Cost Center selector
- Contract selector
- Activity selector
- Note input. Placeholder “Enter a description” (available only when the document is not linked)
- Linked document:
    - document number (document kind: document type) + comment + redirection icon
- “Save” button

_**If there is no uploaded file**_

- button “Browse the device”
- message “or upload the file using drag and drop + formats (maximal size)
- red box:
    - Don’t you have the document for transaction? Let others know that you will not attach it
    - button “I don’t have document”
- orange box (if user clicked on “I don’t have document”
    - document for the transaction is missing
    - Marked that he will not attach the document to this transaction
- red box (when document upload is obligatory)
    - Add a document to this transaction. Document upload is obligatory
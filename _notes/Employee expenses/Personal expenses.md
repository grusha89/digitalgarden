
## Expenses

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

**“Approval” column**
- approval status + the approval path levels

**“Transaction status” column**
- Reserved
- Accounted
- has sorting

**“Amount” column**
- negative spent amount with two decimals

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
- Spent amount
- last 4 digits of the card

**Detailed transaction info**
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


---


## Overview of cards

**Card info**

Card visual
- contains slider if there are several cards
- Card name + last 4 digits of the card + icon of the card status with the tooltip
- Card detail button. Opens card detail window
- Limits bar:
    - Limits on card payment. CZK 10 000
    - Limits on payment online. CZK 10 000
    - Limits on ATM withdrawal. CZK 10 000

**Table of transactions**
Transactions that don’t have attached document are displayed

**Search field**
- filters by Vendor’s name

**“Document” column**
- plus button

**“Transaction” column**
- Icon of the trader (placeholder is used, if there is no image of the trader + icon of the expense type:
    - ATM
    - Pospayment
    - Other
- Name of the trader
- Date and time of the transaction

**“Approval” column**
- approval statuses + the approval path level

**“Transaction status” column**
- Reserved
- Accounted

**“Amount” column**
- negative spent amount with two decimals

**“Private expenses” column**
- positive amount with two decimals

**“Currency” column**
- currency code

**“Card” column**
- card type icon (VISA, MasterCard etc.)
- Alias or card holder
- last digits of the card

**Kebab menu**
- Edit the transaction
- Upload document

### Card detail

_**““Overview” section**_
- Card name **** 1234 (last four digits of the card)
- Card status
- Account number/ bank code
- Expiration 05/25
- Valid from 31.05.2024
- Card visual

If user is not assigned
- Red box:
    - Link the card to the user. Expenses of unlinked cards are not recorded
    - “Assign user” button

If user is assigned
- Avatar
- User name
- User e-mail
- Kebab menu: Remove user
- Set limits
    - Card payment: currency + amount
    - Payment online: currency + amount
    - ATM withdrawal: currency + amount
- “Save” button
    

_**“Settings” section**_
- **Card name (this section is visible only if the card belongs to the current user)**
    - Name the card for easier reference
    - Card name input (alias)
- **Target document type**
    - Select the document type where receipts and incoming invoices are going to be created according to the expenses of the current card
    - The “Receipts” selector, is required. Placeholder “Select document type”
        - Only Receipt types are displayed. There is a full-text search
    - The “Incoming invoices” selector, is required. Placeholder “Select document type”
        - Only Incoming Invoice types are displayed. There is a full-text search
- **Default billing**
    - Select default accountings for expenses paid with the current card
    - The “Cost Center” selector, is not required. Placeholder “Select Cost Center”
        - valid values are displayed
        - full-text search
    - “Contract” selector, is not required. Placeholder “Select Contract”
        - valid values are displayed
        - full-text search
    - “Activity” selector, is not required. Placeholder “Select Activity”
        - valid values are displayed
        - full-text search
    - “Payment method” selector, is not required. Placeholder “Select Payment method”
        - valid values are displayed
        - values assigned only for Receipts and Incoming Invoices are displayed or without any specific document kind
        - full text search
- **Mandatory document upload**
    - User must upload a scanned document to the issue
    - Toggle “Obligation to upload a document to the expense”
- Button “Save”
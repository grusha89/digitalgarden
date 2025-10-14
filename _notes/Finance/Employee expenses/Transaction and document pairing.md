

### Email addresses for transactions and cards
##### **Generating Emails for Each Card**

- Emails will be structured to include card identification, organization, and document type (receipt/invoice).
    - Example: `receipt--card3242--organization--customer@wflowmail.com`
- When a document is sent to this email, it will be automatically created in **wflow** under the corresponding document type set for that card.
- The assigned person for the card will have access to the document.

##### **Processing Flow:**

- The document follows the standard workflow but is marked as an **employee expense**:
    - Hidden payment mechanics.
    - A visible **"Employee Expenses"** block, where users can manually match expenses if they are not automatically paired.
- If multiple PDF attachments exist, they will be merged (same behavior as current "Merge all PDF attachments" option).
- If there are no PDFs, the document will not have a primary file.

##### **Expense Pairing UI:**

- Suggest expenses with the **same amount** first.
- Do not show expenses that already have a linked document.

---

   Enriching Emails with Unmatched Expense Identifiers**

- Emails can include transaction-specific identifiers for automatic pairing.
    - Example: `transactionID--receipt--card3242--organization--customer@wflowmail.com`
- If the expense **already has** an associated document, it will be processed as if there were no transaction link (following the logic from point 1).

##### **Processing Rules:**

- If multiple PDF attachments exist, one will be **randomly selected** as the primary file.
- If there are no PDFs, the document will not have a primary file.


---

### Automatic matching of employee expenses with documents received via email

Automate the pairing of documents received via card email with employee expenses.

With each update (of the total amount) on a document received via card email that has not yet been matched with an expense, attempt to match it based on the total amount. The expense must also be on the same card as the one used in the email.  
If there are multiple matching expenses, do not match to any of them.


---

### Manual pairing

* Locked documents are available in the drop down list.
	* when the locked document is selected, the warning is displayed "Document is locked. Selected cost objects are not gonna be saved"
#### When the paired document is locked

Transaction detail can not be edited when the paired document is locked

- Set all dialog fields as **disabled** (except for comments and opening the document in a new window).
- **Hide** the "Delete" (trash bin) button.
- Set the **Save** button to **disabled** with a tooltip: _The expense cannot be updated because the document is locked._
- Add a **lock icon** next to the paired document (only if it is locked).


### When transaction is "Canceled"

A. When transaction doesn't have paired document yet
* button "Upload document" is not displayed on the grid and in transaction detail and in kebab menu
* All fields in the transaction detail are disabled
* Orange message "Canceled transaction" with description "It's impossible to upload document to the canceled transaction"
* Buttons "Save" and "Pair with the document" are disabled
B. When transaction has paired document
* Transaction behaves as usual (exception -> pairing behavior)
* When document is removed via detail -> behavior is like in A scenario, button "Save" only removes document but don't create new document
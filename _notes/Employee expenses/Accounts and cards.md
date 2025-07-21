### Empty state

When the user who has the right of spend management in the organization that doesn’t have any bank connection (in Spend management section and historically didn’t have) must see the following information when he goes to “Accounts and cards”: https://www.figma.com/file/mMzX5EmK2hq8wibxPp5eDk?kind=file&node-id=3346-55383&page-selector=0&t=SV6Rao38uePni7Zc-1&viewer=1

When the button “Connect account of Ceska Sporitelna” user is redirected to the connection page from Ceska Spoitelna

When user clicks on “Online consultation for free” he is redirected to the [https://www.wflow.com/konzultace](https://www.wflow.com/konzultace)

---

### Account is connected


**Navigation side panel menu:**

The section “Employees expenses” goes after the “Storage” section
The “Employees expenses” includes the following subsections:

- Personal expenses:
    - Overview of cards
    - Expenses
- Transactions
- Accounts and cards

### Accounts and cards

**Breadcrumbs:**
- Accounts and cards: organization name → employee expenses

**Linked bank accounts (section)**
- displays bank accounts that are connected to the current organization
- if there is more than one account, display each account as a separate column
- if there are more than 3 accounts, the slider component is available
- cards that are connected to the bank account are displayed in the table beneath
- each connection has an expiration date with the kebab menu:
    - Update connection with the bank (expiration date is in 6 months???, confirmation message)
    - Cancel connection with the bank (confirmation message???)
        - when the account is disconnected, cards and transactions remain, card status is not displayed anymore, card limits are no longer visible in the card detail, accounts disappear)
- Name of the account
- Quantity of the connected cards (the chip). Don’t show if there is 0
- Account number/ bank code
- Available balance: number with two decimals
- Currency: country flag + currency code

**Cards table**

- Search bar. It's not case-sensitive. Ignores diacritics. Search is available by:
    - alias, cardholder’s name
    - user
    - account number
    - last digits of the card
    
- “Card” column:
    - Icon of the card type (Visa, MasterCard etc.)
    - Name of the cardholder or alias
    - last four digits of the card: **** 1234
    - sorting by alphabetical order of the cardholder or alias (descending, ascending)
    
- “User” column: has sorting
    - Avatar
    - User name
    - User e-mail
    - “Assign user” button if there is no assigned user
        - dialog window “Assign user”. Only one user can be selected
        - description “Select user to assign this card to”
        - selector “Select user”: with the placeholder “Select a user”, the list of user names with emails, full text search
        - button “Cancel”.
        - button “Confirm”
    
- “Account” column
    - account number / bank code

- “Card status” column
    - Active
    - Inactive
    - Blocked
    - Unknown
    
- Kebab menu
    - Edit card
        - the same dialog described above
    - Add user (if user is not assigned)
        - the same dialog described above
    - Delete user (if user is assigned)
        - Confirmation message appears with the description “User will be removed but his transactions remain”
        - “Cancel”, “Remove” buttons
    
- Pagination
    - 10 items per page by default
    - possible to set 10, 20, 30, 40, 80 items per page

#### **Connection expiration**

_**When the expiration date is in less than 14 days**_

- The user is notified about expiration when the expiration date is in less than 14 days
- Notification goes as the bar that is visible throughout the organization + email notification
- Notification bar with the text “Your connection with the bank account expires in less than 14 days. Update your connection as soon as possible. + button “Update connection” that redirects to the “Accounts and cards” page (Orange color)
- Button “Update connection” is displayed in account section as well

_**When the connection is expired**_

- Notification goes as the bar that is visible throughout the organization + email notification
- Notification bar with the text “Your connection with the bank account has expired. Update your connection as soon as possible” button “Update connection” that redirects to the “Accounts and cards” page (Red color)
- All accounts disappear.
- Instead, the red box is displayed:
    - Connection with your bank account has expired. To save the functionality access to the bank account must be confirmed again via login to the internet banking
    - “Cancel the connection” button
    - “Update the connection” button
- cards are still displayed
- error message appears "Something gone wrong. Connection of your account with the bank has been expired"

_**When the account is disconnected (but was connected before)**_

- cards and transactions remain
- The blue box is displayed instead of accounts:
    - Connect the company’s bank account. Have again the overview of the expenses of your employees in real time.
    - “Connect bank account” button

#### Card detail

_**“Overview” section**_

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
        - Email to upload document + copy button [[Transaction and document pairing]]
    - The “Incoming invoices” selector, is required. Placeholder “Select document type”
        - Only Incoming Invoice types are displayed. There is a full-text search
        - Email to upload document + copy button
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
    

**The card status is unknown**

- Card name + last 4 digits
- Account number
- Expiration
- Valid from
- Visual of the grey-blocked card
- User info

**The card is not active**

- everything remains the same as for the active one but the blue message is displayed:
    - The card is not active yet. Activate your card in the George application or contact the administrator

**Card is blocked**

- everything remains the same as for the active one but the red message is displayed:
    - The card is blocked. Contact administrator for more information

#ExternalPeople
#Registers

##### Partners #Partners 
Partners can be set also in [[Document detail. Incoming Invoice]]
It's possible to create partner with duplicate email
When partner is being created - language and currency are automatically filled according to the organization settings


> [!NOTE] Duplicate validation
> if only IC is filled - validation by IC
> if only DIC is filled - validation by DIC
> if IC and DIC are filled - validation with condition AND


**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Search by ID number or VAT number" search panel: #ARES 
	*  the same search panel can be found in [[Organization profile]]
	* search is carried out with the help of [[ARES]] service API 
	* when organization is found the following fields are automatically filled:
		* Legal name
		* Address
		* ID
		* VAT ID (if such registered, can not be in Not VAT payer organizations)
		* Bank account number (if such registered in ARES)
* BASIC DATA section
	* ==**Contact information==
	* Legal name. Can be automatically filled with ARES. Required
	* Address. Can be automatically filled with ARES
	* ID.  Can be automatically filled with ARES
	* VAT ID. Can be automatically filled with ARES
	* Local VAT number input
	* Registration in business register input
	* "Phone No" input
	* Email address input. Valid format must be filled
	* "Language" selector
	* "Note" input
* BANK section
	* ==** Main Bank account==
	* Bank account number. Can filled with ARES
	* Currency selector. Is required
	* IBAN input
	* BIC input
	* ==** Other bank details==
	* button "Add bank account"
		* when is clicked the same fields appears as for Main bank account
		* "recycle bin" appears to remove the bank account
		* possible to add as many bank accounts as user wants
		* possible to save with empty bank accounts

**Conversion from account number to IBAN (for both the partner and on the document):**
- If the account number does not include a bank code → do **not** convert to IBAN (keep it as is)  
    Otherwise → perform the conversion to IBAN
    
**Conversion from IBAN to account number (for both the partner and on the document):**
- If the format is not IBAN → return as an account number without conversion


* ORDERS section
	* ==**Orders== 
	* "Delivery period" number input (days)
	* "Minimum order total" number input with decimals (amount)
	* "Tolerance of difference between the amount of orders and invoices for automatic pairing" number input
	* "Valid" toggle - if true, register will be available throughout organization in [[Document detail. Incoming Invoice]]
	* "Supplier"/"Customer" checkboxes, both can be checked at the same time
		* supplier - partner will be available for Orders, Incoming Invoices and Receipts
		* customer- partner will be available for Outgoing Invoices, PPD
		* supplier/customer - for others
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "IsValid" - TRUE or FALSE, is required
* LocalVAT
* AccountNumber
* BankCode
* IBAN
* BIC
* Note
* PhoneNo
* MailAddress
* DeliveryPeriod
* MinOrderTotal
* Tolerance
* Language
* Currency
* BusinessRegisterRegistration
* Customer
* Supplier
* IC
* VAT
* Name
* Address

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics
* When searching in the register, prioritize showing exact matches (from the beginning). Display priority:

1. Exact match
2. Starts with
3. Full text

**Columns:
* Name. Has sorting
* Supplier
* Customer
* Address. Has sorting
* ID. Has sorting
* VAT. Has sorting
* Recycle bin. Removes the register

---



##### External people #ExternalPeople 

**Button "Add"**. When is clicked dialog window of register creation appears:
* "From the dial" selector. Offers all existing people. When option is selected all corresponding fields in the form are automatically filled
* Personal data
* "Name" input, required
* "Surname" input, required
* "E-mail". Validation on the valid format, required
* "Telephone number" input, validation on the valid format
* Address
* "Street" input
* "Zip code" input
* "City" input
* "Partner" selector. Offers all existing #Partners 
* Other
* "Role in Signi" selector: [[Contracts]]
	* Approver
	* Signer
	* Inserts a stamp
* "Valid" checkbox
* "Add" button. Creates new person

**Search bar**:
* full text search by email, name and surname

**Columns**:
* E-mail. Has sorting
* Name. Has sorting
* Surname. Has sorting
* Street. Has sorting
* City. Has sorting
* Zip code. Has sorting
* Phone No. Has sorting
* Role. Has sorting
* Recycle bin. Removes the person


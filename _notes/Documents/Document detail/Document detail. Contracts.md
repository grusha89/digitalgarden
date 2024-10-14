
### Contract fields

#### General info

* **Document type
	* read only
* **Subject
	* works as the description
	* text input
* **Number
	* text input
* **External designation
	* text input

#### Counterparty section

* **Counterparty
	* partner selector
	* full text search
	* button "Next" to upload the further values
	* button "+" opens the dialog. The dialog window is the same as in [[Contacts]] #Partners
* **Address of counterparty
	* text input
	* can be automatically filled when partner is chosen from selector
* **ID number of the counterparty
	* text input
	* can be automatically filled when partner is chosen from selector
* **Counterparty's VAT
	* text input
	* can be automatically filled when partner is chosen from selector
	* has validation on unreliable VAT payer. More info can be found in [[Customization. Validations]]  and [[Document detail. Validations]]
* **Counterparty's local VAT
	* text input
	* can be automatically filled when partner is chosen from selector
* **Bank account number + bank code
	* text input
	* can be automatically filled when partner is chosen from selector
* **IBAN
	* text input
	* can be automatically filled when partner is chosen from selector
* **BIC
	* text input


#### Dates

* Date of issue
* Valid from
* Valid to
* Effective from
* Effective to
* Date of signing
* To review
	* if the review date  is today or in the past - there is the warning for it on the [[Dashboard]]
	* also Notification can be turned off for contracts that are waiting for review [[wflow.com WIKI/Settings/Notifications|Notifications]]


#### Financial data

* Currency
	* currency code selector
* Total amount
	* number input
	* placeholder "0.00"

### Signatory parties

Users for signature are being assigned here
Signing is carried out via third party application "Signi". Integration can be set in [[Integrations. Signi]]
Users (external and internal) can be selected from registers that are set in [[Contacts]] [[wflow.com WIKI/Other settings/Registers administration/Organization]]

Section consists of:
* "Signi status" icon + the name of the status:
	*  Contract not sent
	* The contract is waiting for an answer
	* Contract rejected
	* The contract has expired
	* Contract signed
* Draftsman section
	* person from organization
* Counterparties
	* person from the partner
* Button "Add"
	* dialog window appear where persons for draftsman and counterparties are selected or manually filled:
		* "From the dial" selector - the list of the organization persons
		* "Name" field (required)
		* "Surname" field (required)
		* "E-mail" field (required)
		* "Telephone number" field
		* "Street" field
		* "Zip code" field
		* "City" field
		* All the personal data can be automatically filled with data from the register
		* "Partner" selector (Only for counterparty). The list of the available partners
		* "Role in Signi" selector: Approver, Signer, Inserts a stamp
		* "Valid" checkbox 
		* "Save to dial and add" - will save the person to the registers. Appears when all required fields are filled
		* "Add" - Adds person as draftsman/counterparties. Becomes available when all required fields are inserted
	* Added person can be edited via button "Edit (pencil)" or removed via button "Remove (bin)". Several person can be added to the same position
	* "Impose" button - closes the dialog window
	* "Send for signature" - sends document via Signi to the counterparties

### Signing process

1.  When the document is sent to counterparties each of the person receives the email invitation to Signi
2. Each person signs or approves (depending on the Signi role that was assigned to him)

### Changes in document detail after the document is signed

* Signi status changes into "Contract signed"
* Signed document is added and becomes main
* Document with the logs is added

---

### Contract flow

1. Not confirmed
2. Filled
3. Waiting to be sent to ERP
4. Sent to ERP


> [!important] Dependency on automation workflow
> * The presence of certain flow statuses and corresponding actions depends on automation workflow settings [[Workflow automations]]
> * If workflow has certain flow action turned off (e.g. sending to ERP), sending to ERP action is not available for the kind/type and ERP flow statuses are not displayed



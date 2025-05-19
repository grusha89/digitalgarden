#AccountingRules
#ChartOfAccounts
#VatReturnLines
#VatControlStatementLines
#VatReverseChargeCode
#CommitmentType 
#Registers
### Accounting rules #AccountingRules 

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is not required
* "Kind of document" selector: 
	* Incoming Invoice
	* Outgoing Invoice
	* Receipt
	* PPD
* "Valid" checkbox - if true, register will be available throughout organization in [[Document types]], [[Document detail. Accounting fields]], [[Bulk actions]]
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is not required
* "IsValid" - TRUE or FALSE, is required
* "Kind" - required

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics
* When searching in the register, prioritize showing exact matches (from the beginning). Display priority:

1. Exact match
2. Starts with
3. Full text

**Columns:
* Code. Has sorting
* Description. Has sorting
* Kind of document. Has sorting
* Valid
* Recycle bin. Removes the register

---

### VAT Return Lines #VatReturnLines 

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is not required
* "Reverse charge" checkbox: 
	* if TRUE, then it will be allowed to select #VatReverseChargeCode  on the [[Document detail. Accounting fields]]
* "Valid" checkbox - if true, register will be available throughout organization in [[Document types]], [[Document detail. Accounting fields]], [[Bulk actions]]
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is not required
* "IsValid" - TRUE or FALSE, is required
* "ReverseCharge" - required (TRUE/FALSE)

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics

**Columns:
* Code. Has sorting
* Description. Has sorting
* Reverse charge. Has sorting
* Valid
* Recycle bin. Removes the register

---


### Chart of accounts #ChartOfAccounts 
### VAT Control Lines #VatControlStatementLines 
### VAT reverse charge code #VatReverseChargeCode 
### Commitment Type #CommitmentType 


**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is not required
* "Valid" checkbox - if true, register will be available throughout organization in [[Document types]], [[Document detail. Accounting fields]], [[Bulk actions]]
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is not required
* "IsValid" - TRUE or FALSE, is required

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics

**Columns:
* Code. Has sorting
* Description. Has sorting
* Valid
* Recycle bin. Removes the register


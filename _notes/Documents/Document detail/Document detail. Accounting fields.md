
##### General info

**How to manage accounting values:**
* creation of new registers
* visibility of the registers (only valid values are displayed in document detail)
can be found in Register Administration [[Accountant]]

**How to manage accounting fields:**
* validation (when accounting field must be filled)
can be found in [[Customization. Field settings for ERP]]
[[Customization. Validations]]

> [!important] Visibility of the accounting fields
> Visibility of accounting fields depends on the settings in [[Customization. Field settings for ERP]] . If the accounting field is excluded from organization it's not being displayed in the accounting section for document detail

**How to manage automation of accounting fields:**
[[Document types]] (when accountings are preselected and automatically filled for certain document types)
[[Workflow automations]] (when accountings can be filled with another values according to the workflow automation)


> [!important] Contracts
> Contracts don't have accounting fields


> [!NOTE] Document flow status
> When accounting fields are filled document doesn't become "Filled" it remains in status "New document"

Accounting fields are mostly selectors. The selector behavior:
* when clicked drop down list appears
* each value in the list consist of the code (name) and description
* the list is scrollable
* button "Next" is displayed if there are more than 10 values in the list
* when "Next" is clicked the following 10 values upload
* only valid values are displayed
* value can be searched by name and description
* search is not case sensitive and ignores diacritics
* when value is not found "No data" is displayed
* if not valid data was input, validation appears "Unknown value"

---

##### Accounting fields overview

1. #CatalogOfItems  : 
	1. accepts custom value besides the listed ones
2. #CostCenters 
3. #Contracts 
4. #Activities 
5. #AccountingRules 
	1. available only for Incoming Invoice, Outgoing Invoice and Receipts 
	2. available also for Orders but values only assigned to Incoming Invoice
6. #ChartOfAccounts 
	1. goes as Contra Account in document detail
7. #PaymentMethods 
	1. available only for Incoming Invoice, Outgoing Invoice and Receipts 
	2. available also for Orders but values only assigned to Incoming Invoice
8. #CommitmentType 
9. #CashDocumentTypes 
10. **Use the VAT reduction - checkbox
11. #VatControlStatementLines 
12. #VatReturnLines 
13. #VatReverseChargeCode 
	1. depends on the VAT return line (editable or read only)
	2. can be edited when VAT return line is empty
14. #CashRegisters 
15. **VAT supply mode code - selector with defined values
	1. Normal supply
	2. Special scheme for travel service
	3. Special scheme for used goods
16. **VAT regime - selector with defined values
	1. Standard
	2. PDP
	3. Reverse charge
	4. Excluded from VAT
	5. Domestic in foreign currency
17. **VAT fixed assets - checkbox
18. #Employees 
19. #Vehicles 


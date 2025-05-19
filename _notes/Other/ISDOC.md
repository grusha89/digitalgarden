
### Processing ISDOC via collecting emails

1. When ISDOC with the error is received - file is uploaded as PDF that can be sent to extraction
	* ![[Error ISDOC.pdf]]
2. When ISDOC and PDF have the same name -> data will be extracted from ISDOC, PDF will be set as the main file
3. When ISDOCx is processed -> data will be extracted from ISDOC, PDF as the main file, ISDOC as attachment
4. When ISDOC and PDF with different names -> data will not be extracted from ISDOC, as nothing will be marked as the main file
5. When ZIP file is processed -> data will be extracted from ISDOC, PDF as the main file, ISDOC and other as attachments


### ISDOC and Review

It is possible to send ISDOC to review as other extracting documents:
* manually via single, bulk actions
* via workflow automations
* ISDOC sent to review can be found in "To review" folder along with other documents that needed to be reviewed in Rossum
* there is no Rossum embedded in ISDOC document detail

##### Reviewing process

* When the changes are not made -> button "Confirm" is displayed
	* When "Confirm" is clicked ISDOC gets status "Reviewed" and disappears from "To review" folder
* When the changes are made -> button "Save and confirm" appears with the hidden second option "Save" (it will only save the changes without confirmation)


### What data is extracted from ISDOC

* description
* document number
* order number
* variable symbol
* constant symbol
* Partner info: name, address, IC, DIC, local DIC
* bank details of Partner: bank account, IBAN
* dates
* currency
* recapitulation
* rounding amount
* total amount
* lines
* custom properties
	* Process according to the identifier of the optional field (referred to below as "properties") – if the field is not defined in the organization, the value obtained from the ISDOC will be ignored.

### ISDOC and Credit Note (dobropis)

When ISDOC with the "Credit Note" invoice type is processed -> invoice type in document detail must be automatically set as "credit note"

![[dobro isdoc.isdocx]]



### ISDOC from not VAT payer

When ISDOC goes without recapitulation -> amounts will be filled in zero rate recapitualtion in document detail 

![[Vydan† faktura - 20230011-invoice (1) (1).isdoc]]


### ISDOC and export

It is possible to export documents in ISDOC format from wflow
Detailed info can be found in [[Grid. Exports]]
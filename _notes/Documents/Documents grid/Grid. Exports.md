

Selected documents can be manually exported to the required format for importing it to the ERPs that wflow doesn't have API integration with
#### "Export" button

Opens the list of the available exports.
Exports that are default:
* Money S3 #MoneyS3 
* Money S4/S5 #MoneyS4/S5 
* Kros - OMEGA SK #OMEGAKros 
* PREMIER #PREMIER 
* Excel #Excel 
* ISDOC #ISDOC 
* XML #XML 
* MRP #MRP
* DATEV #DATEV 
* Byznys Solitea #ByznysSolitea 

#### "Edit" button

Opens the setting page that is identical to the [[Integrations. Export]]


---

##### Money S3 #MoneyS3

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* Sequence input - required. It will be applied if the document doesn't have any selected sequence
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

Features:
* XML format
* Datum uplatneni = Doruceno (in XML) is filled with Date of case from wflow
* Sequence selected in document detail has higher priority than sequence set in the dialog window
* If sequence is not filled in document detail then the sequence set in the dialog window is applied
* Partners tag \<DobOdb> contains \<ObchNazev> and \<ObchAdresa> [MoneyS3 developer's info](https://money.cz/navod/s3xmlde/)
* <xs:element name="Druh" minOccurs="0"> xs:annotationxs:documentationDruh faktury:
	* N - normální (default) 
	* L = zálohová 
	* F = proforma 
	* D = daňový doklad k přijaté platbě![[__Faktura.xsd]]
---

##### Moneys S4/S5 #MoneyS4/S5

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Select document type in Money S4/S5" selector (only for Receipts):
	* Sales received
	* Receipts
	* Commitment documents
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

Features:
* if document doesn't have lines, they will be automatically exported on the base of recapitulation
* Receipts are exported with selected kind in dialog window

---

##### OMEGA Kros #OMEGAKros
Slovakian ERP system

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Receipt type" selector (only for Receipts):
	* Receipts
	* Internal documents
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

Features:
* SK legislation
* [[Import_a_export[1].pdf]]
* [[ImportExport_20_60 (1).xls]]

---

##### PREMIER #PREMIER

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

Features:
* XML format
* if document doesn't have lines, they will be automatically exported on the base of recapitulation

---

##### Excel #Excel

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Export including document items" checkbox
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

Features:
* contains all columns

---

##### ISDOC #ISDOC

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Format":
	* XML document (ISDOC) - exports only ISDOC file
	* XML Document with Attachments - Archive (ISDOCX) 
	* XML document ISDOC with main file - (ZIP)
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

---

##### XML #XML

For Outgoing Invoice:
- these elements in every exported documents should by presented (only when appropriate values are presented in Organization profile):
	- \<MyAccountNo>\</MyAccountNo>
	- \<MyBankCode>\</MyBankCode>
	- \<MyIBAN>\</MyIBAN>
	- \<MyBIC>\</MyBIC>

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

---

##### MRP #MRP 

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

Features:
* "OriginalDocumentNumber" is filled with "Tax document Number". If Tax document Number is empty, ODN is filled with document number (Incoming Invoice, Receipt)
* if the invoice type in wflow is set as Proforma, XML looks like: \<InvoiceType>X\</InvoiceType>

---


##### DATEV #DATEV

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button

---

##### Byznys Solitea #ByznysSolitea

Dialog window:
* if one or more documents selected the dialog window contains the following message "Only marked documents will be included in the export"
* if none of the documents selected the dialog window contains the following message "All documents that meet the currently valid filter condition will be included in the export, regardless of paging"
* "Mark as Sent to ERP" toggle. Tooltip - "The processing status of the exported documents will change to "Successfully sent to ERP" and the documents will be locked
* "Export" button
---


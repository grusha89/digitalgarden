
Internal number import is needed when documents are exported to ERP system manually. Internal number that is assigned to the document by ERP can bed imported to wflow to the corresponding documents.

***Download an example template***
Downloads excel file with the detailed description how internal number import works and with the table for import itself

There are two ways how to import internal number:

1. Fill in GUID of the document and the internal number itself
2. If GUID is unknown, the following values must be filled at once:
	1. Document kind. It's number equivalent:
		* 0 - Incoming Invoice
		* 1 - Outgoing Invoice
		* 2 - Receipts
		* 7 - Income Cash Receipts
		* 3 - Orders
		* 6 - Contracts
		* 5 - Others
	2. VAT or ID
	3. Document number
	4. Total amount
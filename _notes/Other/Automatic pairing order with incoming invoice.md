
Pairing can be turned on and configured in [[Organization profile]]

### Pairing on the base of order number

1. When "Only the order number should be taken into account when matching" is turned on
2. When order is created it gets its unique automatically generated number. To manage automatic sequence of the order go to [[Number series]]
3. When incoming invoice is created and it has the same order number in the "Order number" input 
4. Result: incoming invoice is automatically paired to the order

### Pairing on the base of other fields

1. When "Only the order number should be taken into account when matching" is turned off
2. When order is created 
3. When incoming invoice is created with the same following values as the order:
	1. Order number
	2. Partner
	3. Total amount
4. Result: incoming invoice is automatically paired to the order

### Automatically transfer billing numbers on the header to the received invoice

1. When "Automatically transfer billing numbers on the header to the received invoice" is turned on
2. When order is created:
	1. accounting fields are filled on headers
	2. order is confirmed and marked as delivered
3. When incoming invoice is created:
	1. The same order number is filled (if pairing works on the base of order number only)
	2. The same order number, partner, total amount are filled (if pairing doesn't work on the base of order number only)
4. Result: incoming invoice is automatically paired to the order and inherits order's accounting values on headers

### Automatically transfer items of paired order to incoming invoice

1. When "Automatically transfer items of paired order to incoming invoice" is turned on
2. When order is created:
	1. accounting fields are filled on the lines
	2. order is confirmed and marked as delivered
3. When incoming invoice is created:
	1. The same order number is filled (if pairing works on the base of order number only)
	2. The same order number, partner, total amount are filled (if pairing doesn't work on the base of order number only)
4. Result: incoming invoice is automatically paired to the order and inherits order's accounting values on the lines

### Automatically accept approval flow from order to incoming invoice

1. When "Automatically accept approval flow from order to incoming invoice" is turned on
2. When order is created:
	1. approval path is assigned and completely approved
	2. order is confirmed and marked as delivered
3. When incoming invoice is created:
	1. The same order number is filled (if pairing works on the base of order number only)
	2. The same order number, partner, total amount are filled (if pairing doesn't work on the base of order number only)
		1. tolerance can be set to avoid the strictness for total amount
		2. if the order and total amount are in the different currencies than organization's currency:
	* tolerance amount is still taken into consideration, it will recalculated according to the actual currency exchange
4. Result: incoming invoice is automatically paired to the order and inherits order's approval path

##### Consider the amount for taking over the approval route

* In this case total amounts must be strictly the same (if pairing works on the base of order number only
* tolerance amount can be set to avoid the strictness 
* if the order and total amount are in the different currencies than organization's currency:
	* tolerance amount is still taken into consideration, it will recalculated according to the actual currency exchange


### When order and incoming invoice are paired

Linked document section in document detail

From the view of the ==incoming invoice document detail==:
	* Approval status
		* Approved
		* Not approved
		* Disapproved
		* Returned
	* Delivery status
		* Delivered
		* Partially delivered
	* Partner name
	* Supplier Address
	* Supplier IC
	* Supplier VAT
	* Total amount
	* Date of issue
	* Remains to deliver
		* calculated on the base of "Total amount without VAT" of the order minus "Total amount without VAT" of the incoming invoice minus "Paid by deposit" if such presented
		* amount is displayed with the currency of the document 
		* if invoice type is "Proforma" - remains to deliver is not being calculated 

* From the view of the ==order document detail==:
	* Remains to deliver
		* calculated on the base of "Total amount without VAT" of the order minus "Total amount without VAT" of the incoming invoice minus "Paid by deposit" if such presented
		* amount is displayed with the currency of the document 
		* if invoice type is "Proforma" - remains to deliver is not being calculated 
	* incoming invoice number (Incoming invoice: document type name)
	* Partner name
	* Supplier address
	* Supplier IC
	* Supplier DIC
	* Total amount
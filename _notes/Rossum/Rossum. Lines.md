
Lines in Rossum contain the following fields:

* Business item = Code (wflow)
* Code:
	* duplicates "Business item" field during transition to wflow
	* When "Business item" is not filled, value of "Code" is exported to wflow's "Business item" field
* Description
* VAT rate
* Total with VAT
* Cost Center
* Activity
* Contract
* Accounting rule
* VAT control statement lines
* VAT return lines
* PDP code
* Employee
* Vehicle


- If no rate is entered in Rossum on lines, it will be extracted into the workflow as a zero rate.
- If the unit price is not entered in Rossum, a zero amount will be extracted into the workflow.
- When an item is added in Rossum, the base amount for the item will not be recalculated based on the total amount on the invoice.
- If the quantity is not extracted in Rossum, the value transferred to the workflow will be 1


**ROSSUM Calculation During Export**

a) **Quantity + Unit Price** (when only these fields are filled in)
- During export to the workflow, calculate the base amount as:  
    **Base = Quantity × Unit Price**

b) **Total with VAT + VAT Rate** (when only these fields are filled in)
- Calculate the base amount as:  
    **Base Amount = Total with VAT / (1 + (VAT Rate / 100))**
- Set the unit price as the base amount.
- Set the quantity to "1."
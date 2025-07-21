
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

### Lines template selector

Organization has to have at least one line template in order to use this feature [[Items]]
Changes made in Lines template are automatically synchronized with Rossum

- **Disable prediction** for the dropdown.
- The default value should be **"Not Selected"**.
    - After selecting a template, the label "Not Selected" in the dropdown will change to **"Selected: {template name}"**.

###### Functionality:

1. **Automatic Overwriting of Items:**
    - When a customer selects a template, all existing items are automatically overwritten with the items from the selected template.
2. **For Percentage-Based Templates:**
    - The items are calculated according to the same logic as in **wflow**.
3. **If "Total Base" is Not Filled:**
    - Items are added with zero amounts.



---
### Automatic Lines calculation

##### Automatic Calculation During Export

The goal is to have as many cases as possible with pre-calculated amounts for "Unit Price (Excl. VAT)" and "Total Base Amount."

- Calculation priority:
    1. **Priority 1:** Quantity, Unit Price (Excl. VAT), VAT Rate
    2. **Priority 2:** Quantity, Total Base Amount, VAT Rate
    3. **Priority 3:** Quantity, Total Amount (Incl. VAT), VAT Rate
- Perform calculations **after validation** in ROSSUM.
- If quantity is missing, assume it as "1."

In a situation where we calculate the base amount from the total including VAT and the VAT rate, we must respect the quantity and accordingly enter the unit price without VAT and the VAT base.
##### Manual Calculation in ROSSUM

- Add a custom button **"Recalculate Item Amounts"** in the ROSSUM scheme as per the documentation:
    
    [Rossum Extensions Overview](https://developers.rossum.ai/docs/extensions-overview)
    
- Add button “**Recalculate Item Amounts" after Line items (before lines template)**
    
- Upon clicking the button, calculations should be performed based on:
    
    1. **Priority 1:** Quantity, Unit Price (Excl. VAT), VAT Rate
    2. **Priority 2:** Quantity, Total Base Amount, VAT Rate
    3. **Priority 3:** Quantity, Total Amount (Incl. VAT), VAT Rate
- **Recalculate all relevant fields:**
    
    - Quantity
    - Unit Price
    - Base Amount (Excl. VAT)
    - VAT Rate
    - Total Amount (Incl. VAT)
    - VAT Amount
- **Only process items without validation errors** on the respective row.
    
- **Round all values to four decimal places.**
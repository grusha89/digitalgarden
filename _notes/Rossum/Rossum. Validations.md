
### Summary of Rossum Validation Requirements

 **1. Translation of Validation Messages**
- Translate all validation messages in Rossum into every language currently supported in the system.

**2. Differentiating Warnings and Alerts**
- Implement functionality to display differences in amounts for certain validations.
- Split some validations into **warnings** and **alerts** as per the requirements outlined in [this spreadsheet](https://docs.google.com/spreadsheets/d/1fLaCOh_4LWHX1tFxDW2WW9oHu2zh97Oo4XIBw0OkWgI/edit?usp=sharing).

### Recapitulation

 1. Recapitulation vs Total base

- **Mismatch in totals**:
    - **Warning:** "Amounts in the summary do not match the VAT base."

2. Rekapitulation - Missing Fields or Incorrect Calculations

* Missing Fields: Highlight missing fields at the row level.
* Calculation Errors:
    - **Warning** on the header and respective rows: "Amounts in the rate row do not match."

3. Rekapitulation - Field Format Validation

- Validate for:
    1. **Non-numeric Characters** in fields.
    2. **Field Length**:
        - **Rate:** Max 4 digits, 2 decimal places.
        - **Base Amount (Základ daně):** Max 18 digits, 2 decimal places.
        - **Tax Amount:** Max 18 digits, 2 decimal places.

---

### Total amount

1. Total Amount Validation
	- Formula: **Total Amount = Total VAT Amount + Rounding Amount - Advance Payment**.
	- **Warning:** Show the difference if the formula is violated.

---

### Recapitulation Row Validation

- If a field in the row is missing:
    - Export the row only if amounts match.
    - Highlight missing fields with warnings.

---

### Line Items

1. Ignore missing fields during validation.
2. Compare line VAT base totals with the "Total VAT Base" field in summary.
    - **Warning:** "Line totals do not match the VAT base."
3. Autofill:
    - **Quantity:** Default to 1 if missing.
    - **Unit Price:** Calculate from the line base amount if missing.

---

###  ARES Validation 

- For partner VAT status:
    - **Warning:** "This is an unreliable VAT payer." 
    - **Icon Indicators:**
        - Blue icon: "Reliable VAT payer."
        - Warning: "Account is not registered for VAT."
        - Information: "Partner is not a VAT payer."

---

###  Auto-Cleaning Partner Identifiers

- Remove spaces in **IČ**, **DIČ**, or **IČ DPH** during extraction.

---

### Other Fields

1. **Warnings:**
    - Missing document number.
    - Constant symbol exceeding 10 characters.
    - Missing value in any accounting-related field.

---

### Variable Symbol (VS) Validation

- Validate to ensure no alphabetic characters, slashes, or dashes during extraction.

---

### Rounding Decimals

- Round to the supported number of decimals for all fields with decimal precision during initial extraction.


---

###  Partner Non-VAT Payer Validation

- Additional Rules:
    - Hide VAT-related fields if **DIČ** is not valid or the partner is a non-payer.
    - Adjust logic for non-VAT payer invoices:
        - Exclude summary validations.
        - Assign "Total Amount" as the base for 0% VAT rate.
    - Add info: "Partner is not a VAT payer" next to the IČ field.

---

### Displaying Differences

- Add **difference value** to validation messages for:
    1. VAT Base mismatch.
    2. Total Amount mismatch.
    3. Summary amount mismatch with the VAT Base.

Example:  
**"Amounts in the summary do not match the VAT base. Difference: 150.00."**

---
### Validation tolerance

Validations are always displayed, even in cases of small differences in the amount.

**Target State:**

Small discrepancies will not be shown as warnings but only as information (blue "i" icon). A tolerance of up to 0.3 CZK will be applied.

**Description:**

- Applies only to invoices in CZK, EUR, USD, PLN, and HUF (fixed according to the exchange rate on the development date).
- No changes for other currencies.
- Applies only to validations that display an amount difference.
- If the difference is less than 0.3 CZK, the same message should be displayed but as an informational notification (blue "i") in ROSSUM.

Amounts for other currencies

{ "CZK": 0.3, "EUR": 0.04, "PLN": 0.051, "USD": 0.044, "HUF": 4.83 }

---

### Summary Table for Validation Logic

| **Name**           | **Type** | **Min** | **Max** | **Regex**                 |
| ------------------ | -------- | ------- | ------- | ------------------------- |
| **DOCUMENT**       |          |         |         |                           |
| Number             | string   |         | 80      |                           |
| Internal code      | string   |         | 20      |                           |
| Variable sym.      | string   |         | 20      |                           |
| Constant sym.      | string   |         | 4       |                           |
| Specific sym.      | string   |         | 20      |                           |
| Account term       | string   |         | 7       |                           |
| VAT term           | string   |         | 7       |                           |
| Total amount       | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
| Total amount FC    | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
| Rounding amount    | decimal  |         | 3,2     | ^\d{0,3}?([,.]\d{0,2})?$  |
| Paid amount        | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
| Currency           | string   |         | 3       |                           |
| Exchange rate      | decimal  |         | 10,6    | ^\d{0,10}?([,.]\d{0,6})?$ |
| Partner IC         | string   |         | 10      |                           |
| Partner VAT        | string   |         | 15      |                           |
| Parnter Local VAT  | string   |         | 15      |                           |
| Partner name       | string   |         |         |                           |
| Partner address    | string   |         |         |                           |
| Partner email      | string   |         | 100     |                           |
| Account code       | string   |         | 20      |                           |
| Account number     | string   |         | 30      |                           |
| Bank code          | string   |         | 4       |                           |
| IBAN               | string   |         | 42      |                           |
| BIC                | string   |         | 15      |                           |
| Tag                | string   |         | 80      |                           |
| Business item code | string   |         | 20      |                           |
| External Id        | string   |         | 40      |                           |
|                    |          |         |         |                           |
| **VAT**            |          |         |         |                           |
| Rate               | decimal  |         | 4,2     | ^\d{0,4}?([,.]\d{0,2})?$  |
| Base               | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
| Tax                | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
|                    |          |         |         |                           |
| **LINES**          |          |         |         |                           |
| Total amount       | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
| Total amount FC    | decimal  |         | 18,2    | ^\d{0,18}?([,.]\d{0,2})?$ |
| Account code       | string   |         | 20      |                           |
| Currency           | string   |         | 3       |                           |
| Code               | string   |         |         |                           |
| Description        | string   |         |         |                           |
| Quantity           | decimal  |         | 18,6    | ^\d{0,18}?([,.]\d{0,6})?$ |
| Unit price         | decimal  |         | 18,6    | ^\d{0,18}?([,.]\d{0,6})?$ |
| VAT rate           | decimal  |         | 4,2     | ^\d{0,4}?([,.]\d{0,2})?$  |
|                    |          |         |         |                           |
|                    |          |         |         |                           |
### **Quick Dates Entry**

Add logic to ROSSUM for entering dates similar to the workflow.

For example:
- When "28" is entered, it will autofill as the 28th day of the current month and year.
- When "080623" is entered, it will reformat to 8.6.2023.

Scenarios:
- 6 → 06.09.2023
- 06 → 06.09.2023
- 0609 → 06.09.2023
- 612 → 06.12.2023
- 123 → 12.03.2023
- 060923 → 06.09.2023
- 06092023 → 06.09.2023

### Dates extraction and inheritance

**Issue Date:**
- Do not fill in based on anything – only extract  
    => **data type: captured**
    

**Receipt Date:**
- Fill in based on the issue date (if not already filled in)  
    => **data type: data**
    

**Taxable Supply Date (UZP):**
- Extract from the invoice  
    => **data type: captured**
    

**Case Date:**
- Fill in based on the UZP
    
- If UZP is not available, use the issue date  
    => **data type: data**
    

**Due Date:**
- Do not fill in based on anything – only extract  
    => **data type: captured**

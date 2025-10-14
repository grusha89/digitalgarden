
wflow AI is alternative extraction for Receipts. 
User can select and manage extraction via wflow AI in [[Integrations. Extraction]]

---

### Automatic `caseDate` Assignment 

* After extracting receipts using **wflow AI**, the system automatically sets the **`caseDate`** field based on the **DUZP** date  (Date of Taxable Supply).  
* If the **DUZP** value is not extracted,  the **Issue Date** (`dateOfIssue`) is used as the fallback value for **`caseDate`**.
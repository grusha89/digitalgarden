

Single component displays both an individual **budget** and a **group**; in the case of a group, all overviews and calculations are composed of the sums of all subordinate budgets.

---

### 🧩 Page Modes

- **Read only (view)** – the user has access but is not a “Budget Manager”.
- **Write** – the user has the “Budget Manager” permission or direct edit access.
    

---

### 🧭 Header

* Back button - Returns to the previous screen (e.g., budget list)|
* Page title:
	- `{Group name} – {Budget name}` (if it’s a budget within a group)|
	- `{Group name}` (if it’s a group detail)
    
- `{Budget name}` (if it’s a budget without a group) |  
    | Access-management component (interactive in `write` mode) |  
    | **Action button** (visible only in `write` mode) |
    

---

### 🔁 Period Switching

- At the top of the detail view there is a **slider for selecting a period**, showing one active period at a time.
    
- The displayed page content (chart, amounts, documents) always refers only to the selected period.
    
- **To the right of the slider** there is a button for adding a new period. When clicked, it opens a dialog to set up the budget at the second step with the new period (`last +1`) and the amounts copied from the last existing period.
    

---

### 📊 Summary – Fulfilment Card

A statistics card showing the budget spending overview for the entire period:

|Item Description||
|---|---|
|**Spent**|Sum of allocated amounts from documents (invoices, receipts, contracts)|
|**Ordered**|Sum of ordered amounts|
|**Overspent**|Amount by which the budget has been exceeded|
|**Ordered over budget**|Part of the orders exceeding the available budget|
|**Available**|Budget – (Spent + Ordered)|

- All amounts are rounded to whole numbers.
    
- Spending percentages are shown with two decimal places.
    

---

### 📈 Budget Fulfilment Chart

- Displays the monthly progress of budget spending.
    
- Starts from the initial month of the selected period.
    
- The live visualization reacts to period changes in the slider.
    

[Monthly spending chart](https://www.notion.so/Graf-erp-n-po-m-s-c-ch-35b99290a0e14216987b19c1826be58c?pvs=21)

---

### 📄 Documents

- A table with documents assigned to the budget in the selected period.
    
- Filters are applied by month and by spending status.
    
- Above the table is a “Documents” header with an information icon explaining that **the user only sees documents they have access to**.
    
- No actions on the documents are available in this section.
    

[Documents table](https://www.notion.so/Tabulka-dokumentu-3e9369dfb238454085d2d5cad0f54c31?pvs=21)

---

### 📑 Document Filters

- The selected filters (**period**, **spending**) apply to the entire page and affect the displayed statistics, chart, and list of documents.
    
- **Full-text search** is not available here.
    
- The user can change the period or spending filter in the detail view — these changes apply **locally to the detail view** without affecting the main list filter.
    
- When returning to the budget list, the filter used in the list (e.g., active year) remains unchanged.
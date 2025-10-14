
### Empty state

When there is no single budget or group in organization:
* Banner with the budget icon + text "No budget. You currently have no budget created"
* Button "+ Create a budget"

### Budgets and groups overview

#### Upper panel:
1. Button "+ Create budget" that can be unfolded into following options:
	1. "Create a budget"
	2. "Add a group"
2. Period slider
	* displays the budget period e.g (Jan 2025 - Dec 2025)
	* arrows back and forth to switch to the previous/following period
	* budgets that correspond to the period are displayed
	* start of the period can be set up in [[Organization profile]]
3. Search panel.
	* Budgets can be searched by only budget name
	* Groups are being ignored and not displayed when filter applies

#### Table:
1. Name
	* Name of the group/budget
2. Performance
	* Total amount spent within group/budget (linked incoming invoices, receipts, delivered orders)
3. Budget
	* Total budget for group/budget
4. Ordered
	* Total amount order within group/budget ( linked not delivered orders)
5. Available
	* Total amount that is available within group/budget + the amount of precents
6. Documents
	* The quantity of linked documents withing group/budget
7. Access
	* Icons of users and teams who has access to the budget 
	* Displays two icons: first one is user/teams, second one is quantity of the rest users/teams with "+"
8. Kebab menu:
	* for group:
		* + Create a budget
		* Edit
		* Remove
	* for budget:
		* + Add budget period
		* Adjust budget amounts
		* Budget settings
		* Click to copy
		* Remove
#### General behavior

- **Default state:** All groups are **collapsed**
- Budgets without a group are displayed separately
- **No pagination is applied** – all items matching the filter are loaded
- Data is loaded in two steps:
    1. first, all existing groups
    2. then, all budgets according to the selected filter (e.g., period)
- Aggregation and sorting are handled on the frontend:
    - Budgets are grouped by their groups
    - Default sorting: first by group name and budget name, then budgets without a group
- The period filter is default and mandatory – it determines active records according to the selected period
- The filter is implemented as a horizontal slider of available fiscal years:
    - Displays all years available within the created budgets as a horizontal slider. The entire list is not shown at once – the user can navigate between years using left and right buttons.
    - Only fiscal years that exist in the budgets and are accessible to the user are available for selection.
- Filter parameters (period) are also passed to the budget detail view, where they affect the display of statistics, charts, and documents. The user can change the filter in the detail view, and the change applies only there. When returning to the budget list, the original filter remains unchanged.
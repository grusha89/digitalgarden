
https://www.figma.com/file/J5SBwD5WRJG09r8FezNN8Q?embed_host=share&kind=file&node-id=73-3277&page-selector=0&t=zPwXhbJOccJK1md5-1&viewer=1

“Transaction” [[Transaction]] and  "Expenses" in [[Personal expenses]] pages have 5 filters:

- they represent as selectors where user can select conditions he needs
- filters are placed on the top of the table on the same line with the search panel
- when several filters are used at the same time they have “AND” condition
- selected filtres are memorized within the session

### Period

This filter finds transactions that are made during the period of time of selected condition

- It has icon of the clocks
- The list of conditions appears:
    - The whole period (has a blue tick, it means this condition is default)
    - Today
    - Yesterday
    - Last 7 days
    - Last 14 days
    - Last 30 days
    - This month
    - This quarter
    - This year
    - Custom:
        - “Custom” dialog window appears
        - “Date from” and “Date to” selectors
        - current dates are selected by default
        - button “Confirm’

### Document

This filter finds transactions according to the attached document status

- it has icon of the receipt
- The list of conditions appears:
    - All states ( it has a blue tick, it means this condition is default)
    - Without document
    - With proof
    - Marked without document

### Card

This filter finds transactions according to the selected card

- it has icon of the card
- the list of conditions appears:
    - All cards ( it has a blue tick, it means this condition is default)
    - individual card:
        - alias + 4 last digits of the card

### Approval

This filter finds transactions according to the approval status

- it has icon of the circled tick
- the list of conditions appears:
    - All states ( it has a blue tick, it means this condition is default)
    - Awaiting approval
    - Approved
    - Rejected
    - Without approval

### Currency

This filter is hidden when there transactions with only one currency

It appears when there is more than one currency is used

- it has icon of the coin
- has the list used currencies
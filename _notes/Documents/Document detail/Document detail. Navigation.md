
##### Navigation panel and document detail
    - default state: navigation on the grid/document detail is opened
    - changes are saved in the scope of local storage
    - navigation state in document detail is not affected by the navigation state on the grid and vice versa

##### Navigation arrows
* arrow "Go back to the grid"
* arrows "Switching between the documents"
	* are disabled if the first or the last document is opened

##### Breadcrumbs
* Organization name -> user goes to All documents
* Documents -> user goes to All documents
* All documents -> user goes to All documents
* Document kind -> user goes to the document type
* Document type -> user goes to the document type
---


##### Automatic transition

Toggle "Automatic transition" turns on/off the automatic transition
There is a tooltip

> [!info] What is automatic transition
> Automatic transition is a feature that allows to switch automatically to the next document when the document doesn’t fit to the current filter anymore

- Here are example steps how it works:
    1. User has 10 invoices for him to approve
    2. He has to go to folder “Approvals”
    3. Filter is already applied to this folder
    4. User opens first document
    5. Automatic transition is turned on
    6. He approves document
    7. As soon as the current document doesn’t need to be approved by this user it switches to the next document where user can continue approving and so on

* Before documents switch notification appears notifying user about automatic transition
"The active document is no longer available in this view. You were automatically redirected to the next document"

- Here are the rules of wflow memorizing toggle’s position:
    - It is constantly turned **ON** in folders “Approvals”, “All approvals”, “To review”
    - If you turn the automatic transition **OFF** in folders “Approvals”, “All approvals”, “To review” and go to the grid and return back - automatic transition will be turned **ON**
    - in rest folders automatic transition is turned **OFF** by default
    - if you turn automatic transition **ON** in one document type it will be remembered for all document types and kinds
    - once you turn automatic transition **ON** it stays in this condition until the daily session is over


**Persist "Automatic Transition" Setting in Database**

- "Automatic Transition" setting is saved in the NoSQL database at uisettings/continuos-work-state.
- The current feature behavior is maintained with no changes.

---


##### Drag and drop

Document detail data are separated in special sections

* Tags
* Approval path
* Main data
* Accountings
* Payment order
* Payment record
* Custom properties
* Linked documents

* Each section can be folded/unfolded
* It is possible to change the order of the sections using drag and drop
* Four arrows cursor indicates that section can be dragged 
* When section is dragged other unfolded sections collapse and get back to the previous state when section is dropped
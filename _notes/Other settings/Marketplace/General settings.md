
Integrations vie Marketplace is carried oud by third party integrator named "Prismatic"

##### When Marketplace is not opened yet

When user goes to the Marketplace for the first time he can see the empty page with the following details:
* some image 
* Marketplace API integrations - header
* Marketplace integration served to easily connect other applications and services with wflow via API. You can use our preset scenarios to connect supported applications. You can use the new integration designer to create your own scenarios
* We will continuously add integrations to other applications
* "Go to Marketplace" - button
* Marketplace service is included in the price of your plan. The use of some scenarios may be charged in the future


##### When Marketplace is opened
 
"Marketplace" section:
* all existing integrations are displayed
* search bar with a placeholder "Search integrations"
* Switch button "All"/"Activated"

"Designer" section: 
* displays designed integrations
* search bar with a placeholder "Search integrations"
* Filter. Dialog window appears when filter is clicked:
	* "Description" input
	* "Category" selector
	* "Labels" selector
	* "Show only templates" checkbox
	* "Has outdated components" checkbox
* "Add integration" button. When is clicked the dialog window appears with a three options:
	* Quickstart: Use the designer to build your integration from the ground up
	* Template: Choose a template to use as a starting point in building your customized integration
	* Import: Import an integration from a YAML definition

"Dashboard" section:
* appears only when organization has connected instances

---

* When new instance is created - new api client is created as well
* When instance is deleted - corresponding api client is being removed as well
* When the last instance is removed via dashboard → instance → delete integration - user must be redirected to Dashboard (doesn’t work now)

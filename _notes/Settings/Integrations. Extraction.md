
Choose a provider that will automatically extract data from your documents

##### Extraction settings

**Provider selector:**
* ROSSUM (direct integration of wflow.com) RECOMMENDED
* ROSSUM (Dativery integration) 
* None

**ROSSUM (direct integration of wflow.com) RECOMMENDED**
 * Connections status. Shows whether the access is granted or not
 * Predicate billing codes. Toggle. 
 * Documents: Incoming Invoice, Outgoing Invoice, Receipts
	 * Each document kind has a turn on/off toggle and toggle for turning on/off the items extraction
	 * If toggle of the document kind is turned off, toggle of item extraction is turned off automatically
* Optional fields: Add an optional field selector: #CustomProperties 
	* full text search by name and description
	* selector offers all custom properties and those that are not active on the document detail (see [[Customization. Custom properties]])
	* selected custom property disappears from the list
	* selected custom property is being added as the chip that can be removed by clicking on the cross on the chip
	* Detailed behavior of custom properties in Rossum can be found in [[Rossum. Custom properties]] 
* "Recycle bin" button - removes the whole integration. Has a confirmation message 
* "Cancel" and "Save buttons" - appear when changes are made
* "Synchronization" button - is displayed by default and after the changes were saved
	* button is needed in order to synchronize the changes made in wflow with Rossum settings
		* for example when organization language is changed 
		* or any changes in organization profile and in Rossum setting itself
		* custom properties are changed 


* Rossum language is taken from the organization language
* When ***registers***  and ***items templates*** are updated, synchronization is not needed, they will be updated automatically in Rossum

---

##### PROD and PREPROD stages

Information for testers

In order to use Rossum properly on PROD stage you have to do the following steps:
1. Go to PROD stage of your organization
2. Go to Rossum settings
3. Deactivate Rossum integration
4. Turn on Rossum integration again

And vise verse with PREPROD STAGE:
1. Go to PROD stage of your organization
2. Go to Rossum settings
3. Deactivate Rossum integration
4. Turn on Rossum integration again
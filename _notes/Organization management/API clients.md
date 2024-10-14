
There is an information box on the  right side
"What is API Client for?
he API Client provides you with the ability for third parties to access your data through the public wflow API. API Client ensures access authentication. In order for communication to work properly, the API client needs to be granted (authorize) access at the organization level + external link (https://developers.wflow.com/docs/wflowapidoc/9408cca5f1d4a-using-api#application-client-registration)"


Search by Name

Table:
* Client ID
* Name
* Organization
* Reset secret
* Remove

Pagination

### Create an API client

"Select an organization" selector
* by default is All organizations (API client will be available for each organization)
* this list of all organizations
	* 10 items per page
	* button "Show more" id there are more than 10 organizations
* "Client ID" input (required)
* "Full client ID"
	* read only
	* consists of wflow_customerName_valueFromClienIdInput
	* has button "Copy"
* "Name" input (required)
* "OAuth2 grant type" selectro
	* Client credentials is selected by default
	* Authorization code
	* Implicit
* "Add" button
	* becomes active when all required fields are filled


When API client is created, **"Client created"** dialog window appears with following instructions:
* "You will need "Client ID" and "Secret" to authorize client access to the API"
* "Client ID"
	* read only
	* has copy button
* "Secret"
	* read only
	* has copy button
* "Copy the Secret and save it in safe place. After closing this form, you will no longer have access to it"
* "Close" button

### Reset secret

Dialog window appears with the confirmation message:
"A new Secret will be generated for this client, which will automatically replace the currently valid Secret. The replaced Secret will never be used for authorization. **Perform this action only if it has been lost or its safety is at risk! Do you wish to perform this action ?**"

* Button "No" (red)
* Button "Yes, restore secret" (blue)
	* when "Yes is clicked" - "Secret restored" dialog window appears (it looks the same as "Client created" dialog window)
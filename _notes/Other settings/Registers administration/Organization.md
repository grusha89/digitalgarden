
#Registers 

##### People from the Organization 
#PeopleFromTheOrganization 

**Button "Add"**. When is clicked dialog window of register creation appears:
* "From the dial" selector. Offers all existing people. When option is selected all corresponding fields in the form are automatically filled
* Personal data
* "Name" input, required
* "Surname" input, required
* "E-mail". Validation on the valid format, required
* "Telephone number" input, validation on the valid format
* Address
* "Street" input
* "Zip code" input
* "City" input
* Other
* "Role in Signi" selector: [[Contracts]]
	* Approver
	* Signer
	* Inserts a stamp
* "Valid" checkbox
* "Add" button. Creates new person

**Search bar**:
* full text search by email, name and surname
* When searching in the register, prioritize showing exact matches (from the beginning). Display priority:

1. Exact match
2. Starts with
3. Full text

**Columns**:
* E-mail. Has sorting
* Name. Has sorting
* Surname. Has sorting
* Street. Has sorting
* City. Has sorting
* Zip code. Has sorting
* Phone No. Has sorting
* Role. Has sorting
* Recycle bin. Removes the person

---


##### Delivery locations
#DeliveryLocations 

https://www.figma.com/file/Hhj55N0uxbDQ02ILQe9CwO?embed_host=share&kind=file&mode=design&node-id=636:14528&t=nl74nAHNTDeijDWn-1&type=design&viewer=1

Delivery locations are displayed in creation form for [[Orders]]

**"Add" button.** When is clicked **dialog window** of register creation appears:
* "Code" input - must be unique, required field
* "Description input" - is  required
* "Address" input, not required
* "Contact person" input, not required
* "Valid" checkbox 
* "Create" button - creates register

**"Import" button**
* calls a dialog window where user can upload excel file with registers he want to import

**"Export" button**
* exports all registers including not valid ones
* the exported file can be used as the template for importing new registers or edited existing ones

**Structure of the excel file for import**
* "Id" - unique #guid of the register. If you create a new register, leave it empty. If you want to edit existing register, guid must be filled
* "ExternalId" - unique key, is required
* "Code" - unique key, must be filled
* "Description" - is not required
* "IsValid" - TRUE or FALSE, is required
* "Address" - not required
* "Contact" - not required

**"Show only valid" toggle**
* when is turned off - invalid values are displayed along with the valid registers

**Search bar
* full text search by code and description, ignores diacritics

**Columns:
* Code. Has sorting
* Description. Has sorting
* Address. Has sorting
* Valid
* Recycle bin. Removes the register
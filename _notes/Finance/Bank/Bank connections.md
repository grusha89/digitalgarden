
###### Button "Connect bank": 
* user is being redirected to the aggregator page:
* on the redirected page user select his bank and authorizes
* after authorization user see the message about success and user can get back to wflow or he will be redirected automatically after some time
* in wflow user can see dialog window with pending connection
* user can see his bank is connected

###### Bank connection
* logo of the bank
* toggle "Update payment status for documents"
		* tooltip - "The system will download the transaction history and try to automatically match transaction to received and issued invoices, After pairing, the payment status on the document changes. Frequency: once a day. Note: Three months of transaction history is downloaded at first match"
* name of the account - account number + bank code 
* each account has toggle activation toggle.
* button ***"Set as default"***. User can select the default account - the default account gonna be selected automatically during the payment. 
* "Access to the account movements" https://www.figma.com/design/J5SBwD5WRJG09r8FezNN8Q/p%C3%A1rov%C3%A1n%C3%AD-transakc%C3%AD?node-id=705-5111
	* tooltip with the description
	* button that opens the dialog window to add users. teams, everyone (Admin user doesn't have access to the transaction by default, he must be mentioned in this part)
* connection owner: avatar + user name + email
* connection status: Connected or Connection error
* Kebab menu: 
	*  "Disconnect the account" 
	* "Restore connection"
		* connection is disconnected and user is redirected automatically to the bank page (it helps user to disconnect and connect in one step)

---
* One user can connect several banks (duplicates are allowed)
* If there are several accounts from different connections owned by one user,  user can select the default account - the default account gonna be selected automatically during the payment[[Document detail. Payments]]. One user can have only one default account despite how many different bank connections he has.
* User can see other users' connections but can not manage them. Exclusion: Admin can disconnect the bank connections)
* User can see only active accounts of other users'
* User with the right "Designation for payment" has an access to the Bank settings and can create his own bank connection [[Users and permissions]] #payments

##### Bank connection token is expired
*When bank connection token is expired, the following error message is displayed:
* cs: “Ověření banky vypršelo. Obnovte spojení v  Banka > Bankovni spojeni"
* en: "Bank verification has expired. Please reconnect in Bank > Bank connection”

##### Ceska Sporitelna
* Bank API endpoint Get authorization URL ([https://axway0csasmyaggregationv1.docs.apiary.io/reference/multibanking-api/authorization-url/get-authorization-url](https://axway0csasmyaggregationv1.docs.apiary.io/reference/multibanking-api/authorization-url/get-authorization-url) )has new query parameter:
		* forcePrompt - Currently works only for CSAS, forces consent screen to appear every time
	    * Example:_ true.
	    * Boolean
    
We has to add forcePrompt=true to request what solve this use case:
- User needs to establish connection to different bank accounts from multipple wflow organizations.
	* Current behavior:
    
    1. the user connects first wflow organization to bank and grants permition to access to bank account (from many bank accounts) on consent screen
        
    2. user connect second wflow organization to bank with the same credentials but consent screen doesn’t appear so user can’t grant permition to another bank account
        
    * Expected behavior (with forcePrompt=true in query):
    
    1. the same as current behavior
        
    2. user connect second wflow organization to bank with the same credentials and consent screen appears (already granted access to bank account from step 1. is shown there) and user can grant permission to access to another bank account. User shouldn’t uncheck granted access to bank account from step 1.
        
NOTE:
It works for ČSAS only now.
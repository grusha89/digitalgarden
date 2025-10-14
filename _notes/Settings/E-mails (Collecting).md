
> [!tip] Testing info
> Max. size of files to send via email:
> * PROD stage - 50MB
> * TEST stage - 2MB
> 



Each email has a "Copy" button 
Each email has folder or document type displayed 
Each email has Duplicate and Settings buttons

##### "New e-mail" dialog window

* "Address" input. Restriction on 90 symbols including fixed domain
* "Document type" radio button:
	* has a selector  of document types, contains full text search
	* has a tooltip "When checked, documents received from the e-mail are automatically assigned the document type you selected"
* "Folder" radio button:
	* has a selector of Storage folders that opens in the additional dialog window
	* has a tooltip "When checked, documents received from e-mail are automatically saved in the folder of your choice within the repository"
* "Merge all PDF attachments into one document" checkbox
	* tooltip "If you check, only one document will be created from all PDF attachments from the received email, and all of these files will be attached to it. None of them will be set as the main file. It is therefore necessary to select it in the detail of the created document. If you do not check, one document will be created from each PDF attachment from the received email."
	* this checkbox is not available when "Folder" radio button is selected
* "Ignore image attachments" checkbox
	* tooltip "If checked, image attachments (png, jpg, bmp, ico, tiff, ...) from the received email will not be attached to the document "
* "Receive emails only from allowed addresses (recommended)"
	* tooltip "If you check, you can enter a semicolon-separated list of allowed sender email addresses. Only messages from the senders listed in the list will be received for this email"
	* it is possible to whitelist the whole domain, for example @wflow.com



> [!NOTE] Z emailu zakládat duplicitní přílohy podle názvu pouze jednou
> Soubory zakládat pouze jednou => první deduplikace podle názvu a velikosti a pak až vyhodnocení podmínky na max 20 příloh.
> 
Přepsat logiku na odstranění obrázků (pokud je tak mail nastavený) tak, aby se prováděla před vyhodnocením podmínky na max 20 příloh


> [!NOTE] Emails on different Test environments 
> On all testing environments (TEST, RC, PREPROD) collecting emails don't work. In order to make them work you suppose to make the following steps:
>  1. Create email
>  2. Select settings you need
>  3. Contact with Marek Bojanovksy and send him the emails you created

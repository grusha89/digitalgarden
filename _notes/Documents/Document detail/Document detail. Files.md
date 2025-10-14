

#### Files tab Lines visibility

Can be hidden/unhidden with the help of:
* Files icon on the left panel
* "close" button

"Files" icon displays the count of the lines
The height of the Files section is adjustable by dragging the section header

##### Files stretching

* Files section has stretching button (two arrows)
* Stretching of the files applies automatically on "Lines" section
* User can stretch the Files section along the width of the document
	* Save and Cancel buttons will be above the lines section on the left

### File preview


> [!info] Supported image formats
> JPEG, PNG, SVG

* When the file can not be displayed File tools are not available (not displayed). In this case instead of the image message is displayed "No content! We cannot view this file format"
* When there is no any file the following message is displayed "No content!"
* Such files as .txt and .html must be displayed normally 

##### Upper panel 

**Pages count (1/3)
* Shows the page order out of the all pages of the current document (On the left)

**OCR (Not sure if customers use it at all)
* Allows you to extract data manually 
* is turned off by default (grey color)
* clicking on OCR turns it on/off
* has a blue color when it's on and cursor changes
* in order to extract the text, the text must be defined with the cursor



---

##### File tools

1. **Download** (tooltip on hover)
2. **Print
	* tooltip on hover
	* prints the file
3. Fit to page/ fit to width button (tooltip on hover)
4. Rotate
	* tooltip on hover
	* rotates the image
5. Scale up button (tooltip on hover)
6. Scale down button (tooltip on hover)
7. **OCR (Not sure if customers use it at all)
	* Allows you to extract data manually 
	* is turned off by default (grey color)
	* clicking on OCR turns it on/off
	* has a blue color when it's on and cursor changes
	* in order to extract the text, the text must be defined with the cursor
8. T - enable text selection (Some PDFs don't have such option)
	* tooltip on hover
	* can be turned on/off (blue/grey colors)
	* allows to copy the text out of the file

---

##### The list of files

**Files slider
* buttons "Next file", "Previous file"
* file count: the order of the displayed document out of the general quantity
* the name of the currently displayed document
* fold/unfold button: hides/unhides the list of the files
	* folding/unfolding state is memorized for user throughout the organization and device

**The files
* the currently displayed file is highlighted and indicated with the blue dot
* the main file is marked with the blue star
* each file is displayed as:
	* file name + date when the file was added



> [!NOTE] The rule of the files order

	* the first is always main file
	* then PDF files by alphabetical order
	* then other formats by alphabetical order


---

##### Action buttons (Single)


Each file has the same set of action buttons

1. Time stamp
	* dialog window of the stamp info appears
			* File name
			* Signing date: date and time
			* Valid to: date and time
			* Signed
			* Issued by
			* when file is stamped - stamp button becomes blue
2. Sign
		* create an electronic signature (not Signi)
		* redirects to the third party page
3. Download
		* downloads the file
4. Delete
		* deletes the file
		* ==is not available when the document is locked==

---

##### Action buttons (bulk)

There is a checkbox that selects all the files and the bulk actions appears:
1. Download
	* each file will be downloaded separately without archivation
2. Send via email
	* sending email dialog window appears
3. Delete
	* confirmation message appears

---

##### "Add files" button
==is not available when the document is locked==


> [!important] For Orders and Manual Outgoing Invoices
>  It is allowed to upload the file when the document is confirmed
>  

> [!important] When document doesn't have any file
> Uploaded file automatically becomes the main file
> 

Opens the dialog window "Upload files"
* "Browse device" button
* "Browse storage" button
* Drag and drop area
* "Upload" button

* It is possible to upload file when Order and manual Outgoing invoice are confirmed
* When the document doesn't have main file - uploaded PDF is being marked automatically as the main file
---

##### "Send files" button

Dialog window "Send e-mail" appears:
* "Send from email" - selector:
	* it is possible to select organization's email or current user's email
	* selected email has blue tick
	* user's email is offered by default
	* the latest choice is memorized for the current organization
	* when organization's email is not filled -> user's email is preselected automatically
* "To*" - required text input
	* placeholder "Fill in 1 or more emails"
	* informational tooltip "Separate email addresses with a comma"
	* validation appears when the input is left empty
	* validation appears when the email address has incorrect format
	* each email address is displayed as the chip
* "Subject*" - required text input
	* validation appears when the input is left empty
* The list of files:
	* main file indicator + file name + date of creation + remove button
* "Message" text input
* "Send" button
	* is active when all required fields are filled



---
##### Selected files preview

Each file is displayed as the icon of file with the name of file type + name of the file + date of the last update

export const SUPPORTED_FILE_TYPE_PREVIEWS = [
  'CSS',
  'CSV',
  'DMG',
  'DOC',
  'DOCX',
  'EPS',
  'EXE',
  'GIF',
  'HTML',
  'IMG',
  'ISDOC',
  'ISDOCX',
  'JAVA',
  'JPEG',
  'JPG',
  'JS',
  'JSON',
  'PDF',
  'PNG',
  'PPT',
  'PPTX',
  'RAR',
  'RSS',
  'SQL',
  'SVG',
  'TIFF',
  'TXT',
  'WEBP',
  'XLS',
  'XLSX',
  'XML',
  'ZIP',
];


##### Empty state

When there is no any file, the following things are displayed
* icon of the file
* text "the document doesn't contain files'"





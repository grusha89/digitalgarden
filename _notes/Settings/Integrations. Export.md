
You can export your data in various formats (CSV, XLSX, ISDOC, ...). Here you can create and manage definitions of individual exports - their content and form.

##### Default exports
 Can not be edited, copied or removed

*  Money  S3
* Money S4/S5
* Kros - OMEGA SK
* PREMIER
* Excel
* ISDOC
* XML
* MRP
* DATEV
* Byznys Solitea
* Jezek SW DUEL a STEREO (this is the exclusion for one of the clients: can be edited and copied, better not to touch)

The behavior of the  exports can be found here [[Grid. Exports]]


##### Custom exports

Custom exports can be edited, copied and removed
It is possible to change the order of the custom exports by drag and drop

**"Export settings" dialog window**
* Name input:
	* There is no duplicate validation
* "Share" checkbox:
	* tooltip "If checked, this export will be available to all users in your organization"
* "Definition* section
	* Search and list of columns
		* columns are divided by categories
		* each columns has checkbox
		* when checkbox is clicked to be true column is added to active columns to the end of the list and automatic scroll launches to the freshly added column
	* Active columns
		* using drag and drop we can change the order of the columns
		* selected columns has column Id and the column name
		* Each selected column can be changed clicking on the "pencil" 
* "Options" section
	* "Format" selector: Text file/CSV and Excel table
	* "Header" checkbox with tooltip "If checked, a header with column names will be inserted into the exported file. Otherwise, the data will be exported without a header"
	* "Encoding" selector: UTF-8, Windows-1250, Custom
	* "Delimiter" selector: Semicolon ";", Comma ",", Tab
	* "Quotation marls" selector: Do not use quotation marks, Double quotes, Single quotes
	* "Date format" selector: dd.MM.yyyy, yyyyMMdd, yyyy-MM-dd

It is possible to create or edit custom export via [[Grid. Exports]]
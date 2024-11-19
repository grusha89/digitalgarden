Documents are being kept in recycle bin for 30 days
After 30 days they are automatically being removed

Description of the columns of the recycle bin can be found in [[Customization. Appearance]]

**The frequent user's case**

1. User removes all documents from the  document type A
2. Then user wants to remove the empty document type but he won't be able to do it. He will get the message: "The document type cannot be deleted. Documents are found in this type. If you want to remove this type, move the documents to another type". Because document in the bin are still considered as existing for this document type A
3. In this case, user has to restore all those documents, move them to another document type B, delete them there.
4. Then user will be able to remove the document type A

Recycle bin and event log:
* Document stores the event of removal and restoration

Recycle bin and flow statuses:
* When the document with flow status "Sending to ERP" is removed and restored -> flows status will be changed into "Send to ERP error" and there will be message in the even log "The document was moved to the recycle bin. Repeat the export to ERP."
* When the document with flow status "Sending to Extraction" is removed and restored -> flows status will be changed into "Send to Extraction error" and there will be message in the even log "The document was moved to the recycle bin. Repeat the send to Extraction." (it's hard to simulate, as you need to catch when document has orange status, because it changes into "Successful sent to Extraction" very fast)
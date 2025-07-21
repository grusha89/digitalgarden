This feature can turned on/off in [[Organization profile]]
This feature works only for incoming invoices

Feature allows Rossum to recognize that incoming invoice doesn't belong to the current organization on the base Customer ID and Rossum will sort this document to the correct organization

The following conditions must be met to use this function:
Organizations, between which sorting will be carried out:
	1. must belong to the same customer
	2. must have the toggle "Automatically sort documents into organizations" to be turned on in Organization profile

How automatic sorting works:
1. Incoming invoice gets to organization and is sent to Extraction
2. During the extraction Rossum recognizes that document doesn't belong to the current organization and sort this document to the correct one
3. Document disappears from the initial organization
4. Extracted document appears in the correct organization and in event log user can see that it was sorted from the previous org.
5. Document is extracted again in the target organization
6. User can work with sorted document (send it to review for example)



> [!NOTE] Exception
> If there are more than one target organizations with the same Customer ID - sorting won't be processed

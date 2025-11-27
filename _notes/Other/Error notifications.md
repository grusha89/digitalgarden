
### Notifications UX

[Embedded content](https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fdesign%2FVYySf0qpOqkMGcCOlSqNQc%2F2025-Navigation%3Fnode-id%3D1831-14040%26t%3DOCf9mRw9kbMn1KjG-4 "https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fdesign%2FVYySf0qpOqkMGcCOlSqNQc%2F2025-Navigation%3Fnode-id%3D1831-14040%26t%3DOCf9mRw9kbMn1KjG-4")


1. Max.  quantity of messages is displayed at a time is 4. If a new error message appears, it covers the previous one.
2. If the user hovers on an error message (or tap on mobile or tablet), all messages are displayed.
3. Each error message has negative progress bar at the bottom. Once the progress bar completes, the message disappears.
4. Each error message has copy button to copy the contain of the error including time stamp
5. If the user hovers the mouse over any error message, none of the messages should disappear (reset the time and stop it until the user move the mouse out)


Success message - 3 sec, then fade out
Other messages - 7 sec with negative loading bar, then fadeout

### General

Tips how to simulate the error notifications:

Using different tabs will help as they're not synchronized in automatic update:

For example, let's test "document-is-locked":
1. Open the same document in two different tabs
2. In one tab lock the document
3. In the second tab use the action "Assign approval path"
4. Result: error notification appears that Document is locked


| Key                         | English                                                                  | Czech                                                                | How to test                                                                                                                               |
| --------------------------- | ------------------------------------------------------------------------ | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| document-not-exist<br>      | Document does not exist or user has no access to document.               | Dokument neexistuje nebo uživatel nemá přístup k dokumentu .         | 1. When user opens document via the link to which he doesn't have access/ 2. When user makes some actions on the document that is deleted |
| document-is-locked          | Document is locked.                                                      | Dokument je uzamčený.                                                | When user makes actions that are impossible with locked documents                                                                         |
| task-no exist               | Document task does not exist.                                            | Úloha k dokumentu neexistuje.                                        | When user makes actions that are impossible with the current document                                                                     |
| delete-document-in-approval | Cannot delete a document with the approval process in progress.          | Dokument s probíhajícím schvalovacím procesem nelze smazat.          | When not Admin user tries to remove the document with unfinished approval                                                                 |
| document-has-approval-path  | This document already has associated approval path.                      | Tento dokument již má nastavenou schvalovací cestu.                  | When user tried to assign approval path when the document already has it                                                                  |
| nothing-to-approve          | There is nothing to Approve.                                             | Není co Schvalovat.                                                  | When the document cannot be approved                                                                                                      |
| nothing-to-reject           | There is nothing to Reject.                                              | Není co Zamítnout.                                                   | When the document cannot be rejected                                                                                                      |
| nothing-to-return           | There is nothing to Return.                                              | Není co Vrátit.                                                      | When the document cannot be Returnd                                                                                                       |
| nothing-to-retunr-back      | There is nothing to Return back.                                         | Není co Vrátit zpět na předchozí úroveň.                             | When the document cannot be returned to the previous level                                                                                |
| nothing-to-cancel           | There is nothing to do Approval reset.                                   | Není u čeho Vymazat stav.                                            | When the approval cannot be reset                                                                                                         |
| request-not-exists          | No marks for payment exist for this document.                            | Pro tento dokument neexistují žádná Označení k úhradě.               | When the document is not marked for payment and user tries to pay it (not via bank api)                                                   |
| document-already-exported   | This operation cannot be done on an exported document.                   | Tuto operaci nelze provést na exportovaném dokumentu.                | can not be tested                                                                                                                         |
| kind-change-not-allowed     | Changing the kind of document is not allowed.                            | Změna druhu dokumentu není povolena.                                 | can not be tested                                                                                                                         |
| approval-already-exists     | Such an approval path already exists, so it cannot be created.           | Taková schvalovací cesta již existuje, proto ji nelze vytvořit.      | can not be tested                                                                                                                         |
| file-already-exists         | File with this name already exists in the destination folder.            | Soubor s tímto názvem již v cílové složce existuje.                  | When user moves the files to the folder when the file with the same name exists (Storage)                                                 |
| file-is-locked              | File is locked.                                                          | Soubor je uzamčený.                                                  | When user makes actions that are not allowed with the locked files (Storage)                                                              |
| file-in-approval            | This operation cannot be done while the approval process is in progress. | Tuto operaci nelze v probíhajícím schvalovacím procesu provést.      | can not be tested                                                                                                                         |
| update-file-in-approval     | Cannot update file while the approval process is in progress.            | Během probíhajícího schvalovacího procesu nelze soubor aktualizovat. | can not be tested                                                                                                                         |
| folder-already-exists       | Folder already exists.                                                   | Složka již existuje.                                                 | When the folder with the duplicate name is being created                                                                                  |

### Feature flag notifications

When user tries to do the action that is not allowed according to the feature flag, the error notification appears
" This functionality is not allowed for your plan"
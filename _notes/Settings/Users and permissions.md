

> [!Design] Design prototype
> https://www.figma.com/file/6TxkqAGvEgx3qfkAzCUy34/Users?type=design&node-id=443%3A24816&mode=design&t=zJe2476RAhKrPG0H-1
> 

### USERS

[Jira task](https://6kswcz.atlassian.net/browse/WCOM-6964)

* In the User settings page administrator can add new users (even those who are not yet registered in the app), edit them, assign them to the roles and teams

#### Layout description of “Users” section

**First level:**

- left corner - button “+ Create user”
- right corner - search bar “icon: magnifying glass & placeholder: Search”

**Second level:** table: all columns have adjustable width (is not memorized)

- Column “Name”: consists of an avatar, the name of the user (bold), e-mail and has sorting
- Column “Role”: displays
    - if there is one role → role name is displayed
    - if there is more than one role → one role is displayed and +n icon (there is native browser hover)
    - if there is no role → button “Add role” is displayed
- Column “Team: displays
    - if there is one team → team name is displayed
    - if there is more than one team → one team is displayed and +n icon (there is native browser hover)
    - if there is no team → button “Add team” is displayed
- Column without a name: clickable kebab elements for each row. Unfolded state:
    - if user is registered in app → icon + “Send an invitation”, icon + “Edit user”, under the divider: icon + “Duplicate”, icon + “Delete”
    - if user is not registered in app → icon + “Edit user”, under the divider: icon + “Duplicate”, icon + “Delete”

**Footer:**

- right corner: pagination selector
    - default items per page are 10 (only for the context of new grids)

##### **Functionality**

**Create/edit user:**

- Clicked button “Add user” opens a dialog window (DW) with the header “Add user”
- DW: there are two tabs “Basic information” and “Access to the documents”

---

_“Basic information” tab_

- DW: E-mail input:
    - there is validation on duplicate values
    - there is validation on the correct e-mail format
    - possible to input several e-mails using commas or enter
    - input ignores CapsLock
- DW: role input:
    - has an icon of a magnifying glass
    - it’s a dropdown list with options (only names are shown), if there are more than options button “Next” appears
    - searches among existing roles by name only
    - ignoring diacritics
    - the role is found by matching parts of the words (e.g. there is a description “Role can approve” - it will be found even if the user inputs “le ca”
    - inputting/removing letters updates the result with corresponding matches
- DW: team input:
    - has an icon of a magnifying glass
    - it’s a dropdown list with options (only names are shown), if there are more than options button “Next” appears
    - searches among existing teams by name only
    - ignoring diacritics
    - the team is found by matching parts of the words (e.g. there is a description “Role can approve” - it will be found even if the user inputs “le ca”
    - inputting/removing letters updates the result with corresponding matches

---

_“Access to the documents” tab_

- Document types are divided into kinds. Each kind represents a section that can be folded/unfolded
    
- Each kind and type has two checkboxes: all documents and private documents:
    
    - two checkboxes on the same row can not be true at the same time
    - when one checkbox is selected, the second one becomes unselected automatically
    
    ---
    
- DW: button “Send an invitation”: hitting the button creates/updates the user
    
    - if the user is created and is already registered in the app → avatar, name and e-mail are displayed
    - **if the user is not registered?**
    - there is always an option “To send invitation”

**Add actions on the grid:**

- “Add role”:
    - there is a button “Add role” if the user doesn’t have any assigned role
    - a dialog window appears with a search bar
    - search is by role name
    - added roles are displayed as the list
    - role can be removed from the list by clicking on the cross
    - The “Cancel” button will cancel the dialog window
- “Add to the team”:
    - there is a button “Add to the team” if the user doesn’t have any assigned team
    - a dialog window appears with a search bar
    - added teams are displayed as the list
    - search is by team name
    - team can be removed from the list by clicking on the cross
    - The “Cancel” button will cancel the dialog window
- Remove:
    - a dialog window with a confirmation message appears
    - The “Cancel” button will cancel the delete action
    - The “Remove” button will remove the user

**Search bar**

- Search works only by email

### ROLES

[Jira task](https://6kswcz.atlassian.net/browse/WCOM-6962)

##### Description

Nová entita role, která definuje uživatelská oprávnění.

Role je složená z:

1. Název role
    
2. Popis role
    
3. Definice oprávnění
    
4. Vazba na uživatele
    

Uživatel s vazbou na roli získá také oprávnění, které je na roli definované.

Uživatel může mít i více přiřazených rolí, oprávnění se “sčítají”.

Při založení nové organizace se vytvoří i výchozí role. Výchozí role se chovají stejně, jako uživatelsky vytvořené role. **Výjimka: Role Administrátor -** tato role nelze odstranit (tedy se u řádku této role neukazuje ani možnost odstranění) a v roli musí být vždy minimálně jeden přiřazený uživatel. Pokud tedy spravuji sadu přiřazených uživatelů, nemohu smazat posledního (zmizí tlačítko pro odebrání).

[Seznam předdefinovaných rolí a jejich oprávnění.](https://docs.google.com/spreadsheets/d/1m7IZw1VNLUlRk0shZPVLSmRLyF9EkM5XrJj0R8CZ8vI/edit#gid=0)

Definice oprávnění:

Oprávnění je členěné podle skupin. U role mohu zvolit buď konkrétní oprávněn, nebo celou sekci (tím se zvolí všechna oprávnění pod touto skupinou).

[Seznam oprávnění a členění dle skupin](https://docs.google.com/spreadsheets/d/1m7IZw1VNLUlRk0shZPVLSmRLyF9EkM5XrJj0R8CZ8vI/edit#gid=0)

Nový odkaz → [https://wflowczech-my.sharepoint.com/:x:/g/personal/filip_dolansky_wflow_com/ERT8E5cMMepDkM1YO8kfao4BbD0LJltWLIjlUsGNO8wWDQ?rtime=fupSL4wh3Eg](https://wflowczech-my.sharepoint.com/:x:/g/personal/filip_dolansky_wflow_com/ERT8E5cMMepDkM1YO8kfao4BbD0LJltWLIjlUsGNO8wWDQ?rtime=fupSL4wh3Eg)

Správa rolí:

Správa rolí je pod Nastavení organizace > Uživatelské oprávnění > list: Role

Grid je složený z:

1. Název a popis
    
2. Uživatelé - přiřazení uživatelé u role, pokud nemá role žádného uživatele přiřazeného, zobrazí se call-to-action pro přiřazení
    
3. Další nástroje (tři tečky) - pod tím nabídka:
    

a. Přiřadit uživatele

b. Duplikovat

c. Odstranit

##### _Layout description of “Role” entity_

**First level:**

- left corner - button “+ Create role”
- right corner - search bar “icon: magnifying glass & placeholder: Search”

**Second level:** table: all columns have adjustable width (is not memorized)

- Column “Name”: consists of an icon, the name of the role (bold), the role description, and has sorting. There is a tooltip for role description
- Column “Users”: displays
    - if at least one user is assigned → number of users and user avatars
    - if any user is not assigned → button “Assign user”
    - if more than 5 users are assigned → number of users, avatars of five users, and “+n” icon
- Column without a name: clickable kebab elements for each row. Unfolded state:
    - if Admin role → icon + “Assign user”, icon + “Edit role”, under the divider: icon + “Duplicate”
    - if any other role - > icon + “Assign user”, icon + “Edit role”, under the divider: icon + “Duplicate”, icon + “Delete”

**Footer:**

- right corner: pagination selector
    - default items per page are 10 (only for the context of new grids)

---

##### _**Functionality**_

**Create/edit a role:**

- Clicked button “Create role” opens a dialog window (DW) with the header “Create role”
- DW: input “Name of the role” has placeholder “Name your role”. The name must be unique**.** Otherwise, validation appears**.** Can be copy pasted
- DW: input “Role description” has placeholder “Describe what is the role for…”. The field doesn’t stretch. The field has a restriction of 300 symbols. Can be copy pasted
- DW: Rights: each right is a checkbox, each right consists of a Name and description, and rights are divided into categories that can be folded/unfolded.
    - Approval and review:
        - documents approval: The user can use all approval actions, can see folders “My approvals”, and can add another approver to the approval path only in his path and during his queue
        - document review: The user can review documents and can see the folder “To review”
        - Approval paths assignment: can assign/remove approval paths, can add another approver in any path, can see the folder “All approvals”
    - Work with documents
        - Document create: user can upload documents, copy, and upload documents via the mobile app
        - Document delete: The user can remove documents and restore them from the bin
        - Access change: The user can add, or remove access to the document.
        - if user has access to all document types, it’s impossible to remove this user from document access
        - Document move and merge: The user can move the document to another type/kind and can merge documents
        - Lock: The user can lock and unlock documents
        - Process document files: The user can add/remove files and change the main file
        - send to extraction
        - send to review
        - send to ERP
        - link documents: can link/unlink documents
    - Document data
        - Headers: The user can edit the headers of the document
        - Lines: The user can edit the lines of the document (what if the user can not edit, but can create orders???)
        - Accounting: The user can edit accounting fields (document detail + bulk actions)
        - Custom properties: The user can edit custom properties
        - Tags: The user can create, add, and remove tags (document detail + bulk actions)
    - Payments #payments 
        - processing payments: can pay, mark for payment, bulk payments, set bank connections, can remove processed payment
        - mark for payment
    - Other
        - exporting data: can export data, bulk download, can edit export settings, can export registers
        - sending contracts to Signi: can send to Signi, can edit counterparties
        - signature and stamp: can sign documents and use a timestamp
    - Registers:
        - Partners: The user has access to partners, and can edit, create, and remove, but can not export/import
        - Catalog (catalog of items, catalog category): The user has access to the catalog, and can edit, create, and remove, but can not export/import
        - Items template: The user has access to the items template, and can edit, create, and remove, but can not export/import
        - Accounting, cost centers: The user has access to the rest of the registers, and can edit, create, and remove, but can not export/import
    - Settings:
        - Organization profile: access to the organization profile
        - Storage: access to the storage
- The button “Save”: is not active when changes are not made
- confirmation message about unsaved changes appears if the user closes the window without hitting the button “Save”

**Search bar:**

- role is found by: the name of the role and description
- role is found by ignoring diacritics
- the role is found by matching parts of the words (e.g. there is a description “Role can approve” - it will be found even if the user inputs “le ca”
- inputting/removing letters updates the result with corresponding matches
- roles that are on the following pages can be found

**Button “Add user” on the table:**

- the same dialog window as in kebab actions

**Kebab actions:**

- Add user:
    - a dialog window appears with a search bar
    - users that already exist in the role gonna be displayed on the card (qty of users + 5max icons + “+n”
    - just added users are displayed as the list of names with the cross button (delete user from the list)
    - only users who are not in the role are displayed in the selector
    - search is by user name
    - user can be removed from the list by clicking on the cross
    - The “Cancel” button will cancel the dialog window
- Edit role:
    - a dialog window appears
    - button “Save” is not active until changes are made
    - confirmation message about unsaved changes appears if the user closes the window without hitting the button “Save”
- Duplicate:
    - dialog window appears with the original role name + (Copy)
    - there is a duplicate validation
- Remove:
    - a dialog window with a confirmation message appears
    - The “Cancel” button will cancel the delete action
    - The “Remove” button will remove the role

**Pagination:**

- amount of shown elements can be selected in the page selector
- user can go through the pages using navigation arrows

_**Logic**_

The same user can be in different roles. It means that all rights from different roles gonna merge for this user


| Schvalování ~~a kontrola~~    |                                                                                                                                                                                  | klíč                                 |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| Schválení dokumentů           | Vyjádření k dokumentům ke schválení (schválení, vrácení, zamítnutí, vrácení o krok zpět), možnost přidat další schvalovatele do již přiřazené schvalovací cesty pokud je na řadě | CanApprove (0)                       |
| Přiřazení schvalovacích cest  | Přiřazení schvalovací cesty, odebrání schvalovací cesty, možnost přidat další schvalovatele do již přiřazené schvalovací cesty                                                   | CanManageApprovalPath (2)            |
| Práce s dokumenty             |                                                                                                                                                                                  |                                      |
| Vytvoření dokumentu           | Nahrání dokumentu, kopírování dokumentů, sloučení dokumentů, zaslání dokumentu přes mobilní aplikaci                                                                             | CanCreateDocument (3)                |
| Odstranění dokumentu          | Odstranění dokumentu, obnovení z koše                                                                                                                                            | CanDeleteDocument (4)                |
| Změna přístupu                | Přidání a odebrání přístupů k dokumentu                                                                                                                                          | CanManageAccess (5)                  |
| Přesunutí                     | Změna typu, případně druhu dokumentu (při změně druhu dokumentu v některých případech nelze zachovat data dokumentu)                                                             | CanChangeDocumentType (6)            |
| Zámek                         | Odemknutí a zamknutí dokumentu                                                                                                                                                   | CanLock (7)                          |
| Správa příloh dokumentu       | Přidání a odstranění příloh u dokumentu, změna hlavního souboru                                                                                                                  | CanManageAttachments (8)             |
| Odeslání na vytěžení          |                                                                                                                                                                                  | CanSendToExtraction (9)              |
| Odeslání do ERP               | Odeslání do ERP, označení jako odesláno do ERP                                                                                                                                   | CanSendToErp (11)                    |
| Propojení dokumentů           | Vytvoření propojení dokumentů, zrušení propojení                                                                                                                                 | CanManageDocumentLinks (12)          |
| Data dokumentu                |                                                                                                                                                                                  |                                      |
| Kontrola dokumentů            | Potvrzení dokumentů čekajících na kontrolu.                                                                                                                                      | CanReview (1)                        |
| Data dokumentu                | Změna dat na dokumentu + Copy + accountings + lines                                                                                                                              | CanManageDocument (13)               |
| Účtování & Položky dokumentu  | Změna hodnot účtování (středisko, zakázka, předkontace,..) na hlavičce i položkách, změna hodnot na položekách dokumentu                                                         | CanManageDocumentAccounting (14)     |
| Volitená pole                 | Zména hodnot volitelných polí                                                                                                                                                    | CanManageCustomProperty (15)         |
| Štítky                        | Přidání a odebrání štítků u dokumentů                                                                                                                                            | CanManageTags (16)                   |
| Platby                        |                                                                                                                                                                                  |                                      |
| Provedení platby              | Provedení platby, označení úhrady, hromadné platby, Napojení banky, správa napojené banky, možnost smazat provedenou platbu                                                      | CanManagePayments (17)               |
| Označení k úhradě             | Označení dokumentů k úhradě                                                                                                                                                      | CanMarkForPayment (18)               |
| Ostatní                       |                                                                                                                                                                                  |                                      |
| Export dat                    | Export dat, hromadné stažení dat, správa šablon exportu, ~~export číselníků~~                                                                                                    | CanExport (19)                       |
| Odeslání na podpis přes Signi | Odeslání na podpis přes službu Signi, správa kontaktů protistran. Nemá přistup k číselnikam a Signi integrace                                                                    | CanManageExternalSignature (20)      |
| Podpisování a razítkování     | Podepsání souboru elektronických podpisem a přiřazení časového razítka.                                                                                                          | CanStamp (21)                        |
| Správa číselníků              |                                                                                                                                                                                  |                                      |
| Partneři                      | Přístup do číselníku partnerů, Vytvoření, editace a odstranění karet partnerů + export/import                                                                                    | CanManagePartners (22)               |
| Katalog                       | Správa a editace katalogu a jeho kategorií + export/import                                                                                                                       | CanManageBusinessItems (23)          |
| Šablony položek               | Vytvoření, editace a odstranění šablon položek + export/import                                                                                                                   | CanManageDocumentLinesTemplates (24) |
| Účtování a nákladové objekty  | Přístup do ostatbích číselníiků, vytvoření, editace a odstranění položek + export/import                                                                                         | CanManageRegisters (25)              |
| Nastavení                     |                                                                                                                                                                                  |                                      |
| Nastavení organizace          | Přístup do hlavní nabídky nastavení organizace, krome Nastaveni Exportu a Banky                                                                                                  | CanManageSettings (26)               |
| Správa úložiště               | Nastavení struktury úložiště a přístupů ke složkám, oprávnění zviditelní uživateli všechny složky a soubory úložiśtě                                                             | CanManageFileStorage (27)            |

### TEAMS

[Jira task](https://6kswcz.atlassian.net/browse/WCOM-6966)

##### _Layout description of “Teams” entity_

**First level:**

- left corner - button “+ Create team”
- right corner - search bar “icon: magnifying glass & placeholder: Search”

**Second level:** table: all columns have adjustable width (is not memorized)

- Column “Name”: consists of an icon, the name of the team (bold), description, has sorting and there is a tooltip for description
- Column “Users”: displays
    - if at least one user is assigned → number of users and user avatars
    - if any user is not assigned → button “Add user”
    - if more than 5 users are assigned → number of users, avatars of five users, and “+n” icon
- Column without a name: clickable kebab elements for each row. Unfolded state:
    - icon + “Add users”, icon + “edit team”, under the divider: icon + “Duplicate”, icon + “Delete”

**Footer:**

- right corner: pagination selector
    - default items per page are 10 (only for the context of new grids)

##### _**Functionality**_

**Create/edit team**

- clicking on the button “Create team” opens a dialog window (DW) with the name Create/Edit team
    
- DW: The header is “Details of the team” + description of the function
    
- DW: Input “Team name” has placeholder “Name your team”. The name must be unique. Otherwise, validation appears. Can be copy pasted
    
- DW: input “Team description” has placeholder “Describe what is the team for…”. The field doesn’t stretch. Max 300 symbols. Can be copy pasted
    
- DW: users input:
    
    - has an icon of a magnifying glass
    - drop down list. The next button is available (if there are more than 10 elements). Users that are on the following pages can be found
    - User are displayed with emails
    - ignoring diacritics
    - the team is found by matching parts of the words (e.g. there is a description “Role can approve” - it will be found even if the user inputs “le ca”
    - inputting/removing letters updates the result with corresponding matches
    - added user can be removed by clicking the cross on the user’s chip
    
    **Search bar:**
    
    - the team is found by team name and description
    - role is found by ignoring diacritics
    - the team is found by matching parts of the words (e.g. there is a description “Role can approve” - it will be found even if the user inputs “le ca”
    - inputting/removing letters updates the result with corresponding matches
    - roles that are on the following pages can be found
    
    **Button “Add user” on the table:**
    
    - the same dialog window as in kebab actions
    
    **Kebab actions:**
    
    - Add user:
        - a dialog window appears with a search bar
        - users that already exist in the role gonna be displayed on the card (qty of users + 5max icons + “+n”
        - search is by user name
        - user can be removed from the list by clicking on the cross
        - The “Cancel” button will cancel the dialog window
    - Edit teams:
        - a dialog window appears
        - button “Save” is not active until changes are made
        - confirmation message about unsaved changes appears if the user closes the window without hitting the button “Save”
    - Duplicate:
        - dialog window appears with the original role name + (Copy)
        - there is a duplicate validation
    - Remove:
        - a dialog window with a confirmation message appears
        - The “Cancel” button will cancel the delete action
        - The “Remove” button will remove the team
    
    **Pagination:**
    
    - amount of shown elements can be selected in the page selector
    - user can go through the pages using navigation arrows
    -

### Access rights

[Jira task](https://6kswcz.atlassian.net/browse/WCOM-6963)

1. User settings: access to all documents in the type/kind:
    - user A can see all documents within the type/kind
    - each document of the type/kind has user A in its access settings
    - document type has user A mentioned in its access settings in the section “Access to all documents”
    - if the document type had user A mentioned in the section “Access to private documents”, it will change to “Access to all documents”
2. User settings access: access to private documents
    - user A can see documents that are created by him
    - user A can see documents that have an approval path where user A is the approver or mentioned in the access setting
    - user A can see documents that have an approval path where user A is part of the team that approves or is mentioned in the access setting
    - user A can see documents where he was added to the access settings on the level of the single/bulk actions
    - document type has user A mentioned in its access settings in the section “Access to private documents”
    - ~~if the document type had user A mentioned in the section “Access to all documents”, it will change to “Access to private documents”~~

---

1. Document type settings: “Access to all documents” contains user A
    - user A can see all documents in the current document type and it’s mentioned in his user settings
    - if user A had access to private documents in the current type, his access settings will be changed to “Access to all documents”
    - each document of the type/kind has user A in its access settings
2. Document type settings: “Access to private documents” contains user A
    - user A can see documents that are created by him
    - user A can see documents that have an approval path where user A is the approver or mentioned in the access setting
    - user A can see documents that have an approval path where user A is part of the team that approves or is mentioned in the access setting
    - user A can see documents where he was added to the access settings on the level of the single/bulk actions
    - user A has “Access to private documents” in its settings
    - ~~if user A has “Access to all documents” in user settings, it will change to “Access to private documents”~~

---

1. document access settings:
    - to add a new team to the access: only teams that don’t have yet access to the current document are offered
    - to add new users: only users that have “Access to private documents” for the current document type are offered
    - users and teams gonna be displayed separately on the dialog window of document access settings
    - if a user doesn’t have any access to the document type, but he is a part of the approval path that gonna be assigned to the document → user is not able to see the document, and will not receive email notification
    -


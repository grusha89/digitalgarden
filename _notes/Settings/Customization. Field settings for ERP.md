
In this section we can set accounting fields according to ERP we use.


> [!NOTE] Codependency
> Selected ERP settings in this section will be applied automatically to the all document kinds and to the settings in the section Integrations -> ERP and vise versa [[Integrations. ERP]]

With some ERPs several fields are not available (we can not include them) but we always can exclude those that are available

We can set ERP fields for all document kinds BUT Contracts. Contract don't have accounting fields

Switching between document kinds sections without saving changes causes warning 

##### "Accounting system" selector
* DUEL
* Abra Flexi
* HELIOS
* iDoklad
* 6K
* Money S3
* Money S4/S5
* Pohoda
* PREMIER
* Dynamics 365 Business Central
* Vario
* Other
* None

##### Accounting fields according to ERP

* "-" field is not available for the ERP
* For Other - all fields are available
* For None - nothing is available

|                                 | DUEL | Flexi | HELIOS | iDoklad | 6K  | Money S3,S4,S5 | Pohoda | PREMIER | 365 | Vario |
| ------------------------------- | ---- | ----- | ------ | ------- | --- | -------------- | ------ | ------- | --- | ----- |
| Accounting rule                 |      |       |        | -       |     |                |        |         | -   |       |
| Activity                        |      |       |        | -       |     |                |        | -       |     |       |
| Business item                   |      |       |        |         |     |                |        |         |     | -     |
| Cash document type              | -    | -     | -      | -       | -   | -              | -      | -       | -   | -     |
| Cash register                   |      |       | -      |         | -   |                |        | -       |     | -     |
| Commitment type                 | -    | -     | -      | -       | -   | -              | -      | -       | -   | -     |
| Contra Account (MD/D)           |      |       |        | -       |     |                |        |         | -   | -     |
| Contract                        |      |       |        | -       |     |                |        |         |     |       |
| Cost Center                     |      |       |        | -       |     |                |        |         |     |       |
| Employee                        | -    | -     |        | -       | -   | -              | -      | -       | -   | -     |
| Payment method                  |      |       |        |         |     |                |        |         |     |       |
| VAT apply reduction coefficient | -    | -     |        |         | -   | -              | -      | -       | -   | -     |
| VAT control statement line      |      |       | -      | -       | -   |                | -      |         | -   | -     |
| VAT fixed assets (VAT line 47)  | -    | -     |        |         | -   | -              | -      | -       | -   | -     |
| VAT regime                      |      |       |        |         |     |                |        |         |     |       |
| VAT return line                 |      |       |        |         |     |                |        | -       | -   |       |
| VAT reverse charge code         |      |       |        | -       | -   |                | -      |         |     |       |
| VAT supply mode code            | -    | -     |        |         | -   | -              | -      | -       | -   | -     |
| Vehicle                         | -    | -     |        | -       | -   | -              | -      | -       | -   | -     |
|                                 |      |       |        |         |     |                |        |         |     |       |

##### Settings for the separate accounting field
* each field folds/unfolds
* Toggles "Header" and "Lines" - turn on/off the field for headers and lines on [[Document detail. Incoming Invoice]]
* "Mandatory" selector: 
	* Inactive - the field is not mandatory to be filled on document detail
	* Header - header is mandatory to be filled on document detail
	* Line - line is mandatory to be filled on document detail
	* Header or Line - header or line are mandatory to be filled on document detail
	* "Header" and "Lines" chips - mandatory is marked with the star. Not active is pale
	* Mandatory fields are connected to the [[Customization. Validations]]
* Fields that don't have mandatory option:
	* VAT apply reduction coefficient
	* VAT fixed assets (VAT line 47)
	* VAT regime
	* VAT supply mode code


> [!NOTE] VAT regime
> VAT regime is only on headers


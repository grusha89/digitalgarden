
**Czech Legislation**

- Rossum validates the bank account based on the partner's VAT number (DIČ).
- If the bank account is not provided, Rossum validates the partner's IBAN.
- Account and IBAN validation is not possible without a valid partner VAT number (DIČ).

**Slovak Legislation**

- For Slovak legislation, only the IBAN is validated.
- Rossum validates the IBAN based on the partner's VAT ID (IČ DPH).
- Rossum validates the IBAN even if it is extracted with spaces.
- IBAN validation is not possible without a valid VAT ID (IČ DPH).

**Extracting Invalid Data**

When Rossum extracts an invalid account number or bank code, the document is processed normally, but only valid characters are transferred to the wflow.

For example, if Rossum extracts the account number as `ad88877856234š@$..%`, the invalid symbols will be ignored, and only the numbers `88877856234` will be transferred to the wflow. The same rule applies to the bank code.


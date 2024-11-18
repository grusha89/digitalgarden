Doplnění informací u zákazníků, kteří obejdou první krok registrace

For QA: it's better to use disposable temporary emails for testing this feature such as https://temp-mail.org/

Potential customer gets to the registration form https://apptest.wflow.com/registration/user 

### Registration form page

* Wflow logo is in top left corner. It redirects to the wflow.com
* There is a customer success story on the left part of the page
* Lanaguage selector: default language depends on the browser language:
	* Czech
	* Slovak
	* English
	* German
	* Polish
	* Spanish
	* Romanian
	* Ukrainian 
* "Login" button. Redirects to the login page

#### Registration
Try it without obligation for 14 days for free

| Field                                               | Values                                            | Min symb qty | Max symb qty | Description                                                                          |
| --------------------------------------------------- | ------------------------------------------------- | ------------ | ------------ | ------------------------------------------------------------------------------------ |
| Name                                                | abc, 123, #$%, ščž, spaces                        | 1            |              | is required                                                                          |
| Surname                                             | abc, 123, #$%, ščž, spaces                        | 1            |              | is required                                                                          |
| Work e-mail                                         | [e-mail_123@mail.com](mailto:e-mail_123@mail.com) |              |              | valid e-mail only with @ and ".com" - is required. TLD length is more than 4 symbols |
| Phone                                               | +(420)730 962 241                                 | 9            | 16           | * country code is not required, country code can be any, is required                 |
| Where did you hear about us?                        | no restrictions                                   | 1            | 255          | is not required                                                                      |
| Password                                            | spaces are not allowed                            | 8            |              | hide/reveal password, is required                                                    |
| Confirm password                                    | spaces are not allowed                            | 8            |              | must match with password, is required                                                |
| I agree to data processing and contact by wflow.com | checkbox                                          |              |              | is not required                                                                      |
| I agree to the terms and conditions                 | checkbox                                          |              |              | is required                                                                          |

1. Name
2. Surname
3. Work email
    - there is validation of e-mail after the input whether e-mail is already used or not
    - if e-mail is used message shows up “already exists”
4. Phone
    - code +420 is in input by default
    - info message - Phone will help you verify your account and keep it safe
5. Where did you hear about us?
    - field is displayed when user gets to registration without source url
    - fields is not displayed when user gets to registration with source url
    - source url: [https://apptest.wflow.com/registration?source=hodnota](https://apptest.wflow.com/registration?source=hodnota)
6. Password
    - info message - minimal length should be 8
    - possible to reveal and hide password
7. Confirm password
    - must be identical to the password
8. I agree to data processing and contact by wflow.com - checkbox
	* info text appears on hover "I confirm that I have read the information published on wflow.com Czech Republic s.r.o. may contact me by phone or e-mail with information about products and sending a business offer. This consent can be revoked at any time by email listed here: wflow.com/gdpr, or in each individual email"
9. I agree to the terms and conditions - checkbox
	* terms and conditions is redirect link to the https://www.wflow.com/vseobecne-obchodni-podminky


### E-mail confirmation

When the registration form is submitted user is redirected to the Confirm page. The following message is displayed:

Confirm you email address
We have sent you a confirmation email to "user's email"
If you do not see the confirmation email in your inbox, please check your junk mail

"Submit again" button - sends confirmation email once more (
* possible to use only three times, then it disappears

1. User receives the e-mail:
	1. sender is "noreply@wflow.com"
	2. Subject: "E-mail confirmation | wflow.com"
	3. Content: "Wflow logo. Thank you for registering your account at wflow.com. Your account has been created, please validate it by clicking the button below. After validation, please sign in with your e-mail and pasword. "Validate e-mail" button" + In case of any issues with the registration please contact us via email: [support@wflow.com](mailto:support@wflow.com?subject=Email%20subject&body=Message%20default "Title for mail")._|
© 2022 [wflow.com](https://u10278014.ct.sendgrid.net/ls/click?upn=u001.-2FzHFNQK6eFyqIGQCFT-2FSkruDqzKs1l8GJFaCa2EpMXY-3D_DWL_FJhuKNudokjzYBpf3M55JM1mfysN2S-2FK-2BM8SAfD-2BcyhZTIISzfSFUofZkvZoWZCC0ERMQsJ6tFizR6A7yJyVwbd-2BpbWwxZBmAqSMRHG4ObbdqUIC5nVDPCOZO3sV6GATyw-2Fg0a2Kz4X2hRnT2w9S7Pmm3yQhNmrPWnWPupbVWGpmxBtEXOg74o6mH8l6R96i3kHUAQIi9N21UFYFbOXdow-3D-3D "wflow.com main page") Czech Republic s.r.o._|
2. User clicks on "Validate e-mail" and a new tab opens:
	* "E-mail address has been verified. Please continue to login to create a new organization. "Sign in" button"
3. User clicks on "Sign in" and is redirected to the log in page
4. User logs in


### Setting a new account (customer)

1. When user logs in he appears on the customer registration form "Account settings"

| Field               | Values           | Min symb qty | Max symb qty | Description                                                                                                     |
| ------------------- | ---------------- | ------------ | ------------ | --------------------------------------------------------------------------------------------------------------- |
| Name of the company | no restrictions  | 1            | 255          | single spaces are not allowed                                                                                   |
| Company Id          | letters, numbers | 1            | 20           | numbers can go at the beginning and after the letters, value is auto copied with input of "Name of the company" |
| Country             | CZ - by default  |              |              | drop down list to select country legislations                                                                   |
"Get started with wflow" button 

2. User click on"Get started with wflow" button and is redirected to the DEMO organization.
	* The content of Demo organization is described here [[Demo organization. Content]]
	* there is no DEMO organization for TEST stage, so it will fail
	* but creation of DEMO organization can be tested on RC
1. When user gets to the dashboard his new organization is available for him. It has the name of the selected customer name from the previous form
2. When user goes to the organization - quick organization setup launches [[Quick organization setup]]


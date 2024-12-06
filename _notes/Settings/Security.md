
#### Navigation

* New section “Security” is added to the settings. It goes after “Organization profile” in Navigation panel

* Breadcrumbs: Security → organization name → Settings

#### Buttons

* Button “Cancel”
	* cancels all unsaved changes
	- is always active

* Button “Save”
	- active when at least one change was made

#### Require a form of verification: Business (blue chip)

- Description “Set the login rules. Users logged in by other means will not have access to the organization’s data
- contains 4 radio buttons:
    - Do not require
    - Require Microsoft SSO (it would be possible to sign in only via Microsoft account)
    - Require Google SSO ((it would be possible to sign in only via Google account)
    - Require two-factor authentication ((it would be possible to sign in only with 2FA)

#### Login via mobile app

- description “The mobile app does not currently allow the use of 2FA or SSO authentication. Would you like to prevent users from logging in via the mobile app?”
- contains 2 radio buttons:
    - Enable login
    - Prevent login


---

### Feature flag

Section “Security” will be always available in navigation panel whether feature flag is turned on or turned off

When the feature flag is turned off:
- radio buttons are read only
- Not required is selected
- tooltip on hover appears “This function is available only with Business plan”

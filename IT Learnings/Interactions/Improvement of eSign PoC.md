---
type: interaction
last-modified-date: 23-02-2023
creation-date: 23-02-2023
parent-project: eSign
action: Discussion for improvement
people: Saran Raj
object: PoC
---

## Improvement 1 : Force login of user
We can add this property to loginRequest object in authConfig.js in our React App to ask user to force login using their credentials every time and the app doesn't check for cookies stored by other MS apps like Outlook, Azure Portal etc,

```javascript
loginRequest = {
	prompt: 'login'
}
```

^b91abb

## Improvement 2 : Force logout without select account screen

^2457c0

[Stack Overflow Answer](https://stackoverflow.com/questions/71351411/bypass-the-account-selection-screen-while-sign-outlog-out-azure-msal-angular/72970936#72970936)
To do this, first you have to setup the `login_hint` optional claim in the ID token. That needs to be done on the app registration side of things. (Azure Portal -> App Registration -> Token Configuration -> Add Optional Claim -> ID -> login_hint) ^f1b429

Once that claim is in place, MSAL will pass that into `logoutRedirect()` and will skip the account picker prompt.

```javascript
const account = this.msalService.instance.getActiveAccount();
this.msalService.logoutRedirect({ account: account });
```

^df4783

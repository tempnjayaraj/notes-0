---
type: task
last-modified-date: 17-02-2023
creation-date: 09-02-2023
parent-topic: null
parent-project: eSign
tags: Jira, Azure AD, SpringBoot, React, MSAL
task-type: PoC
completed-date: 09-02-2023
---

## Steps
1. Create a SpringBoot Application with two endpoints
	- /redirect/{id} -> should redirect the user to our React Authentication App
	- /get/{id} -> should check for the entry in database
2. Create a React App with MSAL library - Microsoft Authentication
	- Add a route with path param and use the variable in the print function.
3. Create a Jira site and deploy the new app to the site
	- Use router.nagivate(`<toJavaServerPage>`);
	- setInterval()

---
type: task
last-modified-date: 13-03-2023
creation-date: 13-03-2023
parent-topic:
parent-project: eSign 
tags: 
task-type: 
---
![[Pasted image 20230313102536.png]]

```mermaid
graph TD
A[Jira site Approval Page] -->|UUID and details| B[SpringBoot Table]
B -->|redirection <br>with UUID| C[React App]
C --> D{Get Status <br>from Table}
D -->|If Eligible| E[Redirect to AzureLogin]
D -->|Not Eligible| F[Error Page<br>Not Eligible]
E --> |User details| B
```
https://dev-36542246-admin.okta.com/admin/getting-started

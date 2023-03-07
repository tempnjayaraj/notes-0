---
type: document
last-modified-date: 17-02-2023
creation-date: 17-02-2023
parent-topic:
parent-project: eSign
---


## First Proposal
```mermaid
graph TD
A[Jira Page] -->|Create UUID and pass| B[Java Server]
B -->|setInterval waiting for UUID's response| A
B -->|Redirecting to React App with UUID in path param| C[React App]
C --> |Success with UUID | B
```

## Second Proposal
```mermaid
flowchart TD
A[Approve / Reject button clicked in Jira Page] -->|UUID, AccountID, Action| B[Store UUID, AccountID and Action to Table]
B -->|redirect| C[Azure Authentication Page]
C --> D{Is valid user}
D -->|Yes, pass EmailID, time| E[Get Jira AccountID for the emailID]
D -->|No, status failure| H
E --> F{Is AccountID same in the table?}
F --> |Yes, status done| G[Update Table with EmailID and time]
G --> H[Update table with status]
H --> |Send status to Jira page with the emailID| A
F --> |No, status failure| G
```

^f7f660


```ad-todo
- Build an Azure Authentication App in SpringBoot with the client credentials so that we can remove the React App layer in the first proposal
- Add status and action column in Table
- Fill emailID and time only if the Jira accountID of the user logged in our azure app and the requestor is same
```

---
type: task
last-modified-date: 28-02-2023
creation-date: 28-02-2023
parent-topic:
parent-project: eSign
tags: Authentication, Postgres, Table
task-type: feature
---
```mermaid
graph TD
A(Approve / Reject action triggered from Jira Site) -->|uuid, project-id, issue-id, account-id, jira-email-id| B(Spring Boot App inserts data)
B -->|Redirection with UUID| C[React Azure AD Page]
C --> D{Authenticated?}
D --> |Yes<br>get emailID &<br> check if issue <br> is-completed| E{Issue <br>is-completed?}
D --> |No| F
E --> |Yes| F[Stop Process]
E --> |No<br>check <br>approval_status | G{Issue <br>is rejected?}
G --> |Yes| F
G --> |No| H{Is user <br>the creator <br>of issue?}
H -->|Yes| F
H -->|No| I{Has the <br>user approved<br> in other role?}
I -->|Yes| F
I --> |No,<br> update emailID <br>and timestamp<br>in table| B 
```

^c7fd55

![[Pasted image 20230301094935.png]] ^4f6b77

## Things to send from Jira site
1. UUID
2. Project-ID
3. Issue-ID
4. Approval-Category
5. Approval-Group
6. Approval-Status
7. Account-ID

```javascript
const requestBody = {
	"uuid": "<Generated UUID>",
	"project-id": "<project-id>",
	"issue-id": "<issue-id>",
	"approval-category": "<approval-category>",
	"approval-group": "<approval-group>",
	"account-id": "<account-id>"
}
```


### cURL command to get current approval_status of a issue
```bash
curl --request GET \ 
	   --url 'https://sso-plus-three-validators.atlassian.net/rest/api/3/issue/SSO3-1/properties/approval' \ 
	   --user 'johnson.j@archimedis.io:ATATT3xFfGF0_oH9IM1P2afmq8sL8KwEeYBrca8GlgQOyMr9b04w0PPHfI5BxSMVk2aY3rENQs8BtNxwt9I69A2nFT605CROm1SIBb-gmFjp_tA2n5Y-KWLwdGU3_99hd8L9FsGznYHHEfMz-54lGdnljt5jwX6l3ZCEoYpvM-9QUvFLIFOLbME=787F39CD' \ 
	   --header 'Accept: application/json'
```

## Things to send from React App
- emailID

## Changes in SpringBoot App
- POST Met
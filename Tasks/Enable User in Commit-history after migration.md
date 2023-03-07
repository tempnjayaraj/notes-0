---
type: task
last-modified-date: 17-02-2023
creation-date: 14-02-2023
parent-topic: GitLab, Source Code Management Tool
parent-project: Smith and Nephew DevOps
tags: User Authorization, Commit History
task-type: Bug
completed-date: 14-02-2023
---
```ad-hint
title: Learning : User not showing up in Commit-history
After migration, for the user to be enabled in commit history, the user should be confirmed by the administrator of the instance
```

```ad-success 
title: Solution
While making a PUT call to the /users API to add users to the instance, We also have to add another parameter named **"skip_confirmation"**:"**true**" which adds a confirmed user in a call.
```json
{
	"email":"tempnjayaraj@gmail.com",
	"username":"tempnjayaraj",
	"reset_password": true,
	"name":"Johnson Jayaraj",
	"skip_confirmation":true
}
```


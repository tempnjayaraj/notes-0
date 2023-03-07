---
type: task
last-modified-date: 20-02-2023
creation-date: 20-02-2023
parent-topic: GitLab
parent-project: Smith and Nephew DevOps
tags: GitLab, Branch Protection, API Calls
task-type: feature
completed-date: 20-02-2023
---

```ad-info
title: GitLab Branch Protection API
https://docs.gitlab.com/ee/api/protected_branches.html#list-protected-branches
```

```ad-summary
title: Feature explanation
Branch Protection Rules weren't migrated with export-import. So need to GET branch protection rules from GitLab cloud and POST those rules with the parameters to the GitLab instance
```

```ad-hint
title: GET Call from Cloud
URL: `https://gitlab.com/api/v4/projects/<projectID>/protected_branches`
Authorization: `Bearer <token>`
```

```ad-success
title: POST Call to Instance
URL: `http://<instanceIP>/api/v4/projects/<projectID>/protected_branches`
Params
```JSON
{
	"name" : "<branch-name>",
	"push_access_level" : 40,
	"merge_access_level" : 40,
	"allow_force_push" : true
}
```

```ad-note
title: Valid Access Levels
- 0 => No access 
- 30 => Developer access 
- 40 => Maintainer access 
- 60 => Admin access
```


## Steps
```mermaid
graph TD
A(Import Project via Bundle) --> B[Add Integrations]
B --> D[Get Branch Protection from Cloud]
D --> M[Wait for 3 seconds]
M --> E[Get Single branch protection]
E --> F[Delete previous branch protection from project]
F --> G[Add Branch protection with the same name]
G -->|If another branch protection exists| M
G -->|If branch protections are all migrated| H(Complete Import process)
```

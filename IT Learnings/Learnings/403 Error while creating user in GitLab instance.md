---
type: learning
last-modified-date: 17-02-2023
creation-date: 14-02-2023
parent-topic: GitLab
tags: User Creation, API
---
```ad-error
We shall get 403 Forbidden error when we try to create an user via PUT  call to the /users API if we are using the PAT of an user who is not an administrator
```

```ad-success
title: Solution
For creating users in GitLab instance via /users API, we need to hit the API with PAT of a an administrator's account.
```

---
type: meeting
scheduled-for: 
creation-date: 04-01-2023
parent-project: Smith and Nephew DevOps
reason: Demo with Tamil
members: Tamil Selvan, Johnson Jayaraj, Mohan Raj
---

## PoC - 1 Meeting with Tamil | 04-01-2023

```ad-note
title:Observations
1. We need **SSL** to integrate Cloud Jira with our hosted GitLab Server as Jira only connects to HTTPS servers. There is a Cloud Jira App that helps in integrating with GitLab Server (For Branch Creation from Jira Issue)
2. We need to manually configure Cloud Jira integration in our GitLab server as the configuration is not exported. As a result of which, Smart Commits that had links to Cloud Jira Issues behaves just as String.
3. Smart-commits that were pushed after configuring Jira integration behaves as expected.
4. In order to make earlier commits to behave as **smart-commits**, we have rebased the repo to initial commit interactively and have used '*reword*' command which gets the job done. But this method adds another history to the commit.
5. Snippets are getting imported but 
	- their **mentions in commits** are not  working as the IDs get changed when we import the project
	- authors of the snippets get changed to the importer who imported the projects, so the **history is lost** for snippets
6. GitLab Issues are getting imported but
	- authors of the GitLab issues get changed to the importer who imported the projects, so the **history is lost** for issues

```

``` ad-question
title: Questions for further research
- Are  Branch Protection rules imported?
- How to import differential(delta) data from Saas?
- How to import data to GitLab Enterprise Edition server? Are there any differences?
- Is there any other option for migration except Export-Import?
- Is there any solution to retain author history for Snippets and Issues?
```


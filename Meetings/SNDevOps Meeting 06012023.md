---
type: meeting
scheduled-for: 
creation-date: 06-01-2023
parent-project: Smith and Nephew DevOps
reason: Daily Meet
members: Tamil Selvan, Mohan Raj, Johnson Jayaraj
---
# PoC -1 GitLab Migration Saas to Self hosted Server

## Current Migration Status
![[Pasted image 20230106140114.png]]

## GitLab's Project hierarchy
![[Pasted image 20230106135039.png]]

``` ad-note
title: Observations on the Hierarchy
- A Group in GitLab has Members, Milestones and Labels and Integration.
- Any Subgroup / Project can have access to these properties of its parent group
```

```ad-tip
title: Issues we currently have solutions
After import,
- Branch protection rules can be modified with the API
- Commit-messages have to be re-saved so that Jira Integration and usermentions work as expected [Find working solution in YouTube](https://www.youtube.com/watch?v=4YjKY0u9Z6I "https://www.youtube.com/watch?v=4YjKY0u9Z6I")
- Usermentions in Issue titles could be fixed by modifying the tar.gz file that got exported.
```

```ad-danger
title: Issues we currently have no solutions
- Commit-messages that mention Snippets won't behave as expected as the snippet ID changes after import
```

```ad-example
title: Migration Steps as of now
1. On the Self-hosted GitLab Server, we need to create a Group(via APIs) that mirrors the Cloud Group in which the client has project. Please note that history of these entities are lost. These entities include 
	1. Member migration, 
	2. Label Migration
	3. Milestone Migration
	4. Integration Migration (Jira, as the case may be)
1. On the Cloud GitLab site, we need to export the Project in `Settings>General>Advanced>Export Project`. This will generate a tar.gz file that contains the entire project data. Time taken is directly proportional to the size of the project. When the file is ready, we can download it from the same page.
2. We need to modify the file so as to preserve user history. The modification is manual addition of `public.email` to the `project_members.ndjson` file in `./tree/project/project_members.ndjson`
3. Navigate to the group we have created in step 1 and create a new project it by 'New Project' wizard. Then select 'Import Project'.
4. Then select 'GitLab export', provide name for the project and provide path to the tar.gz file that we have modified.
5. Import process can take time depending on the project size and after successful import, we can access the project in the following url `<instanceIP>/<groupName>/<projectName>`
```

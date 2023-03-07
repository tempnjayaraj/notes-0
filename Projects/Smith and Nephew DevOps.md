---
type: project
projectdescription: Migration task for SN DevOps team
project-name: Smith and Nephew DevOps
---

## Project Description

## Members
```dataview
TABLE from "Persons" where contains(projects,"Smith and Nephew DevOps") SORT creation-date DESC
```

## Hierarchy & Roles

## Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-project,"Smith and Nephew DevOps") SORT creation-date DESC
```

## Interactions
```dataview
TABLE object AS What, people AS Person, action AS Action from "Interactions" where contains(parent-project,"Smith and Nephew DevOps") SORT creation-date DESC
```

## Meetings
```dataview
TABLE reason as Reason from "Meetings" where contains(parent-project,"Smith and Nephew DevOps") SORT creation-date DESC
```

## Documents
```dataview
LIST from "Documents" where contains(parent-project,"Smith and Nephew DevOps") SORT creation-date DESC
```

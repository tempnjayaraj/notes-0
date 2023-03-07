---
type: project
projectdescription: eSign plugin for Jira
project-name: eSign
---

## Project Description


## Members
```dataview
TABLE from "Persons" where contains(projects,"eSign") SORT creation-date DESC
```

## Hierarchy & Roles

### Definitions
- **Approval Category** can have **one or many** Approval Groups.
- Each **Approval Group** can have **one or many** users.
- **Approval Group** is usually named with **Roles**.


## Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-project,"eSign") SORT creation-date DESC
```

## Interactions
```dataview
TABLE object AS What, people AS Person, action AS Action from "Interactions" where contains(parent-project,"eSign") SORT creation-date DESC
```

## Meetings
```dataview
TABLE reason as Reason from "Meetings" where contains(parent-project,"eSign") SORT creation-date DESC
```

## Documents
```dataview
LIST from "Documents" where contains(parent-project,"eSign") SORT creation-date DESC
```

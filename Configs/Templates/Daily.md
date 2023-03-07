---
type: daily-note
creation-date: <% tp.file.creation_date("DD-MM-YYYY")%>
---

## Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(creation-date,"<%tp.file.title%>")
```

## Interactions
```dataview
TABLE object AS What, people AS Persons, action AS Action from "Interactions" where contains(creation-date,"<%tp.file.title%>") 
```

## Learnings 
```dataview
TABLE tags AS Tags from "Learnings" where contains(creation-date,"<%tp.file.title%>")
```


## Meetings
```dataview
TABLE reason as Reason from "Meetings" where contains(creation-date,"<%tp.file.title%>") 
```


## List of URLs



## EOD Status


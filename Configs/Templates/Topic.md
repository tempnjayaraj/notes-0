---
type: topic
last-modified-date: <% tp.file.last_modified_date("DD-MM-YYYY") %>
creation-date: <% tp.file.creation_date("DD-MM-YYYY") %>
parent-topic: 
topic-name: <%tp.file.title%>
tags: 
---

## About


## Related Learnings
```dataview
TABLE tags AS Tags from "Learnings" where contains(parent-topic,"<%tp.file.title%>") SORT creation-date DESC
```


## Related Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-topic,"<%tp.file.title%>") SORT creation-date DESC
```

## Related Documents
```dataview
LIST from "Documents" where contains(parent-topic,"<%tp.file.title%>") SORT creation-date DESC
```
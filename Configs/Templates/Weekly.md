---
type: weekly-note
dates: <% tp.date.weekday("DD-MM-YYYY", 1) %>, <% tp.date.weekday("DD-MM-YYYY", 2) %>, <% tp.date.weekday("DD-MM-YYYY", 3) %>, <% tp.date.weekday("DD-MM-YYYY", 4) %>, <% tp.date.weekday("DD-MM-YYYY", 5) %>
---

```ad-important
title: Objectives of this week

```


## Tasks of this week
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 1) %>") or contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 2) %>") or 
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 3) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 4) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 5) %>") SORT creation-date DESC
```


## Learnings of this week
```dataview
TABLE tags AS Tags from "Learnings" where contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 1) %>") or contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 2) %>") or 
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 3) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 4) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 5) %>") SORT creation-date DESC
```

## Interactions of this week
```dataview
TABLE object AS What, people AS Person, action AS Action from "Interactions" where contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 1) %>") or contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 2) %>") or 
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 3) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 4) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 5) %>") SORT creation-date DESC
```


## Meetings of this week
```dataview
TABLE reason as Reason from "Meetings" where contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 1) %>") or contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 2) %>") or 
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 3) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 4) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 5) %>") SORT creation-date DESC
```

## Topics created this week
```dataview
TABLE tags as Tags from "Topics" where contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 1) %>") or contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 2) %>") or 
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 3) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 4) %>") or
contains(creation-date,"<% tp.date.weekday('DD-MM-YYYY', 5) %>") SORT creation-date DESC
```


## Cards done this week



## Cards canceled this week

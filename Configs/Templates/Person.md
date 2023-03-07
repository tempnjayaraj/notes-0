---
type: person
last-modified-date: <% tp.file.last_modified_date("DD-MM-YYYY") %>
creation-date: <% tp.file.creation_date("DD-MM-YYYY") %>
projects: 
---

## EmailID

## Mobile Number

## WhatsApp

## Recent Interactions
```dataview
TABLE object AS What, people AS Persons, action AS Action from "Interactions" where contains(people,"<%tp.file.title%>")
```

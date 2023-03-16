---
type: topic
last-modified-date: 17-02-2023
creation-date: 17-02-2023
parent-topic: Source Code Management Tool
topic-name: GitLab
tags: SCM
---

## About
GitLab is a Source Code Management Tool, in which we can store our code and use when necessary

## Features
- Source Code Management
- Issues
- Milestones
- Snippets
- Automation Tool - GitLab Runner
- Management via APIs

## Hierarchy![[Pasted image 20230106135039.png]]

## Users in GitLab
```ad-tip
title: Members Hierarchy in GitLab
```mermaid
graph LR
A[Group] ===== g1[members]
A --> B
A --> p1[Project]
p1 ==== pm[members]
B[Subgroup] ==== s1[members]
B --> p2[Project]
p2 === ps[members]
```


## Related Learnings
```dataview
TABLE from "Learnings" where contains(parent-topic,"GitLab") SORT creation-date DESC
```


## Related Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-topic,"GitLab") SORT creation-date DESC
```

## Related Documents
```dataview
LIST from "Documents" where contains(parent-topic,"GitLab") SORT creation-date DESC
```

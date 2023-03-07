---
type: topic
last-modified-date: 26-02-2023
creation-date: 26-02-2023
parent-topic: Git, Source Code Management, Tool
topic-name: git filter-repo
tags: git filter-branch
---

## About

[Git filter repo](https://github.com/newren/git-filter-repo.git)

**git filter-repo** is a versatile tool for rewriting history, which includes capabilities I have not found anywhere else. It roughly falls into the same space of tool as [git filter-branch](https://git-scm.com/docs/git-filter-branch) but without the capitulation-inducing poor [performance](https://public-inbox.org/git/CABPp-BGOz8nks0+Tdw5GyGqxeYR-3FF6FT5JcgVqZDYVRQ6qog@mail.gmail.com/), with far more capabilities, and with a design that scales usability-wise beyond trivial rewriting cases. [git filter-repo is now recommended by the git project](https://git-scm.com/docs/git-filter-branch#_warning) instead of git filter-branch.

## Related Learnings
```dataview
TABLE tags AS Tags from "Learnings" where contains(parent-topic,"git filter-repo") SORT creation-date DESC
```


## Related Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-topic,"git filter-repo") SORT creation-date DESC
```

## Related Documents
```dataview
LIST from "Documents" where contains(parent-topic,"git filter-repo") SORT creation-date DESC
```

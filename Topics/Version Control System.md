---
type: topic
last-modified-date: 26-02-2023
creation-date: 26-02-2023
parent-topic: Source Code Management
topic-name: Version Control System
tags: SCM, Version Control
---

## About
Version control systems are a category of software tools that helps in recording changes made to files by keeping a track of modifications done in the code.

## Some definitions
-   **A repository:** It can be thought of as a database of changes. It contains all the edits and historical versions (snapshots) of the project.
-   **Copy of Work (sometimes called as checkout):** It is the personal copy of all the files in a project. You can edit to this copy, without affecting the work of others and you can finally commit your changes to a repository when you are done making your changes.
-   **Working in a group:** Consider yourself working in a company where you are asked to work on some live project. You can’t change the main code as it is in production, and any change may cause inconvenience to the user, also you are working in a team so you need to collaborate with your team to and adapt their changes. Version control helps you with the, merging different requests to main repository without making any undesirable changes. You may test the functionalities without putting it live, and you don’t need to download and set up each time, just pull the changes and do the changes, test it and merge it back. It may be visualized as.

## **Types of Version Control Systems:** 

-   Local Version Control Systems
-   Centralized Version Control Systems
-   Distributed Version Control Systems

**Local Version Control Systems:** It is one of the simplest forms and has a database that kept all the changes to files under revision control. RCS is one of the most common VCS tools. It keeps patch sets (differences between files) in a special format on disk. By adding up all the patches it can then re-create what any file looked like at any point in time. 

**Centralized Version Control Systems:** Centralized version control systems contain just one repository globally and every user need to commit for reflecting one’s changes in the repository. It is possible for others to see your changes by updating. 

Two things are required to make your changes visible to others which are:  

-   You commit
-   They update

![cvcs](https://media.geeksforgeeks.org/wp-content/uploads/20190624140224/cvcss.png)

The **benefit** of CVCS (Centralized Version Control Systems) makes collaboration amongst developers along with providing an insight to a certain extent on what everyone else is doing on the project. It allows administrators to fine-grained control over who can do what. 

It has some **downsides** as well which led to the development of DVS. The most obvious is the single point of failure that the centralized repository represents if it goes down during that period collaboration and saving versioned changes is not possible. What if the hard disk of the central database becomes corrupted, and proper backups haven’t been kept? You lose absolutely everything. 

**Distributed Version Control Systems:** Distributed version control systems contain multiple repositories. Each user has their own repository and working copy. Just committing your changes will not give others access to your changes. This is because commit will reflect those changes in your local repository and you need to push them in order to make them visible on the central repository. Similarly, When you update, you do not get others’ changes unless you have first pulled those changes into your repository. 

To make your changes visible to others, 4 things are required:  

-   You commit
-   You push
-   They pull
-   They update

The most popular distributed version control systems are Git, and Mercurial. They help us overcome the problem of single point of failure.  

![dvcs](https://media.geeksforgeeks.org/wp-content/uploads/20190624140226/distvcs.png)

**Purpose of Version Control:** 

-   Multiple people can work simultaneously on a single project. Everyone works on and edits their own copy of the files and it is up to them when they wish to share the changes made by them with the rest of the team.
-   It also enables one person to use multiple computers to work on a project, so it is valuable even if you are working by yourself.
-   It integrates the work that is done simultaneously by different members of the team. In some rare cases, when conflicting edits are made by two people to the same line of a file, then human assistance is requested by the version control system in deciding what should be done.
-   Version control provides access to the historical versions of a project. This is insurance against computer crashes or data loss. If any mistake is made, you can easily roll back to a previous version. It is also possible to undo specific edits that too without losing the work done in the meanwhile. It can be easily known when, why, and by whom any part of a file was edited.


## Related Learnings
```dataview
TABLE tags AS Tags from "Learnings" where contains(parent-topic,"Version Control System") SORT creation-date DESC
```


## Related Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-topic,"Version Control System") SORT creation-date DESC
```

## Related Documents
```dataview
LIST from "Documents" where contains(parent-topic,"Version Control System") SORT creation-date DESC
```

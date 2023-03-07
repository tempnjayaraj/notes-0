---
type: topic
last-modified-date: 26-02-2023
creation-date: 26-02-2023
parent-topic: Shell
topic-name: SSH Tools
tags: Remote Access
---

## About
These tools can used to connect to / have an easy access to the Linux server hosted either in GCP, AWS / some local network.

## File Transfer Tools:
### WinSCP
WinSCP is a popular SFTP client and FTP client for Microsoft Windows! Copy file between a local computer and remote servers using FTP, FTPS, SCP, SFTP, WebDAV or S3 file transfer protocols.

SSH Clients:
- [Solar Putty's Official Webiste](https://www.solarwinds.com/free-tools/solar-putty)


## Related Learnings
```dataview
TABLE tags AS Tags from "Learnings" where contains(parent-topic,"SSH Tools") SORT creation-date DESC
```


## Related Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-topic,"SSH Tools") SORT creation-date DESC
```

## Related Documents
```dataview
LIST from "Documents" where contains(parent-topic,"SSH Tools") SORT creation-date DESC
```
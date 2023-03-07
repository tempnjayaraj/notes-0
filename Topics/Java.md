---
type: topic
last-modified-date: 26-02-2023
creation-date: 26-02-2023
parent-topic: Programming Languages
topic-name: Java
tags: null
---

## About
Java is a programming Language invented by James Gosling


## Expressions
Correct way to check for null or empty or string containing only spaces is like this:
```java
if(str != null && !str.isBlank())
```


## Executing binaries
[Answer Link](https://stackoverflow.com/questions/5604698/call-an-executable-and-pass-parameters)
```java
Process process = new ProcessBuilder("C:\\PathToExe\\MyExe.exe","param1","param2").start();
int waitFlag = process.waitFor();// Wait to finish application execution.
if (waitFlag == 0) {
 int returnVal = process.exitValue();
} 
```





## Related Learnings
```dataview
TABLE tags AS Tags from "Learnings" where contains(parent-topic,"Java") SORT creation-date DESC
```


## Related Tasks
```dataview
TABLE task-type AS Type, tags AS Tags from "Tasks" where contains(parent-topic,"Java") SORT creation-date DESC
```

## Related Documents
```dataview
LIST from "Documents" where contains(parent-topic,"Java") SORT creation-date DESC
```
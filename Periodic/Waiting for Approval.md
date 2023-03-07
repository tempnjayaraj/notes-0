```dataview 
TABLE WITHOUT ID regexreplace(Tasks.text, "\[.*$", "") as Task FLATTEN file.tasks As Tasks WHERE meta(Tasks.section).subpath ="Ask for approval" LIMIT 20 
```


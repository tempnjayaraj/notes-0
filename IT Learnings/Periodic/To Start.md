```dataview 
TABLE WITHOUT ID regexreplace(Tasks.text, "\[.*$", "") as Task FLATTEN file.tasks As Tasks WHERE meta(Tasks.section).subpath ="To Start" LIMIT 20 
```


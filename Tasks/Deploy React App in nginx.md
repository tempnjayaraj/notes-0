---
type: task
last-modified-date: 06-03-2023
creation-date: 02-03-2023
parent-topic: nginx
parent-project: eSign 
tags: 
task-type: Deployment 
---

## Steps

### Create the build folder
```bash
npm run build
```

### Copy the build folder to your server
You can use WinSCP for this

### Create a file under `/etc/nginx/conf.d` with '.conf' suffix
```groovy
server {
    listen 3000 ssl;
    server_name react.com;
    root /home/ubuntu/build;
    index index.html;
    ssl_certificate /etc/nginx/ssl/saran.crt; 
    ssl_certificate_key /etc/nginx/ssl/saran.key; 
    location / {
        try_files $uri /index.html;
    }
}

```

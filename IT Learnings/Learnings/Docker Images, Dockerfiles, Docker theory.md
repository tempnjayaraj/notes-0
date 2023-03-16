---
type: learning
last-modified-date: 28-02-2023
creation-date: 28-02-2023
parent-topic: Docker
tags: Containers, Second Video
---
## What is a base image?
Base image is usually the OS

Docker uses 'union' filesystem

## What is a Docker image?
A Docker image is like a VM comprised of multiple layers

## What is a Dockerfile
Set of instructions for docker image
Based on base-image

## Dockerfile Syntaxes
```dockerfile
FROM <base-os>
MAINTAINER <name> <email-id>
RUN <command>
CMD <command>
ENTRYPOINT <command>
WORKDIR <Path>
ADD <Path>
ENV <variable-name> <variable value>
```

### Docker commit
```bash
docker commit <container-ID> <repo>:<tag>
```

### Docker export
```bash
docker export <container-ID> > <file-name>.tar
```

### Docker import
```bash
docker import -update < <file-name>.tar
```

### Docker save
```bash
docker save <container-ID>
```

### Docker load
```bash
docker load < <file-name>.tar
```

### .dockerignore
By default, all files in the directory is mounted by the docker daemon so that daemon takes a lot of time to process. But we can use .dockerignore so that daemon does its work efficiently

Every single command is considered a layer.
We can also run multiple lines in a single command

### To tag an image with a name
```bash
docker tag <image-id> <repo-name>/<tag-name>
```

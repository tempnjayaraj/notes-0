---
type: document
last-modified-date: 17-02-2023
creation-date: 17-02-2023
parent-topic: Docker
parent-project: 
---

## Build an image
```bash 
docker build -t <repo-name>:<image-name> .
```

## Run an image with port
```bash
docker run -itd -p <host-port>:<container-port> <repo-name>:<image-name>
```

## Connect to bash of a running container
```bash
docker exec -it <image-id> bash
```

## Stop a running container
```bash
docker stop <container-id>
```

## Clean up dangling containers
```bash
docker system prune -a
```

## Pull an image from Docker-hub repository
```bash
docker pull <repo-name>:<image-name>
```


---
type: learning
last-modified-date: 27-02-2023
creation-date: 27-02-2023
parent-topic: Docker
tags: edureka, Docker Learnings
---

## Containers
Isolated Applications 
Loaded with goods, sealed well and supports smooth operations
What's inside the containers doesn't matter
![[Pasted image 20230227112721.png]]

## Read about
BSDJail, CHRout

## Docker's essence?
Docker provides a platform for building containers.
Docker is a tool to create, deploy and run applications with use of containers

## Docker's tagline
Build, ship and run any software anywhere

Docker image --> Read only Copy
Docker container --> Read and Write Copy

## Docker Daemon 
Responsible fot creation, running and deployment of apps

## Docker Client
Responsible for providing instructions to daemon to work

## Other commands
```bash
docker help
```

```bash
docker search
```

If no tag specified after image, the daemon pulls the 'latest' image

## How to come out of detached container to host machine
- Ctrl + P + Q
- exit

## A container is a VM without OS

## Containerization is OS level Virtualization

## Two modes of running a container
1. Detached mode
2. Root User mode

```bash
docker cp
```

```bash
docker run -v 
```


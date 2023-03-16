---
type: learning
last-modified-date: 28-02-2023
creation-date: 28-02-2023
parent-topic: 
tags: Containerization, Linux, Docker alternative
---
## What is LXD?
- LXD is a container-manager tool
- Allows us to run Linux Containers(LXC)
- Has additional features likes 'Clustering'

## What is LXC?
LXCs are Linux Containers which are more like VMs
 - If we stop LXCs, we won't loose any data
 - LXCs use features of the Linux Kernel
 - Uses components like 'cgroups ' & 'namespaces'

## How to install LXD / LXC?
Available as snap package.

Also download from https://snapcraft.io


So first install Snap and then LXD-->
```bash
sudo apt install snapd
```

```bash
sudo snap install lxd
```


## Snap Commands
### To list all snap packages installed
```bash
snap list
```

## Ubuntu Commands

### To add user to a group
```bash
sudo usermod -aG <group> <user>
```

### Example : To add a user to sudoers list 
```bash
usermod -aG sudo tempnjayaraj
```

### To get path
```bash
which <binary>
```
Example:
```bash
which snap
```

## LXD Commands
### To set initial configuration for LXD
```bash
sudo lxd init 
```

### To list all remote servers
```bash
lxc remote list
```

### To list all images under a repo with filter
```bash
lxc image list <repo-name>: <filters...>
```

Example:
```bash
lxc image list images: debian
```

### To list running / stopped containers
```bash
lxc list
```

### To run an image in a container
```bash
lxc launch <repo-name>: <image-name> <container-name>
```
Example:
```bash
lxc launch images: ubuntu/focal ubuntu
```

### To execute a command in a running container
```bash
lxc exec <container-name> -- <command>
```
Example:
```bash
lxc exec ubuntu -- apt install apache2
```

### To stop a container
```bash
lxc stop <container-name>
```

### To start a container
```bash
lxc start <container-name>
```

### To restart a container
```bash
lxc restart <container-name>
```

### To delete a container
```bash
lxc delete <container-name>
```

### To create a snapshot of a container
```bash
lxc snapshot <container-name> <snapshot-name>
```

### To know more about a container
```bash
lxc info <container-name>
```

### To delete a snapshot of a container
```bash
lxc delete <container-name>/<snapshot-name>
```

### To restore the container to a snapshot
```bash
lxc restore <container-name> <snapshot-name>
```

### To set autostart configuration to a container
```bash
lxc config set <container-name> boot.autostart 1
```

### To set memory configuration to a container
```bash
lxc config set <container-name> limits.memory 1GB
```

### To show configuration of a container
```bash
lxc config show <container-name>
```

### To set delay configuration to a container
```bash
lxc config set <container-name> boot.autostart.delay <seconds>
```

### To set startup order configuration to a container
```bash
lxc config set <container-name> boot.autostart.order <number>
```

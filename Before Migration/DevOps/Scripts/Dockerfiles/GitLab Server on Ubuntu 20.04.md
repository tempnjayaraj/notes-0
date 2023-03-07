---
type: script
subtype: dockerfile
ports: 443,80,22
dependencies: cURL,CA-certificates,OpenSSH
---
Dependencies
- [[cURL]]
- [[CA Certificates]]
- [[OpenSSH]]
- [[GitLab Runner]]
 
## Dockerfile
```dockerfile
FROM ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive
RUN apt update -y
RUN apt install -y curl
RUN apt install -y ca-certificates
RUN apt install -y openssh-server
RUN curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt -y install gitlab-ce
RUN curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | bash
RUN apt-get install gitlab-runner
CMD gitlab-ctl reconfigure & /opt/gitlab/embedded/bin/runsvdir-start

EXPOSE 443 80 22
```
---
type: script
subtype: dockerfile
ports: 8081
dependencies: cURL,Java JDK
---
Dependencies
- [[cURL]]
- [[Java JDK]]
 
## Dockerfile
```dockerfile
FROM ubuntu:20.04

RUN apt update
RUN apt install openjdk-8-jdk -y
RUN apt install curl -y
RUN curl -O https://sonatype-download.global.ssl.fastly.net/repository/downloads-prod-group/3/nexus-3.29.2-02-unix.tar.gz
RUN mkdir /opt/nexus
RUN tar xzf nexus-3.29.2-02-unix.tar.gz -C /opt/nexus --strip-components=1

CMD /opt/nexus/bin/nexus start && /bin/bash

EXPOSE 8081
```
---
type: script
subtype: dockerfile
ports: 8081,8082
dependencies: cURL,Net-Tools
---
Dependencies
- [[cURL]]
- [[Net-Tools]]
 
## Dockerfile
```dockerfile
FROM ubuntu:20.04

RUN apt update
RUN apt install curl -y
RUN mkdir /home/jfrog
RUN apt install net-tools -y
RUN cd /home/jfrog && curl -O -L https://releases.jfrog.io/artifactory/bintray-artifactory/org/artifactory/oss/jfrog-artifactory-oss/7.9.2/jfrog-artifactory-oss-7.9.2-linux.tar.gz
RUN cd /home/jfrog && tar -xvf jfrog-artifactory-oss-7.9.2-linux.tar.gz
RUN cd /home/jfrog && mv artifactory-oss-7.9.2/ artifactory
RUN cd /home/jfrog && rm -rf artifactory-oss-7.9.2
RUN /home/jfrog/artifactory/app/bin/installService.sh

CMD /home/jfrog/artifactory/app/bin/artifactory.sh

EXPOSE 8081 8082
```
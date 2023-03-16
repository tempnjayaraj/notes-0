---
type: script
subtype: docker-compose
ports: 80,8080,8081
images: Gitlab, Nexus, Jenkins
---

```YAML
version: "2.2"
services:
  jenkins:
    image: ubuntu:22.04
    command:
      - /bin/bash
      - -c
      - |
        apt update
        apt install openjdk-17-jdk -y
        apt install curl -y
        apt install software-properties-common -y
        add-apt-repository --yes --update ppa:ansible/ansible
        apt install ansible -y
        curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
        echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | tee /etc/apt/sources.list.d/jenkins.list > /dev/null
        apt-get update
        apt-get install jenkins -y
        java -version
        usr/bin/jenkins
    ports:
      - "8080:8080"
    networks:
      - archimedis
  gitlab:
    image: ubuntu:20.04
    build:
      context: .
      args:
        DEBIAN_FRONTEND: noninteractive
    command:
      - /bin/bash
      - -c
      - |
        ARG DEBIAN_FRONTEND=noninteractive
        apt update
        apt upgrade -y
        apt install -y curl
        apt install -y ca-certificates
        apt install -y curl
        apt install -y openssh-server
        apt install software-properties-common -y
        add-apt-repository --yes --update ppa:ansible/ansible
        apt install ansible -y
        curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
        apt -y install gitlab-ce
        gitlab-ctl reconfigure & /opt/gitlab/embedded/bin/runsvdir-start
    ports:
      - "80:80"
    networks:
      - archimedis
  nexus:
    image: ubuntu:20.04
    command:
      - /bin/bash
      - -c
      - |
        apt update
        apt-get update
        apt install openjdk-8-jdk -y
        apt-get update
        apt install curl -y
        curl -O https://sonatype-download.global.ssl.fastly.net/repository/downloads-prod-group/3/nexus-3.29.2-02-unix.tar.gz
        mkdir /opt/nexus
        tar xzf nexus-3.29.2-02-unix.tar.gz -C /opt/nexus --strip-components=1
        /opt/nexus/bin/nexus run
    ports:
      - "8081:8081"
networks:
  archimedis:
    driver: bridge
```

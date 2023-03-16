- A Dockerfile has no extensions
- Scripting language is 'GoLang'

Command | Use-Case
--|--
FROM | Base Image
MAINTAINER | EmailID of the creator
RUN | Used for installations
COPY | Used to copy data into the docker-container
CMD| Used to run any server every time the container starts
EXPOSE | Used to expose ports from docker-container to the host

## Why docker containers stop without log?
There needs to be a running service /  a command in the dockerfile


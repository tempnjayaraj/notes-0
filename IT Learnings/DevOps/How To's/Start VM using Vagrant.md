1. Open a Folder or Create a new Folder on your Local Machine and Open a terminal and locate to the Folder.
2.  Parallely Open Virtual Box.
3.  To Install Ubuntu machine using commands to Initialize Vagrant, you'll get the following results
	![[Pasted image 20221230122303.png]]
4. To start the virtual machine 
![[Pasted image 20221230122426.png]]
5.  You will see the Machine in Oracle VirtualBox
   ![[Pasted image 20221230122647.png]]
## Links
- [[Access WebApps running in a Linux Server inside Oracle VirtualBox]]


```mermaid
graph TD
A[Clone from GitHub Repository] --> C{Test passed?}
C--> |Failed| D[Dont build as the tests have failed]
C--> |Passed| E[Start building JAR file]
E--> F[Push the JAR file to JFrog Artifactory]
F--> G[Create a docker image with requirements for the application]
G--> H[The Docker ]
```

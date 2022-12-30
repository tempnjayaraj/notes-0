## To Install GitLab 15.7 on Ubuntu 18.04

1. For Installing GitLab Server we can follow the commands below
	[[Ubuntu Update Commands]]  | [[Ubuntu Upgrade Commands]]]

2. Now, install Gitlab required dependency ([[Ubuntu Installation Commands]]).

3. Add GitLab Repository([[Ubuntu Installation Commands]]). you could see the results.![[Pasted image 20221230115853.png]]
   
4. Now, the repository contents are added to
```shell
cat /etc/apt/source.list.d/gitlab_gitlab-ce.list	
```
![[Pasted image 20221230120058.png]]

5. Now, install GitLab using below command([[Ubuntu Update Commands]]] | [[Ubuntu Installation Commands]]])

6. You will see the below results.
	![[Pasted image 20221230120337.png]]
7. Now, you can edit GitLab configuration file to set settings according to your requirements. Use below command [[GitLab Commands]].

8. To Reconfigure you GitLab Server [[GitLab Commands]].

9. As soon as you hit above command, all GitLab services will  start, Check the status of the Server [[GitLab Commands]].
10.  Open the Browser and enter the IP[[Ubuntu Process Commands]] Address gitlab server is opened. Using username has root and the Initial password([[GitLab Commands]]) on the Server.
![[Pasted image 20221230120952.png]]

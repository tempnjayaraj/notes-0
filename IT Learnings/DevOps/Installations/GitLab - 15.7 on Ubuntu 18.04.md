## Steps to Install GitLab 15.7 on Ubuntu 18.04

1. Upgrade Ubuntu Repository using [[Ubuntu Repository Commands#^71286f|upgrade command]] and add GitLab Repository using [[Ubuntu Repository Commands#^efe1a6|gitlab repo addition command]] ![[Pasted image 20221230115853.png]]
2. Verify that GitLab Repo is added to the Ubuntu Repo by executing following command
``` bash
cat /etc/apt/source.list.d/gitlab_gitlab-ce.list	
```
![[Pasted image 20221230120058.png]] 
3. Please install the following three dependencies as per GitLab's requirement
	- [[cURL]]
	- [[CA Certificates]]
	- [[OpenSSH]]

4. After installing dependencies, install GitLab using below command
```shell
sudo apt -y install gitlab-ce
```

5. You will see the below results.
	![[Pasted image 20221230120337.png]]
6. Now, you can edit GitLab configuration file to set settings according to your requirements. To Reconfigure your GitLab Server, use [[Ubuntu GitLab Commands#^8e7c11|reconfigure command]]
7. As soon as you hit above command, all GitLab services will  start, Check the status of the server by [[Ubuntu GitLab Commands#^79d616|service status command]]
8. Open the Browser and enter the IP Address of the machine in which GitLab server is running. Using username as root and the Initial password on the Server. Find the initial password by [[Ubuntu GitLab Commands#^1fbc50|this command]]
![[Pasted image 20221230120952.png]]

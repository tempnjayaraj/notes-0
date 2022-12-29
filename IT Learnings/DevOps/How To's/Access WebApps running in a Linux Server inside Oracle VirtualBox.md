### Steps to configure VM's Network Settings so that the host machine or nearby machines can access the WebApp that is running in Linux VM
- Open Oracle Virtual Box  [Oracle Virtual Box](file:///C:/Program%20Files/Oracle/VirtualBox/VirtualBox.exe)
- Select the VM that hosts the WebApp and make sure the VM is stopped ![[Pasted image 20221229182009.png]]
- Click Settings![[Pasted image 20221229181845.png]]
- Click Network Tab and see for Attached to field under Adapter 1. By default, the value will be NAT.![[Pasted image 20221229182232.png]]
- Change the value of 'Attached to' to 'Bridged Adapter'. Under 'Advanced' tab, set 'Promiscuous Mode' to 'Allow All' and click 'Okay'.![[Pasted image 20221229182602.png]]
- After you have saved changes, start the VM![[Pasted image 20221229183401.png]]
- After you start the VM, get its IP address ![[Pasted image 20221229185201.png]]
- Login to your VM and make sure the WebApplication is running on the expected port by checking list of running processes. ([[Find IP Address]]  | [[Ubuntu List all running processes]]) (For example, if the WebApp is running on Tomcat and the port is 8080, there should be running process with PID for the port 8080 - check the image below). If the WebApplication is not listed on the runnning processes, you have to start the WebApplication manually. Please note that starting of WebApplications are stack specific and there is no common command.![[Pasted image 20221229184955.png]]
- We have successfully finished configuration. Now, minimize the running VM and open a browser [Chrome](file:///C:\Program%20Files\Google\Chrome\Application\chrome.exe) to access the WebApplication. Now the URL is `IPAddress:PortNumber`. In this case, `192.168.10.37:8080`  ![[Pasted image 20221229190034.png]]
## Important Points
- The IP Address of the VM changes everytime the VM is restarted. 
- Only machines that are connected to the Local Router can access this WebApplication.
Please read about [Bridged Networking](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/network_bridged.html)

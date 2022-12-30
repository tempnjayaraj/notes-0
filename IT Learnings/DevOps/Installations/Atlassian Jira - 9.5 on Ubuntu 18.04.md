## Installation of Atlassian Jira 9.5 on Ubuntu 18.04

1. Download executable -  Atlassian-Jira 9.5 bin file - The file is around 510MB  [9.5 Linux Binary file](https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-9.5.0-x64.bin)
``` bash
wget https://www.atlassian.com/software/jira/downloads/binary/atlassian-jira-software-9.5.0-x64.bin
```

2. Before executing the downloaded file, make sure you have user privileges. For enabling access 
``` bash
sudo chmod a+x atlassian-jira-software-9.5.0-x64.bin
```

3. Execute the file as root user
```bash
sudo ./atlassian-jira-software-9.5.0-x64.bin
```

4. During installation you will be asked the following questions. Please choose answers as expected.
	- Choose Express Install (use default settings) - 1, Enter
	- Jira installation location -  (/opt/atlassian/jira) - Enter
	- Use default ports (HTTP: 8080, Control: 8005) - 1, Enter
	- Install Jira as Service - y, Enter
	- Review configs and Install - i, Enter
	- Start Jira Software 9.5.0 now? - y, Enter

5. Installation complete, you can then access Jira application at [Your 8080 port](http://localhost:8080).

### Links
- [[Access WebApps running in a Linux Server inside Oracle VirtualBox]]
- [[Ubuntu IP Commands]]

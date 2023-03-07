---
type: task
last-modified-date: 23-02-2023
creation-date: 22-02-2023
parent-topic: HTTPS Configurations
parent-project: eSign
tags: nginx, SSL, HTTPS, Certifactes
task-type: Configuration
completed-date: 22-02-2023
---
## Things needed

.key file
.crt file

Expected configuration: ->
```javascript
server {
	...
    ssl_certificate     **www.example.com.crt**;
    ssl_certificate_key **www.example.com.key**;
	...
}
```

## Where to get .key file?
You should have a **.key** file in the folder where you had created a CSR file. 

This [[CSR]] file is the one which you need to provide to the Domain provider so that he could give you a certificate file **(.crt)**

## Where to get the .crt file?
You can always visit your domain provider's website to download the .crt file if you have the .key file already with you.

## What if we lost / deleted the .key file?
We could create a new .[[key]] file and [[CSR]] file using [[openssl]] tool. 
After creation, you have to request a certificate from your domain provider with the content of [[CSR]] file. This process is called [[Re-Keying the certificate]]. After this, you can download a .zip file that contains .crt file from the domain provider's website

```ad-success
title: Crisp Content
- Place the .crt and .key file in a known location in your nginx server.
- Open the server's configuration file which you want to run in HTTPS
- Provide the following properties 
```
```javascript
server {
	...
    ssl_certificate     <path-to-certificate-file>.crt;
    ssl_certificate_key <path-to-key-file>.key;
	...
}
```

Reload nginx server with the following command
```bash
systemctl reload nginx
```

---
type: interaction
last-modified-date: 17-02-2023
creation-date: 08-02-2023
parent-project:
action: Discussion
people: Saran Raj, Johnson Jayaraj
object: Azure AD API Call
---

### Get an access token  
```bash
ACCESS_TOKEN=$(curl -X POST [https://login.microsoftonline.com/yourtenantid/oauth2/v2.0/token](https://login.microsoftonline.com/yourtenantid/oauth2/v2.0/token "https://login.microsoftonline.com/yourtenantid/oauth2/v2.0/token") \  
  -H "Content-Type: application/x-www-form-urlencoded" \  
  -d "client_id=yourclientid" \  
  -d "client_secret=yourclientsecret" \  
  -d "grant_type=client_credentials" \  
  -d "scope=[https://graph.microsoft.com/.default"](https://graph.microsoft.com/.default%22 "https://graph.microsoft.com/.default%22") | jq -r '.access_token')
```
### Get List of users
``` bash 
curl -X GET [https://graph.microsoft.com/v1.0/users](https://graph.microsoft.com/v1.0/users "https://graph.microsoft.com/v1.0/users") \  
  -H "Authorization: Bearer $ACCESS_TOKEN" \  
  -H "Content-Type: application/json"
  ```

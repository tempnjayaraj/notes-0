---
type: interaction
last-modified-date: 27-02-2023
creation-date: 27-02-2023
parent-project: eSign
action: Update repo
people: Saran Raj
object: Changes
---

## Left-over changes:
- In manifest.yml
	 1.  :8443 in manifest.yml
- In ApprovalGroups.jsx
	1. import {router} from @forge/bridge;
```javascript
import { router, view } from "@forge/bridge";
```
	  
   2. delay method
 ```javascript
 const delay = (ms) => new Promise((res) => setTimeout(res, ms));
```

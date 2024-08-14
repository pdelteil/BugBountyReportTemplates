
Note: Domains pointing to xxx.cloudapp.azure.com

# Subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointing to an Azure Virtual Machine instance ($DOMAIN2), but that endpoint was not registered. 

## Steps to reproduce
 
Just go to 

$URL

You will see a blank page, but checking the source code you will see proof of the take over. 

```
<html>  
<!-- poc by deleite --> 
 </html>
```



## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Remove the affected DNS record if not used 
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover/
 - https://hackerone.com/reports/661751

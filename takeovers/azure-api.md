
### Note: Domains pointing to xxx.azure-api.net

# Subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointing to an Azure API Management instance ($DOMAIN2), but that endpoint was not registered. I just created the instance and added the domain as custom domain. 

I also needed to publish a 'Developer Portal', also added a custom widget that works as a XSS. This means that any user that visits the website will get their cookies exfiltrated. 


## Steps to reproduce
 
Just go to $URL

You will see a popup with the user's cookies.  


Archived version: $ARCH_URL


## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Remove the affected DNS record if not used. 
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover/
 - https://www.stratussecurity.com/post/azure-subdomain-takeover-guide#viewer-vxl44110971

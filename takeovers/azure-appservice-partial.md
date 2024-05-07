
### Note: Domains pointing to xxx.azurewebsites.net.

# Partial subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointing to an Azure App service domain ($DOMAIN2), but that endpoint was not registered. I created the instance and added the `$DOMAIN` but it was not possible to add a custom domain, due to domain verification implemented by Azure.

It's partial takeover since I can't host any content but I can set this default error page. 
The owner wouldn't be able to host any content on the subdomain since I have it added on my account. It will show an error, so I have the subdomain hostage.


## Steps to reproduce
 
Just go to: $URL

You will see a default error page. 

Archived version: $ARCH_URL

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
 - https://www.youtube.com/watch?v=OpmpGP8UzAg

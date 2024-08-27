
# Subdomain takeover of [$DOMAIN]

## Summary

The subdomain $DOMAIN was pointing to an Azure Traffic Manager instance ($DOMAIN2), but that endpoint was not registered. I just created the instance and added an external endpoint redirecting to a site owned by me. 

## Steps to reproduce

Go to https://$DOMAIN


## Impact

It's very vulnerable to attacks as a malicious user could create any web page with any content and host it on the `$DOMAIN` domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover
 - https://hackerone.com/reports/388622


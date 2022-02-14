# Subdomain takeover [$DOMAIN]

## Summary

The subdomain was not added in Wix, so I added it to my account and linked it to a custom webpage. 

## Steps to reproduce
 
Go to $URL

 
## Recommendations for fix

* Remove the affected DNS record
 

## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the `ford.com` domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover/
 - https://hackerone.com/reports/661751


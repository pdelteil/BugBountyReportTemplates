

# Subdomain takeover 

## Summary

The domains  were not claimed in Pantheon, so I registered a service with this name and therefore was able to takeover the subdomain.  As a POC, I installed a WordPress instance and created a index page.

## Steps to reproduce
 
Check the following urls:
$URLS

 
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


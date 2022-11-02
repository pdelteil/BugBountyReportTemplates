# Subdomain takeover 

## Summary


## Steps to reproduce
 
Check the following [url.]($URL)
As a POC, I deployed an empty page with the following HTML comment `<!-- POC Subdomain takeover Netlify @philippedelteil -->`


 
## Recommendations for fix

* Remove the affected DNS record
 

## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover/
 - https://hackerone.com/reports/661751


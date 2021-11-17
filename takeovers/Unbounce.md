
## Summary 

It's possible to take over subdomains that point to Unbounce. While adding a subdomain no verification of domain ownership is required. 

Vulnerable subdomain: $DOMAIN
## POC Steps 

1. Go to $POC_URL


## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

### Supporting Material/References
- [Steps to POC](https://www.youtube.com/watch?v=-znOxODC2QM)
- https://hackerone.com/reports/407355




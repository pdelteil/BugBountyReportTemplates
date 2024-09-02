## Title

Subdomain takeover in [$domain]

## Summary

The domain `$domain` was poiting to `CNAME` cname.createsend.com, but it was not actively used in the service Campaign Monitor. Because this service does not re-verify custom domains I was able to take it over.

**Steps to reproduce **

Go to URL: $URL

Webarchive version: $URL2

Domain ownership: https://who.is/whois/$domain

## Impact

It's vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site.

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

# Subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointed using CNAME to Amazon S3, but no bucket with that name was created. 

## Steps to reproduce
 
Check the following [URL]($URL)

You will see the following comment in the code:

```
<!-- takeover by pdelteil -->
```

Archived URL: $URL2

## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the $DOMAIN domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Remove the affected DNS record
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover/
 - https://hackerone.com/reports/661751

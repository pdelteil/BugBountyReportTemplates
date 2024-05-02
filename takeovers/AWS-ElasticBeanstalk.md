
# ElasticBean subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointing to an ElasticBean instance `$CNAME`, but that endpoint was not registered. 
To perform the takeover an attacker just need to create an enviroment pointing to `$CNAME`. 

## Steps to reproduce
 
Just go to $URL

You'll see a blank page with the following comment: 

`  <!-- poc by pdelteil -->`

Webarchived version: $URL

## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Remove the affected DNS record if not used.
 

### Supporting Material/References:

 - https://godiego.co/posts/STO-AWS/

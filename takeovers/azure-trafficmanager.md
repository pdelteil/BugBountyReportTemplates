
# Subdomain takeover of [$DOMAIN]

## Summary

The dangling CNAME record `$DOMAIN` was pointing to `$CNAME` the later pointed to `$DOMAIN2` which was not claimed. I registered a service with this name and therefore was able to takeover the subdomain. 
As a POC, I created a simple php page. 

## Affected assets 

$URL

## Steps to reproduce

 1. Using dig, I was able to determine that the subdomain `$DOMAIN` was vulnerable to takeover. This was the output:
```
$DIG
```
In this case `$CNAME` was taken, but `$DOMAIN2` was available.
I created an account on the Azure Portal and deployed a web app where I added the custom domain: $DOMAIN (see screenshot)
 2. After the actions described, the dig command output was:
 
```
$DIG2

```
Basically I created $DOMAIN2 and 'linked' it to $DOMAIN.
 3. Lastly, check $URL for the POC php page. 

 
## Recommendations for fix

 1. Edit your trafficmanager.net settings 
 2. Remove the affected DNS record
 

## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the `ford.com` domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.
 

### Supporting Material/References:

 - https://0xpatrik.com/subdomain-takeover/
 - https://hackerone.com/reports/661751



# Subdomain takeover of $DOMAIN

## Summary

The dangling CNAME record of *$DOMAIN* was pointing to xxx.trafficmanager.net and xxx.trafficmanager.net pointed to *xxx.azurewebsites.net* which was not claimed by you. I registered a service with this name and therefore was able to takeover the subdomain.  As a POC, I created a simple php page. 

## Affected assets 

$URL

## Steps to reproduce

 1. Using dig, I was able to determine that the subdomain `mustestqa.cv.ford.com` was vulnerable to takeover. This was the output:
```
$DIG
```
In this case `xxx.trafficmanager.net` was taken, but `xxx.azurewebsites.net` was available.
I created an account on the Azure Portal and deployed a web app where I added the custom domain: $DOMAIN (see screenshot)
 2. After the actions described, the dig command output was:
 
```
$DIG2

```
Basically I created waws-prod-dm1-161.cloudapp.net and 'linked' it to $DOMAIN.
 3. Lastly, check $URL for the POC php page. 

 
## Recommendations for fix

 1. Edit your xxx.trafficmanager.net settings 
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


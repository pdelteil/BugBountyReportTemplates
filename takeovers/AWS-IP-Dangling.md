## Title
Subdomain Takeover on [$DOMAIN]

## Summary

The subdomain `$DOMAIN` pointed to an Elastic IPv4 address assigned to an AWS EC2 instance that was terminated. This IP address (`$IP`) was released to the AWS Pool and I was able to take it over and assign it to new EC2 instance.


## Steps to reproduce
 
Check the following url:

$URLS

POC  DoS using Cookie bomb

a. Click on the button "Cookie bomb"
b. You will see is not longer possible to access any subdomain of $DOMAIN


Archived URL: $URL2

## Impact

It's vulnerable to attacks as a malicious user could create any web page with any content and host it on the $DOMAIN domain. This would allow them to post malicious content which would be mistaken for a valid site. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Remove the affected DNS record
 

### Supporting Material/References:

- https://blog.melbadry9.xyz/dangling-dns/aws/ddns-ec2-current-state
- https://hackerone.com/reports/1390093


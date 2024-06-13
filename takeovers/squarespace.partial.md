# Partial subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointing to a Squarespace services ($DOMAIN2), but that endpoint was not registered with any Squarespace account. I added the domain to my acocunt but it was not possible to add a custom domain, due to the domain verification.

The owner wouldn't be able to host any content on the subdomain since I have it added on my account, therefore so I have the subdomain hostage.


## Steps to reproduce
 
Just go to: $URL

You will see a default error page. 

Archived version: $ARCH_URL

## Impact

The subdomain is useless for the company since the attacker has it hostage. 

Since the takeover is only partial (can't publish any content) the impact is low. 

 
## Recommendations for fix

* Remove the affected DNS record if not used 
 

### Supporting Material/References:
 - https://hackerone.com/reports/1527405
 - https://0xpatrik.com/subdomain-takeover/

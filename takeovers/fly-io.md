
# Fly.io subdomain takeover [$DOMAIN]

## Summary

The subdomain `$DOMAIN` was pointing to a Fly.io app named `$CNAME`, but that app was not yet launched. 
This left the subdomain vulnerable to a subdomain takeover. To perform the takeover an attacker just need to lauch a Fly.io app called `$CNAME`. 

## Steps to reproduce
 
Just go to this URL: $URL

You'll see a blank page with the following comment: 

`<!-- POC by pdelteil -->`

Webarchived version: $URL

## Impact

Once the attacker takes over the subdomain, they could:


- Host malicious content: They could deploy phishing pages or malware, tricking users into believing they are visiting a legitimate site.
- Compromise sensitive data: If the subdomain is used for login portals, APIs, or other services, the attacker could steal user credentials, session tokens, or other sensitive information.
- Damage reputation: The presence of malicious content on a legitimate domain could lead to a loss of user trust and reputational harm.
- Bypass security controls: If security policies like Content Security Policies (CSP) or CORS are configured based on the domain, the attacker could potentially bypass these controls to launch further attacks.
 
## Recommendations for fix

* Remove the affected DNS record if not used.

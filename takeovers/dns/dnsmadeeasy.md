## Title  

DNS takeover on [$DOMAIN]

## Summary

A DNS takeover occurs when an attacker can take control of any DNS server in the chain of DNS servers responsible for resolving a hostname.

This was possible because the vulnerable zone/domain was pointing to DNSMadeEasy but the registry was not created.


## Steps to reproduce

 In order to create the POC I added the subdomain `poc` to $DOMAIN with a TXT record.  

 Run `dig txt poc.$DOMAIN +noall +answer`

Check the following output:

$SS

## Impact

The impact is high as an attacker could create any subdomain with any content. This would allow them to post malicious content which would be mistaken for a valid site. 
Because the attacker controls de DNS manager, TXT and MX records can be created, therefore allowing the use of $DOMAIN as email sender. 

They could perform several attacks like:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Disable the domain or update the authoritative nameservers to ones that are not susceptible to hijacking.
* Delete the DNS zone from your DNS provider.
 

### Supporting Material/References:

 - https://blog.projectdiscovery.io/guide-to-dns-takeovers/
 - https://github.com/indianajson/can-i-take-over-dns/issues/6


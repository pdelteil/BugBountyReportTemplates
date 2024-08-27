Note: This is not a regular subdomain takeover but a NS/DNS takeover. 

## Title  

DNS takeover in [$DOMAIN]

## Summary

A DNS takeover occurs when an attacker can take control of any DNS server in the chain of DNS servers responsible for resolving a hostname.

This was possible because the vulnerable zone/domain was pointing to AWS Route53 DNS service (using name servers `ns*-*.awsdns-*.*`) but the zone was not created.

## Steps to reproduce

 In order to create the POC I added a TXT record: 

 Run `dig txt $DOMAIN +noall +answer`

Check the following output:

$SS

A more impactful POC is registering a mail service using the subdomain. 

## Impact

The impact is high as an attacker could create any subdomain with any content. This would allow them to post malicious content which would be mistaken for a valid site. 
Because the attacker controls de DNS manager, TXT and MX records can be created, therefore allowing the use of $DOMAIN as email sender. 

Attackers could perform several attacks:
 - Cookie Stealing
 - Phishing campaigns. 
 - Bypass Content-Security Policies and CORS.

 
## Recommendations for fix

* Disable the domain or update the authoritative nameservers to ones that are not susceptible to hijacking.
* Delete the DNS zone from your DNS manager.
 

### Supporting Material/References:

 - https://blog.projectdiscovery.io/guide-to-dns-takeovers/
 - https://github.com/indianajson/can-i-take-over-dns/issues/6


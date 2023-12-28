

## Summary 

It's possible to take over subdomains that point to a Tilda site. While adding a subdomain  no verification of domain ownership is required. 

## POC Steps 

1. I found this error on $URL

2. I created a Tilda account 
3. Assigned $DOMAIN to my webpage.
4. Modified the webpage. 

## Impact

It's extremely vulnerable to attacks as a malicious user could create any web page with any content and host it on the vulnerable domain. This would allow them to post malicious content which would be mistaken for a valid site.

They could perform several attacks like:

    Cookie Stealing
    Phishing campaigns.
    Bypass Content-Security Policies and CORS.

## How to solve 

Remove affected DNS records. 



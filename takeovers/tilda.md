

## Summary 

It's possible to take over subdomains that point to a Tilda site. While adding a subdomain  no verification of domain ownership is required. 

## POC Steps 

1. I found this error on $URL

2. I created a Tilda account 
3. Assigned $DOMAIN to my webpage.
4. Modified the webpage. 

## Impact

The main impact is for the affected client but I also have consequences for Pantheon since didn't place validations to avoid this type of attack. 

## How to solve 

Pantheon should require some kind of ownership verification while adding a subdomain. Add a TXT record in the DNS record of the main domain is one alternative. 




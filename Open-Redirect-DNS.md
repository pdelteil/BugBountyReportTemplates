
# Open Redirect Vulnerability

## Summary
There is an open redirection vulnerability that allows an attacker to redirect anyone to malicious sites.
    
## Steps To Reproduce

Go to this URL: 

https://test.target.com/url=.evil.com

As you can see it redirects to https://test.target.com.evil.com/. An attacker might use this vulnerability to trick users into a malicious content.  
 
## Impact

Attackers can serve malicious websites that steal passwords or download ransomware to their victims machine due to a redirect and there are a heap of other attack vectors.


### Supporting Material/References:
https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html
https://hackerone.com/reports/692154



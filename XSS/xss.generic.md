# Reflected XSS [$DOMAIN]

Reflected cross-site scripting (XSS) arises when an application receives data in an HTTP request and includes that data within the immediate response in an unsafe way. An attacker can execute JavaScript arbitrary code on the victim's session.

## Steps To Reproduce

Go to:
 -  $URL

## Impact

- Perform any action within the application that the user can perform.
- View any information that the user is able to view.
- Modify any information that the user is able to modify.
- Initiate interactions with other application users, including malicious attacks, that will appear to originate from the initial victim user..
- Steal user's cookie. 

### Supporting Material/References:
- https://hackerone.com/reports/438240
- https://portswigger.net/web-security/cross-site-scripting/reflected

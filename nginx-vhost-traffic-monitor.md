
# nginx vhost traffic monitor leaks info

Nginx virtual host traffic status module is publicly available and it's displaying information that might be used by an attacker.
 
## Steps To Reproduce

Go to this URL:
$URL


## Impact
It's possible to obtain the following (but is not limited to):

- Server uptime
- Server zones (traffic, requests, http response codes)
- Upstream servers (proxies, displaying internal IP address and ports)

 
### Supporting Material/References
* https://github.com/vozlt/nginx-module-vts
* 



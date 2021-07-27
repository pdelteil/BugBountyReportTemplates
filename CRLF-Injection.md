
# CRLF injection

## Summary

A CRLF Injection attack occurs when an attacker manages to submit a CRLF into an application. These two special characters represent the End of Line (EOL) marker for many internet protocols, including HTTP. Web applications typically split headers based on where the CRLF character sequence is found. Therefore, if a malicious user is able to inject their own CRLF sequence into an HTTP stream, they gain control over the contents of the HTTP response.


## Steps To Reproduce

> curl -kI $URL
 
```
Response
HTTP/1.1 301 Moved Permanently
Server: Sun-ONE-Web-Server/6.1
Date: Thu, 29 Apr 2021 20:35:00 GMT
Content-length: 122
Content-type: text/html
Location: XXX
Set-Cookie:crlfinjection=crlfinjection
Connection: close

```

## Impact
 As can be seen in the response, the server will issue a Set-Cookie header with an arbitrary value and that cookie will be set on the client.

### Supporting Material/References:
https://www.veracode.com/security/crlf-injection
https://hackerone.com/reports/858650
https://hackerone.com/reports/446271


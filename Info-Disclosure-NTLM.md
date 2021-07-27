
# Info disclosure using NTLM

## Summary

By sending a HTTP NTLM authentication request with null domain and user credentials (passed in the 'Authorization' header), the remote service will respond with a NTLMSSP message (encoded within the 'WWW-Authenticate' header) and disclose information to include NetBIOS, DNS, and OS build version if available.

## Steps To Reproduce

$URL

Run the following command:

    nmap -p 80 --script http-ntlm-info --script-args http-ntlm-info.root=/root/ $DOMAIN

Output
```
Starting Nmap 7.80 ( https://nmap.org ) at 2020-10-30 20:56 -03

$OUTPUT

```

## Impact

Disclosure of the following info:

 - OS Version ($OSVERSION)
 - Domain Name ($DOMAINNAME)
 - Computer/Server name ($COMPUTERNAME)
  

### Supporting Material/References:
https://nmap.org/nsedoc/scripts/http-ntlm-info.html
https://en.wikipedia.org/wiki/Windows_Server_2012_R2



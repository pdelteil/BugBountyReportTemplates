
# Trace.axd page leaks sensitive information

## Summary
`Trace.axd` leaks sensitive information by allowing no-signed in users to view previous requests sent to the webserver.

## Steps To Reproduce

1.  Visit $URL
3.  Click on `View Details` for any request that seems interesting. 


## Impact

It's possible to obtain the following (but is not limited to):
-   Cookies, session tokens, and CSRF tokens
-   IP addresses and headers
-   Application specific information (endpoints, files and directories on the filesystem, software versions, etc. )
 

### Supporting Material/References:
https://hackerone.com/reports/519418



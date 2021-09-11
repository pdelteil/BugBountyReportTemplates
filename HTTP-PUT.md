
# HTTP PUT method is enabled [$DOMAIN]

## Summary

Unrestricted PUT method allowed upload of static content to server

## Steps To Reproduce

Let's test the PUT method uploading a file called `testing-put.txt` 

```
$REQUEST
```
Where XXX is just a random string.

Now, let's retrieve the uploaded file 

```
$REQUEST2
```
And the response is:

```
$RESPONSE

```
Which is the content uploaded. 



## Impact

The HTTP PUT method is normally used to upload data that is saved on the server at a user-supplied URL. If enabled, an attacker may be able to place arbitrary, and potentially malicious, content into the application. Depending on the server's configuration, this may lead to compromise of other users (by uploading client-executable scripts), compromise of the server (by uploading server-executable code), or other attacks.
 

### Supporting Material/References:
https://hackerone.com/reports/487656




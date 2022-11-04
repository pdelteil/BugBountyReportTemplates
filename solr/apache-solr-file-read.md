
# Solr LFI

## Summary

Apache Solr versions prior to and including 8.8.1 are vulnerable to local file inclusion. It's possible to fetch all files and folders that the user running Solr has privileges. 


## Steps To Reproduce


Steps To Reproduce:
Request the following URLS

  1. [File: /etc/passwd]()
```
****

```
  2. [File: /etc/hosts]()
```
****
```
Supporting Details:
- https://twitter.com/Al1ex4/status/1382981479727128580
- https://nsfocusglobal.com/apache-solr-arbitrary-file-read-and-ssrf-vulnerability-threat-alert/
- https://twitter.com/sec715/status/1373472323538362371




## Impact

Sensitive information is available to download. It was possible to read database host names, database names and passwords. This information may lead to an account take over.






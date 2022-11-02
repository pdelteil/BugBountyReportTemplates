
# LFI allows reading Wordpress config files

## Summary

A Local File Inclusion vulnerability in the Nevma Adaptive Images plugin before 0.6.67 for WordPress allows remote attackers to retrieve arbitrary files via the $REQUEST['adaptive-images-settings']['source_file'] parameter in adaptive-images-script.php.


## Steps To Reproduce

Summary:
Apache Solr versions prior to and including 8.8.1 are vulnerable to local file inclusion.

Platform(s) Affected:
$URL

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
 

### Supporting Material/References:
https://www.cvedetails.com/cve/CVE-2019-14205/
https://www.acunetix.com/blog/articles/local-file-inclusion-lfi/





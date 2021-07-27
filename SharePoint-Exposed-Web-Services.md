# SharePoint exposed web services

## Summary

Microsoft SharePoint is a web application platform developed by Microsoft. Because of improper configuration an anonymous user has access to the SharePoint Web Services.

## Steps To Reproduce
Go to 
1. https://usace-admin.dps.mil/_vti_bin/lists.asmx?WSDL
2. https://ako.ssi.tradoc.army.mil/_vti_bin/lists.asmx?WSDL

Check


## Impact
The SharePoint Web Services can disclose sensitive information. This information can be used to launch further attacks.

 
### Supporting Material/References

* https://hackerone.com/reports/761158


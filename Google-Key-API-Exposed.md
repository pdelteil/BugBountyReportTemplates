

# Google Maps API Key exposed

## Summary

API keys have some security configurations for blocking unauthorized usage for malicious people which does **not** comes by default. 
Developers need to configure this security controls within their own decisions. While these API keys are designed as public API keys and does not have any impact in terms of customer data confidentiality/integrity, this security configurations still need to be implemented for blocking unauthorized usage.


## Steps To Reproduce

 1. Go to this [URL]($URL)
 2. Find in source code for the API Key $KEY 
 3. Use the API in the following ways (exploit):
	 a. [Google Maps](https://maps.googleapis.com/maps/api/staticmap?center=45%2C10&zoom=7&size=400x400&key=$KEY)

I did 1,000 requests of the API Key using Burp Intruder. (screenshot)

Request used:
```
GET /maps/api/staticmap?center=45%2C10&zoom=7&size=400x400&key=$KEY HTTP/1.1
Host: maps.googleapis.com
Connection: close
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
```

	
## Impact

-   Consuming company’s monthly quota or can over-bill with unauthorized usage of this service and do financial damage if the company does not have any limitation settings on API budgets.
-   Conduct a DOS specific to the service if any limitation of maximum bill control settings exist in the Google account.
- Costs table:
```
-------------------------------------------------------------
  Results 		|| Cost Table/Reference to Exploit:
-------------------------------------------------------------
- Staticmap 		|| $2 per 1000 requests
``` 
 

### Supporting Material/References:
 - [Unauthorized Google Maps API Key Usage Cases, and Why You Need to Care](https://medium.com/bugbountywriteup/unauthorized-google-maps-api-key-usage-cases-and-why-you-need-to-care-1ccb28bf21e)
 


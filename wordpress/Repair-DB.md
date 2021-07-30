

# Wordpress repair database function 

## Summary

The **WP_ALLOW_REPAIR** constant, when used, activates the native WordPress feature to repair corrupted tables in the database. The same feature can also be used to, in addition to repair, optimize tables.

## Steps To Reproduce

Go to $URL/wp-admin/maint/repair.php

And click in one of the buttons. 

It's also possible repeat this request several times ( I tested with 10 just to be nice with your DB)

**Request**

```
GET /wp-admin/maint/repair.php?repair=2 HTTP/1.1
Host: $DOMAIN
Sec-Ch-Ua: "Chromium";v="91", " Not;A Brand";v="99§§"
Sec-Ch-Ua-Mobile: ?0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.114 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Connection: close
```


## Impact
The database must be repaired, and/or optimized when needed. This must be done by authorized persons. Therefore, after making use of the feature consider removing the **WP_ALLOW_REPAIR** constant from the wp-config.php file.

Otherwise, anyone can perform these costly operations on your database and compromise the performance and operation of your application.
 

### Supporting Material/References:
 https://nestify.io/blog/wp_allow_repair-repair-optimize-wordpress-database/


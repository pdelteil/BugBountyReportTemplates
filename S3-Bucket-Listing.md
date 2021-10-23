
# S3 bucket listing /download

## Summary
It's possible to get a listing and download every file in the S3 bucket `$DOMAIN` 

## Steps To Reproduce

We can find the name of the buckets going to https://URL

We can list all files using the aws CLI:
`` aws s3 ls s3://S3``

We can calculate the size of the bucket 
```
aws s3 ls --summarize --human-readable --recursive s3://S3 |grep "Total"
 Total Objects: 222,968,902
 Total Size: 917.0 GB
```
More importantly we can download the entire bucket: 
``aws s3 cp s3://S3. --recursive``

## Impact
An attacker can download files that are not intended to be public, the bucket is very big, most of the file (if not all) are terrain files. 
An attacker can increase dramatically the bandwidth used by the bucket, programmatically and continuously downloading the entire bucket content setting a more expensive bill. 

Example: 
The attacker has a 1500 Mbps internet connection (let's use an average of 1200 Mbps)  and here's the data transfer cost:
```
**Data Transfer OUT From Amazon S3 To Internet**

Up to 1 GB / Month $0.00 per GB
Next 9.999 TB / Month $0.09 per GB
Next 40 TB / Month $0.085 per GB
Next 100 TB / Month $0.07 per GB
Greater than 150 TB / Month $0.05 per GB
```
Let's assume you are in the 'Next 40 TB/Month' category, if an attacker downloads the entire bucket in one day, that would increase the bill in the following way
```
 (1200/8) [MB/s]* 3600 [s]* 24 [hrs] =  12,960 GB per day
 - 12,960 [GB] * 0.085 [$/GB]= 979 [$]
 - Month -> $29.376
```


### Supporting Material/References

https://hackerone.com/reports/278191


# Brute Force Amplification Attack

## Summary

Using Wordpress' XML remote procedure protocol (XML-RPC) is possible to perform a ​Brute Force Amplification Attack​. With every request the attacker could test for 1,000 username and password pairs.Using Burp's Intruder I was able to test 100,000 users and passwords for Wordpress logins in less than a minute. 

**​I did not encounter any type of rate limit**.  Every request had 1,000 calls to the method ​wp.getUsersBlogs​ to test for credentials.

Platform(s) Affected
$URL
XML RPC :​ $URL


## Steps To Reproduce

1. Download the request file (request.txt in attached request.zip)
2. Launch Burp, go to the Repeater tab, in the request section, do a right click and select the option 'Pastefrom file'
3. Load the file request.txt.
4. Click Send. (You might need to add the domain rem-b.com and the port 443)
5. You will get a response (just like the attached response.txt file in attached response.zip)In order to repeat the request 10 times we need to:
	1.  Send the request to Intruder (right click on the request on the Repeater).
	2. On tab ​Position​, make sure Attack type is Sniper. Click on the button 'Clear'.
	3. Go to the first username on the list, click Add $ two times.
	4. Go to payload, select payload type 'Numeric'
	5. In payload options, select from: 1, to: 10, step: 1.
	6. Click Attack. 

Attack will be performed, we could increase the value of to to a quite bigger numbers than 10.

Note: 1,000 is not the max. limit of the amount of calls that can be made to the ​wp.getUsersBlogs​ function by every request


## Impact

With enough time the attacker could retrieve usernames and passwords of the blog platform. With that access the attacker could publish and delete posts.It's also possible to create a DOS attack, every request is 1 MB in size, using only 1,000 threads we could send 1GB of traffic with little effort. Scaling up this value we could create a DOS on the website.

## Recommendations for fix

 1. Disable XMLRPC if not used. 
 2. Rate limit the amount of requests accepted by the XMLRPC. 
 3. Set access rules to specific and trusted IPs in order to use XMLRPC.


### Supporting Material/References:

 - https://blog.cloudflare.com/a-look-at-the-new-wordpress-brute-force-amplification-attack/
 - https://hackerone.com/reports/125624




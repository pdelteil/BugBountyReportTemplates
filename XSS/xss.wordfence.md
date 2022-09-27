
# WordPress plugin Wordfence 7.4.6 XSS

WordPress plugin Wordfence version 7.4.6 has a XSS vulnerability. [More info](https://vulmon.com/exploitdetails?qidtp=packetstorm_exploits&qid=4c4a19b487de18d919fa7c64af08c127)

Reflected cross-site scripting (XSS) arises when an application receives data in an HTTP request and includes that data within the immediate response in an unsafe way. An attacker can execute JavaScript arbitrary code on the victim's session.

The Moodle instance installed has a XSS vulnerability in the parameter redirect_uri. 


## Steps To Reproduce

Go to:

 -  https://$DOMAIN/wp-content/plugins/wordfence/lib/diffResult.php?file=%22%3E%3Csvg%2Fonload%3Dalert(\`XSS!`)%3E
 -  
You will see a popup appear. 



## Impact

 -  Perform any action within the application that the user can perform.
-   View any information that the user is able to view.
-   Modify any information that the user is able to modify.
-   Initiate interactions with other application users, including malicious attacks, that will appear to originate from the initial victim user..
- Steal user's cookie. 

 

### Supporting Material/References:

* https://gist.github.com/0x240x23elu/891371d46a1e270c7bdded0469d8e09c
* https://hackerone.com/reports/438240
* https://portswigger.net/web-security/cross-site-scripting/reflected


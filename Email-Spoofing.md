## Email spoofing

## Summary

Email spoofing is the forgery of an email header so that the message appears to have originated from someone or somewhere other than the actual source. Email spoofing is a tactic used in phishing and spam campaigns because people are more likely to open an email when they think it has been sent by a legitimate source.

I found this vulnerability checking the MX records in [MxToolBox](https://mxtoolbox.com/SuperTool.aspx?action=mx%3a$DOMAIN&run=toolpage).

## Affected domains

 1. $URL

## Steps To Reproduce:

1. Go to https://emkei.cz/. 
2. Write down XXX in `From Email ` field
3. Add Support in the `From Name` field.
4.  Write down the test address (where you want to check the spoofed email) in the `To` field. (I used my personal email pdelteil@gmail.com)
5. Add a subject and body test messages. 
6. Click en send. 

An email will be send to your test address from 
$EMAIL

## Tests (screenshots)


- Gmail 

 
## Impact:

Users can be triggered to click into links controlled by the attacker. Even though in my case the email was received in the spam folder, this problem can be overcame by reaching the user and make him/her to check for a urgent message that might not have been received.

## Supporting Material/References:

 - https://hackerone.com/reports/288707
 


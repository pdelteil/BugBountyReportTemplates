

# Git config file exposed 

## Summary
There's an accessible git repository on [$URL(https://$URL). This issue allows an attacker to retrieve source code and git history.

## Steps To Reproduce

Go to this urls:

 1. $URL/.git/logs/HEAD
 2. $URL/.git/config
 
 ##Comments_while_commiting_this: To can actually download the entire repo using git dumper. 

## Impact
This issue could potentially reveal sensitive information.

 
### Supporting Material/References:
https://hackerone.com/reports/541349
https://hackerone.com/reports/970520


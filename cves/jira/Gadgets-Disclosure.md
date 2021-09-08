

# JIRA Installed gadgets disclosure

Atlassian Jira Server allows an unauthenticated user to list installed gadgets and xml config files. 



## Steps To Reproduce

Go to: 	
* $URL/rest/config/1.0/directory
* $URL/rest/gadgets/1.0/g/com.atlassian.confluence.plugins.gadgets:gadget-search/gadgets/gadget-search.xml




## Impact

Attacker can list all existing installed gadgets on this Jira server. 

 


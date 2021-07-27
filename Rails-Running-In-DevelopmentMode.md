
# Rails application running in development mode

## Summary

This Ruby on Rails web application is running in development mode. When you generate a Ruby on Rails application it will create three environments: development, production and test. In development mode, Rails is not as secure as it shows diagnostics pages that leak a lot of sensitive information about the application internals.

## Steps To Reproduce
Go to $URL

 - Gems (and versions) being used
 - Local server paths. 
 - Local IP address. 
 - Routes. 
 - HTTP Methods used. 

## Impact

An attacker could leverage the information finding vulnerable gems. 
Use disclosed paths to infer attack points.  ( /apis(/:client_type)/services/voice/update-pin(.:format), /apis(/:client_type)/services/voice/update-question(.:format))


 

### Supporting Material/References:
https://www.acunetix.com/vulnerabilities/web/rails-application-running-in-development-mode/




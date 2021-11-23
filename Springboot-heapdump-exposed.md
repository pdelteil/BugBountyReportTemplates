
## Description

Heap dumps contain a snapshot of all the live objects that are being used by a running Java application on the Java heap.


## Steps To Reproduce
1.  Go to the following URL $URL/actuator/heapdump 
2.  This url will download the heap dump of the server
3.  Using a memory analyzer such as Eclipse memory analyzer it's possible to read the file.
4.  Inside the file you can sensitive information as trustStorePassword (see screenshot)




## Impact


This vulnerability allows any attacker to perform many severe attacks such as :


-   PII Data leaking
-   Accessing all credentials from the application properties such as , admin credentials, swagger credentials , billing credentials .
-   Get database credentials
-   Server Environment variable
-   Server config Properties.
-   Payments manipulations and money stealing
-   and more

 
### Supporting Material/References

 - https://reflectoring.io/create-analyze-heapdump/
 - https://www.ibm.com/support/pages/was-javaxnetssltruststorepassword-disclosure

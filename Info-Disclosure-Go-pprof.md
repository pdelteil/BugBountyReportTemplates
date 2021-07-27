
# Information Disclosure with Go pprof

## Summary
Golang’s [net/http/pprof](https://golang.org/pkg/net/http/pprof/) package is incredibly powerful: it’s trivial to debug a running production server. In the process it’s equally easy to accidentally expose your debugging information to the world.

## Steps To Reproduce

Go to: `https://$DOMAIN/debug/pprof/allocs?debug=1`  
You will see these links:

-   allocs: A sampling of all past memory allocations
-   block: Stack traces that led to blocking on synchronization primitives
-   cmdline: The command line invocation of the current program
-   goroutine: Stack traces of all current goroutines
-   heap: A sampling of memory allocations of live objects. You can specify the gc GET parameter to run GC before taking the heap sample.
-   mutex: Stack traces of holders of contended mutexes
-   profile: CPU profile. You can specify the duration in the seconds GET parameter. After you get the profile file, use the go tool pprof command to investigate the profile.
-   threadcreate: Stack traces that led to the creation of new OS threads
-   trace: A trace of execution of the current program. You can specify the duration in the seconds GET parameter. After you get the trace file, use the go tool trace command to investigate the trace.

## Impact
An attacker can obtain the following info (but not limited to):

-   Function names and file paths are revealed.
-   Profiling data may reveal business sensitive information (for example traffic to a web server)
-   Profiling degrades performance, providing a vector for a DoS attack

### Supporting Material/References:

* http://mmcloughlin.com/posts/your-pprof-is-showing
* https://hackerone.com/reports/783807


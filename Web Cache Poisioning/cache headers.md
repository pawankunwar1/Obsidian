Server Cache Headers->
-> `X-Cache` in the response may have the value of `miss` when the request wasn't cached and the value `hit` when it is cached
->`Cache-Control` indicates if a resource is being cached and when will be the next time the resource will be cached again: `Cached-Control: public, max-age=1800`
-> Vary is often used in the response to `indicate additional headers` that are treated as `part of the cache key` even if they are normally unkeyed
-> `Age` defines the times in seconds the object has been in the proxy cache
-> `Server-Timing: cdn-cache; desc=HIT` also indicates that a resource was cached
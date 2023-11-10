-> If the page give 403 -> then add random directory value -> if the response is 404 not found -> then it is 403 only for main home page -> do directory fuzzing and so on.

1) HTTP Methods/Verbs fuzzing :- If getting 401 and 403 in `GET` requests change it to `POST, PUT, PATCH, DELETE, HEAD, CONNECT, TRACE `.
2) User-Agent fuzzing:- Sometimes developers want to serve different content depending on what kind of browser/OS you use to access the web app. In this case of misconfiguration you might be able to get access to the resource only by modifying User Agent.
3) HTTP Headers fuzzing:- X-Forwarded-For, Referer and Authorization headers. X-Forwarded-For can be fuzzed to bypass security controls that rely on IP address filtering. By changing the IP address in this header, an attacker can attempt to bypass any security controls that are based on IP address filtering.
4) Downgrade the protocol version:-  if HTTP/2 wont let you in or bypass. We can use different versions like `1.1, 0.9, 1.0, 1.1, 2` and remove the Host header at all. ->` if we do not put Host in the header if the server and any other security mechanism is not configured in the right way. it puts the destination address itself in the header , and this make us known as local.`
5) Path Fuzzing and creative string literals:- if `example.com/admin` gives you 403. Then try adding ``/%2e/ or /%252e/ to the path:
     `example.com/%252e/admin` . Why this work -> The `/%2e/` or `/%252e/` sequence represents the URL-encoded version of the `.` character. By using this sequence in the URL path , the server may interpret the request as accessing a different path than the one intended, potentially bypassing access controls that are based on the original path.
6) HTTP request smuggling :- #httprequestsmuggling
7) Exploiting Hop-by-Hop request header:- Hop-by-hop headers are HTTP headers that are intended for communication between a client and server, and that are not forwarded  by intermediaries such as proxies or caches. These headers are called "hop-by-hop" because they are processes on a per-hop basis, meaning that each intermediary along the path of the request will see and potentially modify the headers as they pass though, The HTTP/1.1 specification defines the following headers as hop-by-hop headers: 
     `Connection, Keep-Alive, Proxy-Authentication, Proxy-Authorization, TE, Trailer, Transfer-Encoding , Upgrade
     -> When a proxy receives a request containing one of these headers, it should process it and then remove the header before forwarding the request to the next server in the chain.
     -> `Note that the `HTTP/2 protocol` has a different mechanism for handling headers, with the concept of "pseudo-headers" that are treated differently from regular headers.
     --> What interesting, you can define what headers should be removed by adding them to Connection header, like this:-
     `GET /index.html HTTP/1.1`
     `Host: example.com`
     `Connection: close, X-Forwarded-For`
     `X-Forwarded-For: 192.167.0.1`
 -> Using this trick, you may be able to bypass 401 and 403 status codes, as long as some server in the request chain relies on the header that the proxy add/intermediary server adds, but you define it to be removed. However, it is important to note that just because you can remove the header, somewhere in the chain does not necessarily mean the host is vulnerable. This is only the first step in exploiting the underlying issue, and it is necessary to explore further to determine if it can be used to bypass the authorization check. Additionally, it is important to recognize that this technique may cause unexpected issues on the server-side, depending on how the server handles the removed header.

--> Example payloads to be fuzzed with `Connection` header:
       --> hop_by_hop_heades:
       - Accept 
       - Accept-Application
       - Accepted
       - Accept-Encoding
       - Accept-Encodxng
       - Accept-Language
       - Accept-Ranges
       - Accept-version
       - Access-Control-Allow-Credentials
       - Access-Control-Allow-Headers
       - Access-Control-Allow-Origin
       - Access-Control-Expose-Headers
8) Spring Framework specific bypass technique:- Versions < 5.3 have `useSuffixPatternMatch` setting set to true by default. It means that methos mapped for example to /admin would match `/admin[.].*` , it can be used to bypass access restrictions.
9) Using method override headers like `X-HTTP-Method` if backend server supports them.
10) Manipulating the URL path using directoral traversal.
11) `api//users`
12) `api\\users`
13) `/api/v1/user/id.json`
14) `/api/v1/user/id?`
15) `/api/v1/user/id/`
16) 
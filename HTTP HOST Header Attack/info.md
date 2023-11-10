```
Websites that uses HTTP/2 end-to-end are inherently immune to request smuggling attacks. As the HTTP/2 specification introduces a single, robust mechanism for specifing the length of a request, there is no way for an attacker to introduce the required ambiguilty.

However, many webistes have an HTTP/2 speaking front-end server, but deploy this in fornt of back-end infrastructure that only supports HTTP/1. This means that the font-end effectively has to translate the requests it receieves into HTTP/1.1. This process is know as HTTP downgrading. 
```

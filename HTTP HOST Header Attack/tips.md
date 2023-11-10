-> add `Host: host.com.` in password reset functionality and see if we get the mail in gmail containing `host.com.` domain

-> replace burp collaborator domain in Host Header -> to check SSRF

-> if backend is checking Host header value add -> burp collaborator server into Host value and add website host to the url

-> sometimes server validate only depends upon Connection header , we can bypass by using -> Connection: keep-alive with single conenction attack

->add lining wrapping 
`
`GET /example.com HTTP/1.1
 Host: bad.example.com
Host: Vulnerable.com`

-> always add -> Host: example.com:portnumber in reset passwrod functionality and see .
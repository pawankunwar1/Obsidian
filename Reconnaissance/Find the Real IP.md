--> Roadmap
1) SSL Certificates 
2)  Histroic DNS Records
3) Subdomains
4) Security Headers
5) Favicon Hashes
6) Remove Host value


7) SSL Cetificates --> Websites use SSL Certificate to allow secure connection to be made via HTTPS. Each Certificate is unique and has its own fingerprint. It is possible to find all the certificates that have ever associated to a domain. This include non-Cloudflare issued certificates and historic certificates. These can be searched with Censys, Shodan , Zoomeye and cert.sh. -> `curl -k https://cloudflare.com --resolve original.com:443:127.0.0.1` --> it is a curl command to get the content from real ip not from cloudflare, sometimes response come from cache also so.
8) Historic DNS Records --> Not all sites start out using Cloudflare. Old DNS A records can often reveal the original hoating IP. We can find in --> https://securitytrails.com/ , also www.riskiq.com
9) Sudomains --> Sometimes only main domain or some subdomains are behind the cloudflare but not all the subdomains are in behind the cloudflare.
10) Security Headers --> We can find security headers in www.securityheaders.io .  from here we can see the website is using Contet-Security-Policy :- Content-Security-Policy tell browser to only load content from the certain domains or subdomains. Now we go to censys, shodan , zoomeye and search that Content-Security-Policy and it returns all the domain , ip that uses that same content-Security-Policy. `services.http.responses.headers.content_security_policy:'domain.com'` here this command in censys return all the contetn_securtiy_policy which is same as domain.com
11) Favicon Hash --> Almost all webistes have Favicon. Usually found at -> https://example.com/favicon.ico . Every favicon.ico have unique hash that deifnes them. --> we can find www.faviconhash.com which give the Hash for us. now, we can go to the shodan and search `http.favicon.hash:53036791` and it gives all the domain , ip using this favicon.
12) We can found` copyright` line in the footer , or a link to a Terms and Conditions  or ©2021 imaginaryCompany All rights reserved
     then we can dork by using intext:"©2021 imaginaryCompany All rights reserved" or search on shodan, censys.
    7) Remove Host value: if the certain endpoint show Location in the HTTP response then if we remove all HTTP headers including Host header, it may give to real ip of the website.


Manual approach --> Using Cnesys, Securitytrails, FOFA, Zoomeye
Automation approach --> uncover tool , syntax --> `**uncover -q “target.com” -e censys,fofa,shodan,shodan-idb | httpx | tee ips.txt**` it search ip address from censys, fofa, shodan and store in ips.txt file 

--> Then use `open multiple urls extension to open ip in ulrs` 



Other Methods
1) If we can get the ASN of the application, then grap all ASNs -> then grap all the ip ranges and try to check all live HTTP Server and compare the titile of website and ip.
2) If the application is using mail server in own its server . If we do password reset and sen the email in burp collabrator we can get the real ip.



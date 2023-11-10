1) Try all redirect status codes (301, 302, 303, 307, 308,etc). When you are hitting your own server with the request, try redirecting to sensitive locations using all of the HTTP redirect status codes.
2) Open redirect :- If there is open redirect vulnerability means there can be SSRF 
3) URL Structuring :-  ![[F3HuPMaW4AAatTu.png]]
4) Url Encoding(1x, 2x, 3x):- Using multiple layers of URL encoding can allow for bypassing of restrictions. 
5) DNS Rebuiding :- When a target is resolving the domain to make sure that its not pointing to localhost or other internal domains, we may able to bypass this with DNS rebinding.
6) Hitting Semi-Internal hosts:- While you may not to able to hit localhost or other private IP space,try hitting servers that are in DMZ which are accessible externally, but when requested from inside the network don't have the same protections.
7) IPv6 addresses:- Sometimes you can use IPv6 addresses to bypass restrictions on which IPs you can communicate with. #manyfacesofip
8) Use different local address:- Sometimes there is just a simple blacklist in place to prevent SSRF. In cases like this, it's trivial to bypass these by using alternative IP addresses(0.0.0.0 , 127.0.0.2)
9) Protocol-Based Bypasses:- a) File scheme(file:///ect/passwd) b) Dict scheme(dict://127.0.0.1:1337/) c) FTP scheme(ftp://127.0.0.1) d)TFTP scheme(tftp://evil.com/test) e) SFTP scheme(sftp://evil.com:1337/test) f) LDAP schem(ldap://127.0.0.1:1337/) g)Gopher scheme(gopher://evil.com/-Test)
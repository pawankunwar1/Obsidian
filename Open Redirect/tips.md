->`https://example.com/login?next=dashboard.` --> here we can find open redirect 

-->Referer-Based Open redirects --> which can be found without having redirect parameter in url but can have in Referer-Based HTTP header so , keep on eye in 3XX response code like 301 and 302.


Google dorks 
-->inurl:%3Dhttp site:example.com   --> %3D = '='  
-->inurl:%3D%2F site:example.com    ---> %2f = '/' so --> '=/'
-->inurl:redir site:example.com
-->inurl:redirect site:example.com
-->inurl:redirecturi site:example.com
-->inurl:redirect_uri site:example.com
-->inurl:redirecturl site:example.com
-->inurl:redirect_uri site:example.com
-->inurl:return site:example.com
-->inurl:returnurl site:example.com
-->inurl:relaystate site:example.com
-->inurl:forward site:example.com
-->inurl:forwardurl site:example.com
-->inurl:forward_url site:example.com
-->inurl:url site:example.com
-->inurl:uri site:example.com
-->inurl:dest site:example.com
-->inurl:destination site:example.com
-->inurl:next site:example.com



`https:attacker.com`
https;attacker.com
https:\/\/attacker.com
`https:/\/\attacker.com ``
https;,attacker.com
htt ps://evil.com

this can help to bypass URL validation based on blocklist where validator rejects URL that contains strnigs like http:// or https://

Most Modern browser also automatically correct backslaches (\) to forward slashes(/)--> https:\\example.com to` https://example.com`



Maybe validator checks the redirect domain by domain that contain or ends eith the same site domain which can be bypassed --> redire=`https://example.com.attacker.com`
                                --> redir=`https://attacker.com/example.com`
                                -->redir=`https://example.com.attacker.com/example.com`
                                
                                
                                
also can be bypassed using usernameportion like --> redir=`https://example.com@attacker.com/example.com`

can also used data: scheme such as redir=`data:text/html;base64,
`PHNjcmlwdD5sb2NhdGlvbj0iaHR0cHM6Ly9leGFtcGxlLmNvbSI8L3NjcmlwdD4= `   whcih is base64 code for ``<script>location="https://example.com"</script>`



using non-ascii character like `https://attacker.com%ff.example.com` , here %ff is the character ÿ which is non-ascii character, here validator setermined that example.com is the domain name and attacker.comÿ is the subdmoain name. sometimes browsers decode non-ascii characters into question marks like `` https://attacker.com?.example.com` , here example.com becomes query not the hostname 




here (%E3%80%82) represents non-ascii character dot(。) but the browser interpret it as real dot(.) 



somwtimes developer use only relative url to redirect like /login -->`https://example.com/login` so we can bypyass this by using //attacker.com as // can be used for http or https protocol and if webiste block the uses od double // we can bypass by /%0d/ or /%oa/ or /%09/ .



->In Apache or some version of IIS  , also in ngix if we forgot to put  `/` on /directory  like this at the end of directory then it will give 301 code with Location header like Location: https://example.com/directory/

->?redirect=//differentFaceOfIp -> try it out
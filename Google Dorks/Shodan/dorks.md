```
org:”target.com”  
http.status:”<status_code>”  
product:”<Product_Name>”  
port:<Port_Number> “Service_Message”  
port:<Port_Number> “Service_Name”  
http.component:”<Component_Name>”  
http.component_category:”<Component_Category>”  
http.waf:”<firewall_name>”  
http.html:”<Name>”  
http.title:”<Title_Name>”  
ssl.alpn:”<Protocol>”  
http.favicon.hash:”<Favicon_Hash>”  
net:”<Net_Range>” (for e.g. 104.16.100.52/32)  
ssl.cert.subject.cn:”<Domain.com>”  
asn:”<ASnumber>”  
hostname:”<hostname>”  
ip:”<IP_Address>”  
all:”<Keyword>”  
“Set-Cookie: phpMyAdmin”  
“Set-Cookie: lang=”  
“Set-Cookie: PHPSESSID”  
“Set-Cookie: webvpn”  
“Set-Cookie:webvpnlogin=1”  
“Set-Cookie:webvpnLang=en”  
“Set-Cookie: mongo-express=”  
“Set-Cookie: user_id=”  
“Set-Cookie: phpMyAdmin=”  
“Set-Cookie: _gitlab_session”  
“X-elastic-product: Elasticsearch”  
“x-drupal-cache”  
“access-control-allow-origin”  
“WWW-Authenticate”  
“ X-Magento-Cache-Debug”  
“kbn-name: kibana”  
“X-App-Name: kibana”  
“x-jenkins”



"For finding template injection"

http.component:"AngularJS"
http.component:"Ruby"
http.component:"Ruby on Rails"
http.component:"Python"
-------------------------------

"For finding php vulnerabilites"

http.component:"PHP"
----------------------------------------------

"For finding SAP XSS CVE"

http.component:"SAP"
----------------------------------------------

"For finding Log4j"

http.component:"Java"
----------------------------------------------

"For finding vulnerable databases

http.component:"MongoDB"
http.component:"MySQL"
----------------------------------------------

"For finding unauthentication admin dashboard"

http.component:"Python"
http.component:"Django"
----------------------------------------------

"For finding api misconfigurations"

http.component:"Open Graph"
http.component:"Sentry"
http.component:"Google Maps"
----------------------------------------------

"For finding prototype pollution"

http.component:"JQuery"
http.component:"Node.js"
http.component:"Loadash"
----------------------------------------------

"For finding caching issues"

http.component:"Cloudflare"
http.component:"Cloudfront"
http.component:"Amazon Cloudfront"
http.component:"cdnjs"
http.component:"jsDelivr"
http.component:"CreateJS"
http.component:"Akamai"
http.component:"JQuery CDN"
http.component:"Varnish"
http.component:"Netlify"
http.component:"WP Rocket"
----------------------------------------------

"For finding subdomain takeovers" 

http.component:"Amazon S3"
http.component:"GitHub Pages"

----------------------------------------------

"For finding smuggling/desync attacks"

http.component:"HTTP/2"
http.component:"HTTP/3"
----------------------------------------------

"For finding deserialization vulnerabilities"

http.component:"Microsoft ASP.NET"
----------------------------------------------

"For finding OAuth squatting"

http.component:"Google Sign-in"
http.component:"Apple Sign-in"
http.component:"Facebook Sign-in"
----------------------------------------------

"For finding CMS related vulnerabilities"

http.component:"WordPress"
http.component:"Contentful"
http.component:"Discourse"
http.component:"Joomla"
http.component:"Drupal"
http.component:"WooCommerce"
http.component:"Wix"
http.component:"Shopify"
http.component:"Magento"
http.component:"Contentful"
http.component:"Django CMS"
http.component:"Craft CMS"
----------------------------------------------



NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks will not give you the direct hit to vulnerabilities.

NOTE 2 : This dorks will help you to know what vulnerabilities you can find on your target domains, if any of your target is using the above mentioned components.

NOTE 3 : All dorks mentioned are from the perspective of bug bounty.





http.component_category:"Programming languages"
http.component_category:"Databases"
http.component_category:"CDN"
http.component_category:"Caching"
http.component_category:"Javascript libraries"
http.component_category:"Javascript frameworks"
http.component_category:"Security"
http.component_category:"Miscellaneous"
http.component_category:"Maps"
http.component_category:"CMS"
http.component_category:"Message boards"
http.component_category:"Web frameworks"
http.component_category:"Authentication"
http.component_category:"Web servers"
http.component_category:"Payment processors"
http.component_category:"WordPress plugins"
http.component_category:"Blogs"


NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks will not give you the direct hit to vulnerabilities.

NOTE 2 : All dorks mentioned are from the perspective of bug bounty.



http.waf:"Cloudflare"
http.waf:"Cloudfront"
http.waf:"Akamai"
http.waf:"AWS"
http.waf:"Azure"
http.waf:"Imperva"
http.waf:"Nginx"
http.waf:"Barracuda"
http.waf:"F5"
http.waf:"Sucuri"
http.waf:"ModSecurity"
http.waf:"Fastly"
http.waf:"Citrix"
http.waf:"FortiWeb"


NOTE 1 : You need to enumerate and find a way how you can bypass this firewalls. There are many techniques to bypass this firewalls and someof them have the payloads (XSS) hosted on github and you can also read different medium blogs.

NOTE 2 : All dorks mentioned are from the perspective of bug bounty.



product:"Apache httpd"
product:"OpenSSH"
product:"ciscoSystems"
product:"nginx"
product:"BigIP"
product:"Microsoft HTTPAPI httpd"
product:"Apache Tomcat/Coyote JSP engine"
product:"OpenResty"
product:"Postfix smtpd"
product:"MySQL"
product:"Exim smtpd"
product:"Kubernetes"
product:"AkamaiGHost"
product:"PostgreSQL"
product:"MiniServ"
product:"Grafana (Open Source)"
product:"SQL Server Browser Service"
product:"Apache Tomcat"
product:"Node.js"
product:"CouchDB"
product:"MongoDB"
product:"Memcached"



NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks will not give you the direct hit to vulnerabilities.

NOTE 2 : This dorks will help you to know what vulnerabilities you can find on your target domains, if any of your target is using the above mentioned products.

NOTE 3 : All dorks mentioned are from the perspective of bug bounty.




http.html:"Wordpress"
http.html:"Discourse"
http.html:"Grafana"
http.html:"Jenkins"
http.html:"MongoDB"
http.html:"JBoss"
http.html:"Drupal"
http.html:"Joomla"
http.html:"Kibana"
http.html:"Elastic"
http.html:"Elasticsearch"
http.html:"Docker" 
http.html:"Kubernetes"
http.html:"Redis"
http.html:"Citrix"
http.html:"Outlook"
http.html:"Owa"
http.html:"Index of /"
http.html:"DisallowedHost at /"
http.html:"InfluxDB"
http.html:"Apache Kafka"
http.html:"Apache Tomcat"
http.html:"Prometheus"
http.html:"Logstash"
http.html:"Terraform"
http.html:"Jira"
http.html:"Atlassian"
http.html:"Confluence"
http.html:"GraphQL"
http.html:"Gitlab"
http.html:"Git"
http.html:"Github"
http.html:"Postman"
http.html:"Swagger UI"
http.html:"nagios"



NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks sometimes might give you the direct hit to vulnerabilities.

NOTE 2 : All dorks mentioned are from the perspective of bug bounty.




http.title:"Grafana"
http.title:"Jenkins"
http.title:"MongoDB"
http.title:"JBoss"
http.title:"Django"
http.title:"Drupal"
http.title:"Joomla"
http.title:"Discourse"
http.title:"Wordpress"
http.title:"Kibana"
http.title:"Elastic"
http.title:"Elasticsearch"
http.title:"Docker"
http.title:"Kubernetes"
http.title:"Redis"
http.title:"Citrix"
http.title:"Outlook"
http.title:"Owa"
http.title:"Index of /"
http.title:"DisallowedHost at /"
http.title:"InfluxDB"
http.title:"Apache Kafka"
http.title:"Apache Tomcat"
http.title:"Prometheus"
http.title:"Jira"
http.title:"Atlassian"
http.title:"Confluence"
http.title:"GraphQL"
http.title:"Gitlab"
http.title:"Git"
http.title:"Github"
http.title:"Postman"
http.title:"Swagger UI"
http.title:"nagios"



NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks sometimes might give you the direct hit to vulnerabilities.

NOTE 2 : All dorks mentioned are from the perspective of bug bounty.





http.status:"101"  --------------------------------------------------------------  Switching Protocols (For finding web socket hijacking)
http.status:"102"  --------------------------------------------------------------  WebDAV (For checking enabled webdav)
http.status:"200"  --------------------------------------------------------------  OK
http.status:"301"  --------------------------------------------------------------  Moved Permanently
http.status:"302"  --------------------------------------------------------------  Moved Temporarily
http.status:"307"  --------------------------------------------------------------  Temporary Redirect
http.status:"308"  --------------------------------------------------------------  Permanent Redirect
http.status:"401"  --------------------------------------------------------------  Unauthorized (For checking authorization bypass)
http.status:"403"  --------------------------------------------------------------  Forbidden (For checking forbidden bypass)
http.status:"404"  --------------------------------------------------------------  Not Found (For checking subdomain takeover)
http.status:"407"  --------------------------------------------------------------  Proxy Authentication Required (For checking authenthication bypass)
http.status:"426"  --------------------------------------------------------------  Upgrade Required (For checking desync/smuggling attaks)
http.status:"501"  --------------------------------------------------------------  Not Implemented (For checking desync/smuggling attaks)



NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks will not give you the direct hit to vulnerabilities.

NOTE 2 : All the mentioned shodan dorks are from the perspective of bug bounty.






http.favicon.hash:"81586312"      -------------------------------------------------------   Jenkins  
http.favicon.hash:"743365239"     -------------------------------------------------------   Atlassian
http.favicon.hash:"628535358"     -------------------------------------------------------   Atlassian
http.favicon.hash:"705143395"     -------------------------------------------------------   Atlassian
http.favicon.hash:"855273746"     -------------------------------------------------------   JIRA
http.favicon.hash:"981867722"     -------------------------------------------------------   Atlassian – JIRA
http.favicon.hash:"552727997"     -------------------------------------------------------   Atlassian – JIRA
http.favicon.hash:"-1581907337"   -------------------------------------------------------   Atlassian – JIRA
http.favicon.hash:"-305179312"    -------------------------------------------------------   Atlassian – Confluence
http.favicon.hash:"-1642532491"   -------------------------------------------------------   Atlassian – Confluence
http.favicon.hash:"-1379982221"   -------------------------------------------------------   Atlassian – Bamboo
http.favicon.hash:"1768726119"    -------------------------------------------------------   Outlook Web Application
http.favicon.hash:"1356662359"    -------------------------------------------------------   Outlook Web Application
http.favicon.hash:"-1249852061"   -------------------------------------------------------   Microsoft Outlook
http.favicon.hash:"442749392"     -------------------------------------------------------   Microsoft OWA
http.favicon.hash:"708578229"     -------------------------------------------------------   Google
http.favicon.hash:"-297069493"    -------------------------------------------------------   Apache Tomcat
http.favicon.hash:"396533629"     -------------------------------------------------------   OpenVPN
http.favicon.hash:"1772087922"    -------------------------------------------------------   APS.NET
http.favicon.hash:"878647854"     -------------------------------------------------------   BIG-IP
http.favicon.hash:"-335242539"    -------------------------------------------------------   f5 Big IP
http.favicon.hash:"1278323681"    -------------------------------------------------------   Gitlab
http.favicon.hash:"516963061"     -------------------------------------------------------   Gitlab
http.favicon.hash:"1642701741"    -------------------------------------------------------   Vmware Secure File Transfer
http.favicon.hash:"1895360511"    -------------------------------------------------------   VMware Horizon
http.favicon.hash:"-1255992602"   -------------------------------------------------------   VMware Horizon
http.favicon.hash:"-991123252"    -------------------------------------------------------   VMware Horizon
http.favicon.hash:"-1967743928"   -------------------------------------------------------   SAP ID Service: Log On
http.favicon.hash:"1347937389"    -------------------------------------------------------   SAP Conversational AI
http.favicon.hash:"-266008933"    -------------------------------------------------------   SAP Netweaver
http.favicon.hash:"-318947884"    -------------------------------------------------------   Palo Alto Networks
http.favicon.hash:"602431586"     -------------------------------------------------------   Palo Alto Login Portal
http.favicon.hash:"1453890729"    -------------------------------------------------------   Webmin
http.favicon.hash:"-1038557304"   -------------------------------------------------------   Webmin
http.favicon.hash:"1280907310"    -------------------------------------------------------   Webmin
http.favicon.hash:"479413330"     -------------------------------------------------------   Webmin
http.favicon.hash:"-1544605732"   -------------------------------------------------------   Amazon PHP Application - AWS Elastic Beanstalk
http.favicon.hash:"-1010568750"   -------------------------------------------------------   phpMyAdmin
http.favicon.hash:"-476231906"    -------------------------------------------------------   phpMyAdmin
http.favicon.hash:"1993518473"    -------------------------------------------------------   cPanel
http.favicon.hash:"1544230796"    -------------------------------------------------------   cPanel Login
http.favicon.hash:"902521196"     -------------------------------------------------------   Netflix
http.favicon.hash:"1611729805"    -------------------------------------------------------   Elastic (Database)
http.favicon.hash:"1552860581"    -------------------------------------------------------   Elastic (Database) 
http.favicon.hash:"-38580010"     -------------------------------------------------------   Magento
http.favicon.hash:"-167656799"    -------------------------------------------------------   Drupal
http.favicon.hash:"1174841451"    -------------------------------------------------------   Drupal
http.favicon.hash:"-1153950306"   -------------------------------------------------------   Dell
http.favicon.hash:"1627330242"    -------------------------------------------------------   Joomla
http.favicon.hash:"-1950415971"   -------------------------------------------------------   Joomla
http.favicon.hash:"366524387"     -------------------------------------------------------   Joomla
http.favicon.hash:"-759754862"    -------------------------------------------------------   Kibana
http.favicon.hash:"-1200737715"   -------------------------------------------------------   Kibana
http.favicon.hash:"-267431135"    -------------------------------------------------------   Kibana
http.favicon.hash:"1668183286"    -------------------------------------------------------   Kibana3
http.favicon.hash:"75230260"      -------------------------------------------------------   Kibana4
http.favicon.hash:"-1414475558"   -------------------------------------------------------   Microsoft IIS
http.favicon.hash:"1726027799"    -------------------------------------------------------   IBM Server
http.favicon.hash:"-1616115760"   -------------------------------------------------------   ownCloud
http.favicon.hash:"2124459909"    -------------------------------------------------------   HFS (HTTP File Server)
http.favicon.hash:"731374291"     -------------------------------------------------------   HFS (HTTP File Server)
http.favicon.hash:"191654058"     -------------------------------------------------------   Wordpress Under Construction Icon
http.favicon.hash:"-1067420240"   -------------------------------------------------------   GraphQL Playground
http.favicon.hash:"1232159009"    -------------------------------------------------------   Apple
http.favicon.hash:"-1498185948"   -------------------------------------------------------   Apple
http.favicon.hash:"1382324298"    -------------------------------------------------------   Apple


NOTE 1 : You need to enumerate and look for the vulnerabilities. This dorks will not give you the direct hit to vulnerabilities.

NOTE 2 : All dorks mentioned are from the perspective of bug bounty.





port:21 "proftpd"
port:21 "220" "230 Login successful."
port:27017 "MongoDB Server Information"
port:22 OpenSSH
port:25 "exim"
port:80 "Apache httpd"
port:3389 "remote desktop"


NOTE 1 : You need to enumerate and look for the sensitive information. This dorks will not give you the direct hit to vulnerabilities.

NOTE 2 : All dorks mentioned are from the perspective of bug bounty.
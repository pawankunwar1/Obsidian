<mark style="background: #BBFABBA6;">Passive Enumeration</mark>
       1) Certificate Transparency
             a) <mark style="background: #FF5582A6;">Crt.sh </mark>--> https://crt.sh/ works as database, means when we enter domain name it gives result(subdomain) based on the domain certificate(SSL certificate) means it checks domain certificate and search that certificate in its database where other subdomains/domain contains.  We can also search organization name in crt.sh for finding subdomin, we can get org name from `connection secure` in browser.  plus we can search `copyright something` . For finding org name we can view in chrome.
             b) <mark style="background: #FF5582A6;">Censys.io </mark>--> www.censys.io 
             c) <mark style="background: #FF5582A6;">Facebook </mark>--> https://developers.facebook.com/tools/ct/
        2) <mark style="background: #FF5582A6;">Google </mark>-<mark style="background: #FF5582A6;">Dorking</mark>-> `site:*.example.com`  --> https://docs.google.com/document/d/1ydVaJJeL1EYbWtlfj9TPfBTE5IBADkQfZrQaBZxqXGs/edit
        3) <mark style="background: #FF5582A6;">Pastebin </mark>--> Pastebin allows users to store and share plain source code online. dork-->`site:pastebin.com ".domain.com"` 
        4) <mark style="background: #FF5582A6;">OSINT </mark>-->from github and gitlab
        5) <mark style="background: #FF5582A6;">Google dork</mark> --> intext"2023 yahoo" or copyright things
        6) <mark style="background: #FF5582A6;">Amass </mark>-->  `amass enum -passive -d example.com -o results.txt`
        7) <mark style="background: #FF5582A6;">subfinder </mark>-->
        8) <mark style="background: #FF5582A6;">massdns </mark>--> `./scripts/ct.py example.com |     ./bin/massdns -r ./lists/resolvers.txt -o S -w results.txt` 
        9) <mark style="background: #FF5582A6;">BIng  Dorking</mark>--> https://support.microsoft.com/en-us/topic/advanced-search-keywords-ea595928-5d63-4a0b-9c6b-0b769865e78a
        10) <mark style="background: #FF5582A6;">DuckDuckGo </mark>--> https://duckduckgo.com/duckduckgo-help-pages/results/syntax/
        11) DNS Addregators
               a) <mark style="background: #FF5582A6;">VirusTotal </mark>-->https://www.virustotal.com/gui/home/upload
               b) <mark style="background: #FF5582A6;">DNSDumpster </mark>-->https://dnsdumpster.com/
               c) <mark style="background: #FF5582A6;">Netcraft </mark>--> https://searchdns.netcraft.com/
        12) <mark style="background: #FF5582A6;">Subject Alternate Name (SAN)</mark> --> It gives subdomains list which certificate  is same(used) as the given domain(which is given by me) --> `true | openssl s_client -connect facebook.com:443 2>/dev/null | openssl x509 -noout -text  | perl -l -0777 -ne '@names=/\bDNS:([^\s,]+)/g; print join("\n", sort @names);'
        13)  <mark style="background: #FF5582A6;">Rapid7 Forward DNS dataset </mark>--> THe dataset contains the response the DNS requests for all forward DNS names known by Rapid7. We can download dataset here --> https://opendata.rapid7.com/sonar.fdns_v2/
        14) 

<mark style="background: #BBFABBA6;">Active Enumeration</mark>
             1) <mark style="background: #FF5582A6;">Brute Force </mark>-->ffuf , dirsearch, gobuster 
             2) <mark style="background: #FF5582A6;">Amass</mark> --> `amass enum -brute -w wordlists.txt -d domain.com -o output.txt`
              3) <mark style="background: #FF5582A6;">Worldlists </mark>--> <mark style="background: #FFF3A3A6;">Jhaddixs wordlists</mark> --> https://gist.github.com/jhaddix/86a06c5dc309d08580a018c66354a056 , <mark style="background: #FFF3A3A6;">SecLists </mark>--> https://github.com/danielmiessler/SecLists/tree/master/Discovery/DNS and <mark style="background: #FFF3A3A6;">Assetnotes </mark>--> https://github.com/assetnote/commonspeak2-wordlists, Github -->https://raw.githubusercontent.com/appsecco/bugcrowd-levelup-subdomain-enumeration/master/subdomain_wordlist.txt
              4) <mark style="background: #FF5582A6;">Gobuster </mark>--> `gobuster dns -t 30 -w subdomains.txt -d example.com` 
              5) <mark style="background: #FF5582A6;">DNS ZONE Transfer </mark>--> `dnsrecon -a -d tesla.com` or `dig axfr @ns1.example.com example.com` 
              6) <mark style="background: #FF5582A6;">CNAME Records </mark>--> `dig +short -x 'dig +short example.com'`  here ' = ``. ``this command first find out the ip address of example.com and find if other domain is host in that ip address . --> one subdomain point another sub-domain through CNAME Records, so we can get subdomains from there.
              7) RiskIQ.com --> www.riskiq.com
              8) Aquatone tool
              9) Assetfinder -> `echo domain.com | assetfinder --subs-only`
              10) alt dns
              11) puredns
              12) ALLforONe(imp)
              13) sudomy


--> `subfinder --all -dL sub.list` -> this command take list of subdomains and find find other subdomains.






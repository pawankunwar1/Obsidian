```
POST /about HTTP/1.1
Host: exmaple.com
Transfer-Encdoing: chunked
Content-Length: 6

3
abc
Q
```
->here if both frontend and backend take Content-Length header than it will give -> backend response
-> here if both frontend and backend take Transfer-Encoding header than it give frontend response by removing Q
-> here if frontend use Tranfser-Encoding and backend use Content-Length then ot give frontend response
-> here if frontend use Content-Length and backend use Transfer-Encoding use -> then it gives `timeout`

```
POST /about HTTP/1.1
Host: example.com
Transfer-Encoding: chunked
Content-Length: 6

0

X
```
-> here if both frontend and backend use CL.CL then -> backend response
-> here if both frontend and backend use TE.TE then -> backend repsones
-> here if front end use Transfer-Encoding then backend use Content-Length then -> `timeout
-> here if forntend and backend use CL.TE then -> socket poisonn



---> Maybe direct use of Content-Length and Tranfser-Encoding be not be applied but we can add Content-Length with different Transfer-Encoding headers like #te 


-> Cl!=0 -> here front end server accepts  body data with get requests but backend ignore content-length header and act two requests(not only get request but all request that doesnt have body)

-> CL=CL -> here if the request have two Content-Length header then front end will take first Content-Length header and backend will take second Content-Length header 

->CL-TE -> if Content-Length and Transfer-Encoding both are used then Content-Length header is ignored. here frontend use Content-Length header but backend server uses RFC spefication so that it ignore Content-Length and accept Trasfer-Encoding.
-> there is no csrf security at all

-> change methods 

-> remove csrf token and all csrf key value pair and see -> if not then with that change methods

-> check if csrf token is tied to the user session or not ->if not then try other use csrf token

-> if csrf token is tied with non session token then try to inject non-session token through CRLF injection

-> check if header cookie and csrf token if same -> then sever will check if both are same then it is a valid request but we can add header cookie by CRLF injection.

->change method or method override by using `_method=POST` but the main method is GET when server does not allow GET method or when cookies is in sameSite-> Lax

-> if the cookie is in strict then we can bypass that by same as portswigger labs -> 

-> if server validate cerf by using Referer header -> then try to remove Referer header completely if ok -> then add this in csrf poc -> `<meta name="referrer" content="no-referrer">`

-> sometimes when server check Referer header it only check if the referer header contains certain domain name we can bypass this by -> appending domain nema into this like -> atacker.com/?victim.domin.com

-> some websites uses first GET /getCsrf to get csrf token -> maybe that is cors misconfiguration and we can get the csrf token
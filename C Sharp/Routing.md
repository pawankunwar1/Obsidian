-> Routing is a process of matching incoming requests to a given action/function based on the URL and request method.
-> Routing -> URL + HTTP METHOD
-> Ex  Client request `Get http://localhost:3000/Home` in browser then Asp.net App give `index.html`. So for each route we defined a middleware, and that middleware function will executed for that particular route. We can define different middleware for same url but for different HTTP Methods.

->Pattern ->`https://example.com/{controller}/{action}/{id}` -> id is not compulsory.


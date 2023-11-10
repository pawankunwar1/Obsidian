Oauth 2.0 terminology:-

-> Resource Owner:- means user 
-> Resource Server:- There is a server which manages the users data. The server is called "Resource Server".
-> Client Application:- The application that want user data.
-> Authorization Server:- It is a server that gives permission to autorize like `accounts.google.com` by entering email and password.
-> Authorization grant:- It means it gives the grant to access the resources.
-> Redirect URI:- This is the uri where does client goes after getting resources like /myaccount
-> Access token:- authorization grant does many things but in higher level access token is the key that say what resource does i granted.



-->Here, user click in "connect with google" in example.com the the request is going to the authorization server where user enter gmail and password for authorization with that it also 
provide redirect Uri to authorization server and inback authorization server gives Response type: code , after that google server prompts allow for resources(yes or no) then after allowing it redirect to redirect URI, 
the client does not do many things with authorization code but the client ask authorization server hey i need access token and to get the access token it must provide the authorization code, authorization server validates the code and give   
token. Now the client can interact with resources server for data by using access token.
--> Firstly, what client is requested to access the resources based on that token is given . ex if client first want to access contacts but later want to access other information , the server doesnt give permission.


--> ATTACKS ON OAUTH 2.0
1) Token/Code Stealing
2) CSRF(missing `state` param)
3) Token Impersonation





--> `https://authorization-server.com/auth?response_type=code&client_id=CLIENT_ID&redirect_uri=REDIRECT_URI&scope=photos&state=1234zyx`
-> here, `response_type=code` - indicates that your server expects to receive an authorization code.
-> here `client_id` - indicates The Client ID you received when you first created the application.
-> here `redirect_uri` - indicates the URI to return the user to after authorization is complete.
-> here `scope` - one or more scope values indicating which parts of the users account you wish to access.
-> here `state` - A random string generated by your application, which you'll verify later.

Now, the users see the authorization prompt like `An application would like to conenct to your account(The app want to access you email) - Allow App acees? - Deny ALlow`

If the user click 'Allow', the service redirects the user back to your site with an authorization code.
`https://example.com/cb?code=AUTH_CODE_HERE&state=1234xyz`
-> `code` -> The server returns the authorization code in the query string
-> `state` -> The server returns the same site value that you passed
You should first compare this state value to ensure it matches the one you started with. You can typically store the state value in a cookie or session, and compare it when the user comes back. This helps ensure your redirection endpoint isn't able to be tricked into attempting to exchange arbitrary authorization codes.

-> Getting an Access Token:-
Your server exchanges the authorization code for an access token by making a POST requests to the authorization servers token endpoint:
`POST https://api.authorization-server.com/token`
`grant type=authorization_code&`
`code=Auth_Code_Here&`
`redirect_uri=REDIRECT_URI&`
`client_id=CLIENT_ID&`
`client_secret=CLIENT_SECRET`

-> grant_type=authorization_code - The grant type for this flow is authorization_code
-> code=AUTH_CODE_HERE - This is the code you received in the query string.
-> redirect_uri=REDIRECT_URI - Must be identical to the redirect URI provided int the original link.
-> client_id = CLIENT_ID - The client ID you received when you first created the application
-> client_secret=CLIENT_SECRET - SInce, this request is made from server-side code , the secret is included.

-> The server replies with an access token and expiration time:
     {
          "access_token" : "`RsT5OjbzRn430zqMLgV3Ia",
           "expires_in": 3600
    }
-> or if there was an error 
    {
        "error": "invalid_request"
    }








###############################3
SSO Bypass Techniques
->https://internal.org.com -> SSO
-> dig CNAME internal.org.com ->org.3rdparty.com
->gau-subs 3rdparty.com -> hey.3rdparty.com/authentication/register
-> https://internal.org.com/authentication/register -> 200 OK
here 3rd party endpoint also work in main sso domain.



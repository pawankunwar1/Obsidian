HTTP Parameter Pollution 
Tip 1:- When requesting a password reset link: 
           `email=victim@domain.com&youremail@doman.com`
            When resetting password: 
           `token={token}&email=youremail@domain.com&email=victim@domain.com`
 Tip 2:- While linking account to facebook, google. POST request looked like :oauth={token}&userid=myuserid&email=myemail. Change userid with victims userid and forward.
   Tip 3:- If you find your password reflected in response/source code don't report it yet Check if it is vulnerable to CORS or any IDOR to steal other user's passwords
   Tip 4:- Link your account to facebook/google and capture the request, if there is no CSRF here you can send the link to a victim to link your google to his account, then you log in using google

<mark style="background: #FF5582A6;">Tip 5:-</mark>
a) User A invites user B to his instancce where user B is his second email address
b) User A asks for password reset of user B
c) User B opnes the reset link and waits
d) User A edits User B's email to victim's email
e) Reset Password TOkens becomes valid for Victim.
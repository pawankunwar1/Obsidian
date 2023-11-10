1) Force Browsing :- try to access the next endpoint directly just you need to know the path of the next endpoint If this doesnt work , try to change the Referrer header as if you came from the 2FA page.
2) Response Manipulation :- first enter the correct code --> intercept response. now enter the wrong code --> intercept the response now change this response to correct one.
3) Status Code Manipulation:- status code 4XX for wrong OTP change it to 2XX (same as response manipulation)
4) Sharing unused tokens:- Check if you can get for your account a token and try to use to bypass the 2FA in a different account.
5) Lack of Rate Limit:- There is any limit in the amount of codes that you can try, so you just brute force it. Be careful with a possible "silent " rate-limit, always try several codes and then the real one to confirm the vulnerability. (or get one legit code from own account if server block code after 5 times non-legit code applies then try 4 random code + one own legit code + 4 random code + one own legit code)
6) Developers Check/Client side check:-  RIght click on submit button (continue or CheckOtp), Inspect element , sometimes there will be function that check otp client side in javascript. References --> [https://shahjerry33.medium.com/otp-bypass-developers-check-5786885d55c6](https://shahjerry33.medium.com/otp-bypass-developers-check-5786885d55c6)
7) Header base bypass:- `add X-Forwarded-For: 127.0.0.1 in request   If it did not work try :   X-Originating-IP   X-Forwarded-For   X-Remote-IP   X-Remote-Addr   X-Client-IP   X-Host   X-Forwared-Host` and many more from github
8) Password reset function:-
    In almost all web applications the **password reset function automatically logs the user into the application** after the reset procedure is completed. Check if a **mail **is sent with a **link **to **reset the password** and if you can **reuse** that **link **to reset the password as **many times as you want** (even if the victim changes his email address).
9) Reusing token:- Maybe you can reuse an already used token inside the account to authrnticate.
10) OTP codes leaked in the response:- Is the token leaked on a response from the web application? . Capture request after sending OTP and see this is leaking at response or not. Also, check burp history  after sending OTP if somewhere its leaking
11) CSRF/ Clickjacking :- Check if there is a CSRF or a Clickjacking vulnerability to disable the 2Fa.
12)  Password-Reset == disable 2FA
       a) Create an Account and Turn On 2FA
       b) Logout from the account.
       c) Now, Go to forgot Password_reset page
       d) Change your password
       e) Now try to log in
       f) If you are not asked to enter a 2FA code , You can report.
13) Information DIsclosure:-  If you notice some confidential information appear on the 2FA page that you didn't know previously (like the phone number), then this can be considered an information disclosure vulnerability
14) Email Verification Link:-  a) First create an account and server send email verification link then verify it and activate 2FA. Now open other browser try to login it ask 2FA code, but now paste the email verification link in the browser , it may sometimes redirect to dashboard bypassing 2FA.
15) Flow rate limit but no rate limit:- In this case there is a flow rate limit(you have to brute force it very slowely: 1 thread and some sleep before 2 tries) but no rate limit. So with enough time, you can be able to find the valid code
16) Previous sessions:- When the 2FA is enables, previous sessions created should be ended. This is because when a client has his accoutn compromised he could want to protect it by activating the 2FA, but if the previous sessions arent ended, this wont protect him.
17) APIs : - f you find that the 2FA is using an API located under a /v*/ directory (like "/v3/"), this probably means that there are older API endpoints that could be vulnerable to some kind of 2FA bypass.
18) Subdomains:- If you can find some "testing" subdomains with the login functionality, they could be using old versions that don't support 2FA (so it is directly bypassed) or those endpoints could support a vulnerable version of the 2FA.
19) Re-send code and reset the limit:- There is rate limit but when you "resend the code" the same code is sned and the rate limit is reset. Then, you can brute force the code while you resend it so the rate limit is never reached.
20) Lack of rate limit re-sending the code via SMS:- You won't be able to bypass the 2FA but you will be able to waste the company's money.
21) Improper access control to backup codes:- Backup code are generated immediately after 2FA is enabled and are available on a single request. After each subsequent or remain unchanged (static codes). If there are CORS misconfigurations/ XSS vulnerabilities and other bugs that allow you to pull backup codes from the response request of the backup code endpoint, then the attacker could steal the codes and bypass 2FA if the username and password are known.
22)  Remember me functionality:- a)Guessable cookie:-If the "remember me" functionality uses a new cookie with a guessable code , try to guess it. b) IP address :- If the "remember me" functionality is attached to your IP address, you can try to figure out the IP address of the victim and impersonate it using the X-Forwarded-For header.
23) Session Permission:- If the website use any cookie or boolean value to indicate that this user pass 2FA check then we can copy that cookie and paste in victim 2FA check bypass.
24) Lack of rate limit in the users account:- Sometimes you can configure the 2FA for some actions inside your accoutn(like change(mail,password). However even in cases where there is a rate limit when you tried to log in, there isn't any rate limit to protect actions inside the account.
25) Sometimes website create login cookie before completeing the 2FA process. So check for the flow.
26) Using simliar endpoints:- If you are attacking the `/api/v3/sign-up` endpoint try to perform bruteforce to `/Sing-up`, `/SignUp`, `/singup`...(if the website doesnt do URL normilazation). Also try appending to the original endpoint bytes like `%00, %0d%0a, %0d, %0a, %09, %0C, %20` (Signup%00, SIgnup%0d%0a)
27) Blank chars in code/params :- Try adding some blank byte like %00, %0d%0a, %0d, %0a, %09, %0C, %20 to the code and/or params. For example `code=1234%0a` or if you are requesting a code for an email and you only have 5 tries, use the 5 tries for `example@email.com`, then for `example@email.com%0a`, then for `example@email.com%0a%0a`, and continue...
28) Change other headers:- Try changing the user-agent, the cookies... anything that could be able to identify you.
29) Adding extra params to the path:- If the limit in in the path `/resetpwd`, try BFing that path, and once the rate limit is reached try `/resetpwd?someparam=1`
30) Login in your account before each attempt :- Maybe if you are login into your account before each attempt(or each set of X tries ), the rate limit is restarted. If you are attacking a login functionality , you can do this in burp using a Pitchfork attack in setting your credentials every X tries( and marking follow redirects)
31) Js FIle Analysis:- While triggering the 2FA Code Request, Analyze all the JS FIles that are referred in the Response to see if any JS file contain indormation that can help bypass 2FA code.
32) Bypass tip :- first capture the delete 2FA request in your account then login with victim credentials then website ask for 2FA , maybe request the capture 2FA request with victim cookie, should disable 2FA.
33) 13.Bypass 2FA with null or 000000  
          Enter the code 000000 or null to bypass 2FA protection.
34) Bypassing OTP in registration forms by repeating the form submission multiple times using repeater  
       Steps :-   
    1) Create an account with a non-existing phone number  
    2) Intercept the Request in BurpSuite  
    3) Send the request to the repeater and forward  
    4) Go to Repeater tab and change the non-existent phone number to your phone number  
    5) If you got an OTP to your phone, try using that OTP to register that non-existent number
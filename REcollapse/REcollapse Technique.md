1) Identify the regex pivot positions
   a) `starting` & `termination` positions
   b) `separator` positions
   c) `Normalization` positions
2) Fuzz positions with all possible bytes
3) Analyze the responses 


-> FUZZ  the starting and termination position  with all character from `%00 to %ff`-> `https://example.com/redirect?url=$1https://legit.example.com$2` where `$1 -> starting positions` `$2 -> termination position`

-> FUZZ the separator positions -> `https://example.com/redirect?url=https$1:$2/$3/$4legit$5.$6example$.$com`

-> FUZZ the normalization positions -> `https://example.com/redirect?url=https://L$1git.ex$2mple.c$3m` 



FUZZ in -> openredirect scenerio -> in email field -> user_name -> also for xss 


Uncovering Mysterious Bugs
1. Set your goal(e.x ATO)
2. Pick you target field(e.x email)
3. Identify all flows that consume it
4. For every endpoint: REcollapse
5. Analyze all response codes. Any successful respnse?
  a. Is the regex always the same in all endpoints? Usually not
  b. Pick a weird byte that went through
6) Go through all the flows from Step 3
  > Recovery, login, signup, OAuth, SSO, email change & confirmation(depends on target field)
  
Examples 
1-> Cache Deception -> here `https://redactes.com/wp-json/v1/user` have sensitive api_token. First we can try to add -> user.css, user.pdf, user.js for to cache 

-> Caching rules are usually regex-based
-> A static extension is not enough these days to perform web cache deception
-> We need to enforce the correct Content-Type in the response

-> SO we can fuzz in here like `https://redacted.com/wp-json/v1/user$.[extension]` from %00 to %ff and other encoding. -> here `https://redacted.com/wp-json/v1/users%23.pdf` gives OK.

2->In  OAuth and SAML -> normalization is often used in these flows -> here normilization is common to make the input consistent but when the Oauth parent like google, facebook application accepts one weired character that is not normalized in the first place but client application normalized later can cause account takeover.

3-> In Shopify -> when we signup in accounts.shopify.com with weired `i` character -> in case of sign up it signup as weired `i` character but during login it normalize weired `i` character and replaces with regular `i` character -> ATO

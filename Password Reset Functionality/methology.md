1) check if can change victim email or username while changing with our password token.
2) Password reset link not expiring 
3) No rate limiting on password reset
4) Denial Service when entering a long password -> Normally password have 8-12-24 or up to 48 digits, if there is no word limit while keeping a password we can consider it as a vulnerability. If register page have limiting password length maybe after forgot password page there is not limiting.
5) Password reset token leak via referer -> a) Request password reset to your email address b) Open on the password reset link c) Make sure you dont change the password there d) On Password Reset Page Click On Social Media Links Given Below And Capture the request using burp suite
6) Check if the referer header is a leaking password reset token
7) Double parameter aka HTTP parameter pollution -> email=victim@domain.com&email=hacker@gmail.com
8) Carbon Copy->email=victim@domain.com%0a%0dcc:hacker@gmail.com
9) Using sepators -> a) email = victim@domain.com,hacker@domain.com b) email=victim@domain.com%20hacker@domain.com  c) email = victim@domain.com|hacker@domain.com
10) No domain-> email = victim
11) No TLD(Top Level Doman) -> email = victim@domain
12) JSON table -> {"email:["victim@domain.com","hacker@domain.com]"}
13) Weak cryptographic issue a) Generated based timestamp b) Generated based on cryptography c) Generated base in userID d) Generated based on email user e) Generated based on first name and last name f) Generated based on the date of birth 
14) Host header attack
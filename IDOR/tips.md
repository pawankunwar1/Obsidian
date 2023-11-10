--> tool --> authorize or autorepeater

--> Parameters to look for IDOR
1) notificationID
2) couponID
3) consumer ID
4) advertiser ID
5) business ID
6) phone number
7) email address
8) last name
9) application ID
10) SSN (social security number)
11) premise ID
12) confirmation ID
13) reservation ID
14) ticket ID
15) policy ID
16) bank account number
17) profile ID
18) meter number
19) account number
20) user ID
21) document name or ID
22) loan / mortgage number
23) employee ID
24) VIN (vehicle ID)

--------------------------------------------------------
HOW TO FIND IDOR?
Method 1
1.Find endpoints with ID's in the request
2.Change the ID (to another account)
3.If its works its an IDOR

Method 2
1.Find endpoints that require admin permissions 
2.Login to an account that has a guest permissions
3.Grap the cookies of guest account and add, then requests to the admin endpoints
4.If its works its an IDOR

Case Study 
-> Create a task with USER A
-> Login with USER B
-> Create a task with USER B
-> Turn on interceptor
-> DELETE USERS B's task
-> Change the ID to User A's task in interceptor 
Impact:- Other users can delete tasks

Case Study 
-> Create 2 acounts: admin and guest
-> Use the admin account to create a poll
-> Change the visibility settings so people cannot see the poll
-> The guest account can still view the poll id via a request
Impact: Users can see hidden polls

Case Study 
-> Notice that the app has 2 internal APIs with different versions
-> Find an endpoint which exists on an earlier API v1(versions1
-> Use your knowledge of ther newer endpoint, on the other domain to poke the older endpoint
-> Find a bunch of IDORs
Impact: From knowing a sequential account id, a malicious user can use the API to view private info about an account

Case Study 
-> Users can message store and a store can reply add attach a file
-> No Protection on overwriting files though 
-> A second store can upload a document with a same name 
Impact: An attacker could overwrite a bunch of files for a store, assuming that they can guess the names.

Case Study(Low Priviliged user able to add new Geopgraphical settings to the Admin account)
-> Create a regular user account with no special permissions 
-> Poke at the API and find the setting modification endpoints 
-> Notice that you cannot view update geo settings 
-> However, you can make them via this API
Impact: Low level users can make settings changes to a high level user 


Tips 
1. APIs can be great to find IDORs 
-> It never hurts to do some recon on the API endpoints 
2.Sometimes validation might only be client side, so worth it do everything in burp
3.IDORs can appear in so many different kinds of web apps
4.The impact of an IDOR can range from low to critical 
5.Make sure you consider non-logged in users AND low-permission users.





#Tips
->If no ID's in the application-generated request, try adding one to the request.Append id, user_id, message_id, or object references to the URL query, or the POST body parameter, and see if it makes a difference to the applications behavior. For example,says this request displays your messages:
--> GET /api_v1/messages
Then maybe this request would dispaly another user's message instead:
--> GET /api_v1/messages?user_id=ANOTHER_USERS_ID


#KEEP AN EYE OUT FOR BLIND IDORS
Still, sometimes endpoints susceptible to IDOR don’t respond with the
leaked information directly. They might lead the application to leak infor-
mation elsewhere, instead: in export files, email, and maybe even in text
alerts. For example, imagine that this endpoint on example.com allows users
to email themselves a copy of a receipt:
POST /get_receipt
(POST request body)
receipt_id=3001
This request will send a copy of receipt 3001 to the registered email of
the current user. Now, what if you were to request a receipt that belongs to
another user, receipt 2983?
POST /get_receipt
(POST request body)
receipt_id=2983
While the HTTP response does not change, you may get a copy of
receipt 2983 in your email inbox! Often a malicious request can cause an
info leak sometime in the future. I once found an IDOR that led to an info
leak one month later, in a monthly report






######################################################################################
-->Broken Object Level Authorisation / BOLA --> accessing an object owned by another user 
--> Broken Function Level Authorisation --> Accessing an admin function when logged in as a regular user
--> Missing Access Control --> Accessing an object when logged out of an account
--> Cross - Tenant --> Accessing another tenants objects without being a member



#####################################################
-> if the id is large like id=1234567890 then bruteforce only last three or four digits.

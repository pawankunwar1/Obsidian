1) Send Group in sequence(single connection)
2) Send Group in sequence(separate connections)
3) Send Group in Parallel


1) Sending over a single connection :- If you select `Send group in sequence(single connection`, Repeater establishes a connection to the target, sends the requests from all of the tabs in the group and then closes the connection.
     Sending requests over a single connection enables you to test for potential client-side desync vectors. It also reduces the 'jitter' that occur when establishing TCP connections. This is useful for timing-based attacks that rely on being able to compare responses with very small differences in timings.

2) Sending over separate connections :- If you select `Send group in sequence(Separate connections)`, Repeater establishes a connection to the target, sends the request from the first tab, and then closes the connection. It repeats this process for all of ther other tabs in the order they are arranged in the group.   
     Sending requests over separate connections makes it easier to test for vulnerabilities that require a multi-step process.

Criteria to meet Send in Sequence:-
a) There must not be nay WebSOcket message tabs in the group 
b) There must not be any empty tabs in the group
c) All tabs must have the same target 
d) All tabs must use the same HTTP version(i.e the must either all use HTTP/1 or all use HTTP/2)


 3) Sending requests in parallel :- If you select **Send group in parallel**, Repeater sends the requests from all of the group's tabs at once.Repeater synchronizes parallel requests to ensure that they all arrive in full at the same time. It uses different synchronization techniques depending on the HTTP version used:
     - When sending over HTTP/1, Repeater uses last-byte synchronization. This is where multiple requests are sent over concurrent connections, but the last byte of each request in the group is withheld. After a short delay, these last bytes are sent down each connection simultaneously.
- When sending over HTTP/2+, Repeater sends the group using a single packet attack. This is where multiple requests are sent via a single TCP packet.
- When you select a tab containing a response to a parallel request, an indicator in the bottom-right corner displays the order in which that response was received within the group (for example, 1/3, 2/3).

Criteria to meet Send in Parallel:-
- All requests in the group must use the same host, port, and transport layer protocols.
- HTTP/1 keep-alive must not be enabled for the project.

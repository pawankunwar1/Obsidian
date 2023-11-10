#manyfacesofip


1) Dotted-decimal notation :- We are most familiar with the dotted-decimal notation, which has the format of `N.N.N.N`, where `N` can range from `0` to `255`. In this notation, `localhost` is the familiar `127.0.0.1
2) 0-optimized dotted-decimal notation:- The digitally correct format of 127.0.0.1 is actually 127.000.000.001. 127.0.0.1 is the zero suppressed form. <mark style="background: #FFF3A3A6;">Zero suppression </mark>is the exclusion of zeros from a number that don't have significance in the value of a number(left-padded zeros).  <mark style="background: #FFF3A3A6;">Zero compression</mark> is the exclusion of segments whose value sus up to zero. Using zero compression, the 0 value segments of an IP addresses can be ommitted. So, 127.0.0.1 becomes --> 127.1. Likewise 192.168.0.1 becomes 192.168.1. Because of zero suppression and zero compression , `127.0.00000000000000000000001` becomes `127.0.0.1`. But 000127.0.1 will not resolve to 127.0.0.1 . because 000127 will be read as octal 0127 which equals to 87 in decimal. so 000127.0.1 will resolve to 87.0.0.1
3) Octal notaion:- Each number of the dotted-decimal IP address can be represented in the octal format too. So in octal notation `127.0.0.1` is `0127.0.0.01` It's important to note that the leading `0` before the numbers are required for marking them as octal. And you can put as many `0`s before them. So, the following also refer to `127.0.0.1`: `
       `00000000177.000.0.00000001
       `0177.0.0.0000001
    `000177.0000.00000.01
      `` 0000177.000000000000000000.00000000000.00000000001
`00000000000000000000000000000000000000000000000000177.0.0.01`
 4) Hexadecimal notation:- "If something can be represented in octal, it probably can be represented in hexadecimal too." . So in hexadecimal notation `127.0.0.1` is: `0x7f.0x0.0x0.0x1`. The dots are optional if you preceed the concatenated hex values with a `0x`:- `0x7f000001` . And, you can left-pad the hex value with any amount of any random hex values. So, the following also refer to `127.0.0.1`:
      `0xDEADBEEF7f000001
      `0xBADF00D7f000001
     `0xDEADC0DE7f000001
     `0xBADC0DE7f000001
    `0xBAAAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa7f000001
5) Decimal notation a.k.a dword notation :- Dword is the non-dotted decimal representation of an IP address. In dword notation `127.0.0.1` is: `2130706433
6) Binary notation :- IP addresses can be represented in binary too. `127.0.0.1` in binary notation `01111111000000000000000000000001`. The binary notation is the true form of an IP address. It is the format understood and used by the lowest level networking components.
7) Mixed notation :- A different notation for one or more segments of the address? Just keep the left-most segment intact. Here are some examples: `00000000000000000000000000000000000000000000000000177.1
     `0x7f.1
     `127.0x1
      With three of the four segments represented the same in dec, oct, and hex, `127.0.0.1` doesn't give us much room to play. Let's see how `172.217.166.174` (google.com) may be represented in the decimal-octal-hexadecimal-dword mixed notation:
    `172.14263982
    `0254.0xd9a6ae
    `0xac.000000000000000000331.0246.174
  ` 0331.14263982
  
8) IPv6 format:- then we have IPv6. All of the following resolve to `::1`:
     `0000000000000:0000:0000:0000:0000:00000000000000:0000:1
     `0000:0000:0000:0000:0000:0000:0000:0001
     `0:0:0:0:0:0:0:1
     `0:0:0:0::0:0:1

9)  URL-encoded IP address:- URL-encoded IP addresses are accepted as valid IP addresses in most browsers and HTTP clients. So, the following refers to `http://127.0.0.1`: `http://%31%32%37%2E%30%2E%30%2E%31.` AND And the following refers to `http://[::1]`:
     `http://[%3A%3A%31]
 10) Using bubble text :- `http://ⓔⓧⓐⓜⓟⓛⓔ.ⓒⓞ`  :- this site can help --> https://capitalizemytitle.com/bubble-text-generator/





      



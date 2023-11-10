-> image retrival link like `?img=img1.png`

-> if there is waf -> find for origin ip

-> Look for input parameter: Form parameters, cookie value

-> Lang(website support several types language)

-> Are there request params which could be used for file-related operation

-> Are there unusual file extension?

-> Are there interesting variables name?


-> check allow function and see website send cookie and test for LFI

-> we can try differernt types HTTP methods if (not GET methods then POST methods)

-> ```
```php
<?PHP 
	include($_GET["lang"]);
?>
```
-> Null bytes technique is not working with above PHP 5.3.4 version -> like -> %00 and in Hex -> 0x00

-> Sometimes web app only filter when we give payload like this -> `../../../etc/passwd` but when we give -> `/DirectoryName/../../../../etc/passwd` -> bypasswd 

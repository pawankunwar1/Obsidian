-> Entities -> it is like variable  in XML . We can assign it a value and can use in different parts in XML document. This entities is defined in separate part of XML document called Document Type Definition(DTD). ex.
```
<?xml version="1.0"?>
<!DOCTYPE Person [
   <!ENTITY name "Pawan">
]>
<Person>
   <Name> &name; </Name>
   <Age> 90 </Age>
</Person>
```
Three Types of Entities -> 
1) General (which is above)
2) Parameter
3) Predefined

2) Parameter -> it is valid only inside DTD -> and only can refrence inside DTD
```
<!ENTITY % outer "<!ENTITY inner 'John'>">
```
3) Predefined ->
```
<hello> < </hello> -> the xml parser gives error because of special error
<hello> &#x3c; </hello> -> so we used this which is called predefined
```


```
<?xml version="1.0"?>
<!DOCTYPE XEE [
    <!ENTITY subscribe SYSTEM "secret.txt">
]>
<pwn>&subscribe;</pwn>
```
-> `SYSTEM` is the keyword that tells the XML parser -> Entity is the type external. Simply tell the XML parser to fetch external secret.txt file and store in subscribe entity. XML support any type of protocol like file, http, ftp so we can use in instead of secret.txt

XXE Types 
1) Inband
2) Error
3) Out of bound
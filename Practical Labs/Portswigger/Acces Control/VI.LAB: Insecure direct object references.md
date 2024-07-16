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



































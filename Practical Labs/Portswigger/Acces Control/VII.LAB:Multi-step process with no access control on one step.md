## Welcome, my friend. Today we will start the [12. access control lab](https://portswigger.net/web-security/access-control/lab-multi-step-process-with-no-access-control-on-one-step) in ```portswigger```     

# Explain this Scenario:


# Access control vulnerabilities in multi-step processes
### What are multi-step processes?

#### Many websites perform important functions in several sequential steps. This is common when:

1. You need to collect a variety of inputs or options.
2. The user needs to review and confirm the details before performing the operation.

### Practical example:

#### Suppose we have an administrative function to update user details. This process may include the following steps:

#### 1. Upload Form: Upload the form containing the specified user details.
#### 2. Submit Changes: Enter changes and submit the form.
#### 3. Review and confirm changes: Review and confirm changes before they are actually implemented.

### Where can vulnerabilities occur?

##### Sometimes a site may implement strict access control measures on some of these steps, but ignore others. Imagine a site that correctly applies access control measures to steps one and two, but not to step three. The site assumes that the user will reach the third step only if he has completed the first two steps, which are subject to appropriate control.

#### How can the vulnerability be exploited?

##### An attacker could exploit this vulnerability by directly bypassing the first two steps and submitting the request to the third step with the required parameters. Practical scenario:

#### Step 1: The user (or attacker) uploads the form containing the user's details. The site implements access control and verifies the user's authority to access this page.
#### Step Two: The user submits the changes. Again, the site verifies the user's permissions.
#### Step Three: The user reviews and confirms the changes. Here, if the site does not implement access control measures properly, an attacker can bypass the first two steps and directly access this step using the appropriate request.

### Example request:

```
https://insecure-website.com/admin/update-user?userId=123&newEmail=attacker@example.com&confirm=true
```

##### If the site does not verify the user's permissions in this step, an attacker can change the user's details without going through the first steps.

#### How can we protect against these vulnerabilities?

 #### Verifying user permissions at every step: The site must ensure that the user has the necessary permissions at every step of the process.
 #### Use secure session tokens: Use unique tokens for each step to ensure that the user has completed the previous steps correctly.
 #### Redirect the user: If direct access is attempted to a later step without completing the previous steps, the user must be redirected to the correct step









-----------

# Let'a play this lap:

![image](https://github.com/user-attachments/assets/6d4cfe39-2390-4b3f-b80e-1c6d0ec31fa2)


> [!TIP]
> Before we begin, my friend, I want you to have some patience, and it is also preferable to prepare your favorite drink, stay away from anything that distracts you, and enjoy this room. It is kind of long, but it is fun.

#### Let's log in with admin account using the following credentials: ```administrator:admin```

![image](https://github.com/user-attachments/assets/8164344d-8f57-43da-8290-31b78a152bf7)

#### Let's navigate the site and discover its content inside interesting path ```admin panel```,And do not forget, my friend, that I will also intercept requests so that I can find out what is happening on the front end and also on the back end. i will using ```burp suite``` tool.

![image](https://github.com/user-attachments/assets/b3377448-fd60-47ca-8a2e-077db5a69366)

#### intercepting:

![image](https://github.com/user-attachments/assets/87d7b83d-cba5-4f21-8a19-403f58be20cc)


### Well we navigate to ```/admin``` ,his job is to promote regular users to admin.



#### Now enter ```Upgrade user```

![image](https://github.com/user-attachments/assets/350084c7-72be-492c-9696-60c907392f9d)

#### intercepting:

![image](https://github.com/user-attachments/assets/d7c01b1e-7a7b-4fcc-9541-93b4c432cb71)

### Well we navigate to ```/admin-roles``` ,his job is to confirm this operation.

#### Now enter ```yes```

![image](https://github.com/user-attachments/assets/ab019400-a425-4609-a493-269072a0cc13)

#### intercepting:

![image](https://github.com/user-attachments/assets/d475b137-6743-4421-b91c-dcabd655d0e3)

### well done, We promote carlos to admin.

#### But unfortunately this is not our goal. Our goal is to do these functions, but from within the Normal account, such as ```Wiener```, and not from the Admin account

#### Now we want to try these functions and raise the privileges of our account, but not from within the admin account, but from our ```Wiener``` account.


#### It's simple. We will use those requests, but we will modify something simple. Do you know what it is, my friend?
##### Yes, it is what the ```cookie``` for our account thinks about and we send it to find out whether we will be able to increase our authority or not



#### First log in with wiener account and copy our cookie.

![image](https://github.com/user-attachments/assets/1da15388-0549-4101-8240-405fb79acc1f)

#### Great this is our cookie, Let's change instead of cookie of admin account.


![image](https://github.com/user-attachments/assets/e03d72ab-fb6b-42be-be86-a28e5d79815c)


### OOppsss unauthorized in ```/admin``` path, Let's check in other paths.

![image](https://github.com/user-attachments/assets/c5c712e8-d8ac-42a9-80e2-9bc36ea633a9)


### OOppsss unauthorized in ```/admin-roles``` path, Let's check in last path.

![image](https://github.com/user-attachments/assets/44b8063d-4f27-4e51-8fbd-3659be2caec0)


### WOW! the vulnerable is here, we can promote carlos to admin privilge.
#### But in this lab reqire promote Wiener not carlos.

#### change ```wiener``` instead of ```carlos```


![image](https://github.com/user-attachments/assets/b6b6fbbc-2b57-43af-a3bd-8d75d5e29028)


### go to wiener account :)

![image](https://github.com/user-attachments/assets/575c3df0-a1bb-4295-8d7c-6a97644375b4)



## Congratulations, friends❤️‍🔥

<p align="center">
<img src="https://github.com/user-attachments/assets/08933e17-6379-4928-b803-d6c9e653b128" >
</p>




















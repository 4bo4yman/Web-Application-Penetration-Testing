## Welcome, my friend. Today we will start the [13. access control lab](https://portswigger.net/web-security/access-control/lab-referer-based-access-control) in ```portswigger```

# Explain this Scenario:


# Access control based on Referer header

#### What is Referer Header?

##### The Referer header is part of the HTTP request data that the browser sends to the server. The Referer header tells the server which page the current request came from. For example, if you are browsing a particular page on a site and click on a link, the new page will receive a request with a Referer header pointing to the previous page you were on.

#### How is the Referer header used in access control?

##### Some sites rely on the Referer header to control access to some sensitive subpages. Let's understand this with a practical example:

#### Practical example:

##### Suppose we have an application that is used to control access to administrative pages. The administration home page ```/admin``` is strictly controlled. However, for subpages such as ```/admin/deleteUser```, the application relies only on examining the Referer header.

##### When a user submits a request to access ```/admin/deleteUser```, the application checks whether the Referer header contains the ```/admin``` home page URL. If found, the request is allowed.
#### How can this vulnerability be exploited?

##### An attacker can easily forge the Referer header. It can send a direct request to sensitive subpages such as ```/admin/deleteUser``` and include the Referer header required to be granted access.

#### Example request:

##### Suppose the attacker wants to delete a user from the application. It can send an HTTP request using tools like cURL or Postman and adds the Referer header to the request:

```
POST /admin/deleteUser HTTP/1.1
Host: insecure-website.com
Referer: https://insecure-website.com/admin
```

#### This way, it tricks the application into believing that the request came from the administration's home page, thus giving it unauthorized access to sensitive functionality.



# Let'a play this lap:

![image](https://github.com/user-attachments/assets/acb68183-439a-402e-a64f-b1d40ba112e6)


> [!TIP]
> Before we begin, my friend, I want you to have some patience, and it is also preferable to prepare your favorite drink, stay away from anything that distracts you, and enjoy this room. It is kind of long, but it is fun.

#### Let's log in with admin account using the following credentials: ```administrator:admin```

![image](https://github.com/user-attachments/assets/3eacf3ec-79aa-4d84-9f76-4f207272737d)


#### Let's navigate the site and discover its content inside interesting path ```admin panel```,And do not forget, my friend, that I will also intercept requests so that I can find out what is happening on the front end and also on the back end. i will using ```burp suite``` tool.

![image](https://github.com/user-attachments/assets/33f6aa1c-1fc5-4087-bc19-4e35028b6fd1)

### Well we navigate to ```/admin``` ,his job is to promote regular users to admin.

#### Now enter ```Upgrade user```

![image](https://github.com/user-attachments/assets/44c12124-af25-4bc0-b53a-8dffbe64e9f8)


#### intercepting:

![image](https://github.com/user-attachments/assets/737a3ede-4302-42d7-919e-b752a29b7990)


### well done, We promote carlos to admin.

#### But unfortunately this is not our goal. Our goal is to do these functions, but from within the Normal account, such as ```Wiener```, and not from the Admin account

#### Now we want to try these functions and raise the privileges of our account, but not from within the admin account, but from our ```Wiener``` account.


#### It's simple. We will use those requests, but we will modify something simple. Do you know what it is, my friend?
##### Yes, it is what the ```cookie``` for our account thinks about and we send it to find out whether we will be able to increase our authority or not



#### First log in with wiener account and copy our cookie.

![image](https://github.com/user-attachments/assets/32440f04-bd33-4335-a2df-aaa212684a4d)

#### Great this is our cookie, Let's change instead of cookie of admin account.



![image](https://github.com/user-attachments/assets/1edcf70b-b392-42c9-8025-c89dea08a511)



### WOW! the vulnerable is here, we can promote wiener to admin privilge.

### go to wiener account :)

![image](https://github.com/user-attachments/assets/8ff38b63-f273-4e46-a77d-27bf388de19e)


## Congratulations, friends❤️‍🔥

<p align="center">
<img src="https://github.com/user-attachments/assets/a26fb719-f806-4f5e-8154-cec3df3161fd" >
</p>



#### Good bye, my friend.I hope you enjoyed these interesting Labs with us, and I ask you, my friend, to solve these Labs yourself. Good luck to you, my dear friend.



















































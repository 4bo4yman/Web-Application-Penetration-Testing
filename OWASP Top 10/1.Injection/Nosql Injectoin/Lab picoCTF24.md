<h1>$${\color{blue}Nosql}\space {\color{blue}Injection}\space {\color{blue}picoCTF24} $$</h1>


*****

#### MongoDB

Much like MySQL, MariaDB, or PostgresSQL, MongoDB is another database where you can store data in an ordered way. MongoDB allows you to retrieve subsets of data in a quick and structured form. If you are familiar with relational databases, you can assume MongoDB works similarly to any other database. The major exception is that the information isn't stored on tables but rather in documents. For [more information](https://www.mongodb.com/docs/manual/)


<br>

#### How to inject NoSQL

When looking at how NoSQL filters are built, bypassing them to inject any payload might look impossible, as they rely on creating a structured array. Unlike SQL injection, where queries were normally built by simple string concatenation, NoSQL queries require nested associative arrays. From an attacker's point of view, this means that to inject NoSQL, one must be able to inject arrays into the application.

Luckily for us, many server-side programming languages allow passing array variables by using a special syntax on the query string of an HTTP Request. For [more information](https://learn.snyk.io/lesson/nosql-injection-attack/)


<br>

***let's go*** to website and walking through it , we try login with ```"admin:admin"``` :

<p align="center">
<img src="https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/95a00cd9-f489-48bc-9923-3003777430fe">
</p>

Invalid! I was really expecting that ;)

Now,  We will doing The First step is enumeration and walking on site and recover the hidden Directory, use ```gobuster``` tool to help us in this task:


<p align="center">
<img src="https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/495c2f1b-3867-4450-9134-bc78363cb2f5">
</p>

Now, we know that exist ```"/admin"``` directory only.

Let's go to this directory for looking it:

<p align="center">
<img src="https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/e50005e1-3d6d-40b9-a972-32dc6e7667fb" >
</p>

Ummm, We didn't get anything important here.

Go back to the ```login``` page, Use ```burp``` to repeater the request:

<p align="center">
<img src="https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/ce0c9722-1066-40a5-9852-dd0376345cb2" >
</p>


***Now, start the playing ;***

We need to inject Nosql in burp and We will notice what will happen after injecting the payload into the application.
if you search about payload for Nosql injection it's [HERE](https://book.hacktricks.xyz/pentesting-web/nosql-injection)

example for payload:

```
{"username": {"$ne": "foo"}, "password": {"$ne": "bar"} }
```

***BUT*** in our case we will get ```\``` before ```"```  So we can deceive the web server and show it that it is not a payload and that it is plain text , ```This is the most important point in the lab```.

Our payload will be as follows:

```
{"username": {\"$ne\": \"foo\"}, "password": {\"$ne\": \"bar\"} }
```

Let's see how use this payload in ```burp``` tool:


<p align="center">
<img src="https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/224325f1-0c7e-4d66-9539-f51e206da8a3" >
</p>

Lastly, We hacked login page by ```Nosql Injection``` ;)

<br>

******
if this content liked you, follow me [Here](https://github.com/4bo4yman) ;) :tada:
*****



















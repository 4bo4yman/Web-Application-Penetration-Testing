## Welcome, my friend. Today we will start the [10. XSS lab](https://portswigger.net/web-security/cross-site-scripting/dom-based/lab-dom-xss-stored) in ```portswigger```
### Let's play this lab:

![image](https://github.com/user-attachments/assets/786b4d33-d218-4f1c-836b-93e0d3cb6684)

#### First, we navigate inside the browser

![image](https://github.com/user-attachments/assets/1f6a442d-9b91-46d3-a813-4e8e841a6fda)

### Let's enter ```<><h1>hi</h1><h5>0xT0R</h5>``` in **Comment**:

![image](https://github.com/user-attachments/assets/c82e1006-2256-4448-be56-e48ee0c3792c)


### Here there html injection, Let's enter malicios code to discover XSS vulnerability:

```
<><img src='x' onerror=alert(404)>
```

![image](https://github.com/user-attachments/assets/8997273f-988d-4a26-9a41-5a36e88fe953)


![image](https://github.com/user-attachments/assets/e5e24ce3-5b0a-4bd6-9202-498c14db5e75)


![image](https://github.com/user-attachments/assets/91120845-c0bc-4790-a15c-962a712c62a5)


-------

### Done! Congratulations, friends❤️‍🔥


<p align="center">
<img src="https://github.com/user-attachments/assets/005cac22-a8a2-4737-a170-ffc300cd2a7c" >
</p>
















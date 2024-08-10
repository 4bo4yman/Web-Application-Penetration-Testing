## Welcome, my friend. Today we will start the [20. XSS lab](https://portswigger.net/web-security/cross-site-scripting/contexts/lab-javascript-string-single-quote-backslash-escaped) in ```portswigger```
### Let's play this lab:

![image](https://github.com/user-attachments/assets/0bab8d82-ea55-4588-86da-c0363acc13f9)

#### First, we navigate inside the browser

![image](https://github.com/user-attachments/assets/b32ec8c2-cb22-4cf4-a402-9184dedfc687)

### Let's search for ```hi```:

![image](https://github.com/user-attachments/assets/d32ce9de-ff09-406e-bf6b-8436168661a3)


### Go to ```inspect``` and search for ```hi```

![image](https://github.com/user-attachments/assets/4a1edac3-74cd-4c7c-a34f-4b0462958dbd)

Ok, We exist from ```script tag``` and inject html code such as:

```
</script><h5>hi</h5>
```

![image](https://github.com/user-attachments/assets/3f65d2a5-abc6-46cf-8855-b1ee5311dbce)


Ok. Here print ```hi``` in browser. Now enter malicios code to discover XSS vulnerability:

```
</script><img src='mohamed' onerror=alert(404)>
```

![image](https://github.com/user-attachments/assets/4f426832-48a2-424b-97d1-621940791832)


![image](https://github.com/user-attachments/assets/bb8b2c91-2d99-4715-b40d-b61760634d4a)


-------

### Done! Congratulations, friends❤️‍🔥


<p align="center">
<img src="https://github.com/user-attachments/assets/15a03813-a959-4628-9018-708548137ba0" >
</p>

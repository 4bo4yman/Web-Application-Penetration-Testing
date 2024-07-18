## What is a URL shortener?

##### URL shortening is a technique used to make long URLs much shorter. This is achieved through HTTP redirection, where a short domain name redirects users to a web page containing a long URL.

#### How does a URL shortener work?

###### When the user clicks on a shortened URL, an HTTP redirect is executed that takes the user from the shortened URL to the final destination. This is usually done using the HTTP 301 status code, which indicates "Moved Permanently".

#### Example of URL shortening

#### Let's take an example of a long URL:

```
http://www.example.com/this/is/a/very/long/url/that/we/want/to/shorten
```

It can be shortened using a URL shortening service like bit.ly to:


```
http://bit.ly/abc123
```

> Although a URL shortener is useful, it can be used for malicious purposes. For example, attackers may use shortened links to hide malicious URLs. Therefore, you should be careful when clicking on unknown shortened links.


--------

##  Google URL Shortener

![image](https://github.com/user-attachments/assets/d09a0e2a-643c-4e58-a509-ca56fcaf63e0)

----

## Link checking services:
 
#### Some websites and apps provide tools to scan shortened links and show you the final destination. You can enter the short link in these tools and get a preview.

### Example of a service that displays a preview

#### Let's say there is a shortened link using the bit.ly service:

```
http://bit.ly/abc123
```


User can add the word ```+``` at the end of the link to get a preview:

```
http://bit.ly/abc123+
```

> When this link is visited, a page will be displayed containing information about the final destination of the shortened link, which helps the user make an informed decision on whether or not they should click on the link.

<br>

## Benefits of previewing shortened links

 #### 1. Increased security: Link preview helps users avoid malicious links and reduce the risk of phishing.
#### 2. Increased trust: Users feel more comfortable clicking on shortened links that they already know their destination.
#### 3. Improve user experience: Previewing links makes it easier for users to know if they want to visit the final destination of the link.

--------

## Illustrative scenario

#### Scenario: Use the preview feature to check links

##### Let's say a user receives an email containing the following short link:

```
http://bit.ly/secure-login
```

### Before clicking on the link, the user can add ```+``` at the end to get a preview:

```
http://bit.ly/secure-login+
```

### When he visits this link, he can see that the final destination is a suspicious site:

```
http://phishingsite.com/login
```


![image](https://github.com/user-attachments/assets/c91b18b3-cb56-4dac-9abf-f201c2efaff4)

We use websites like [VirusTotal](https://www.virustotal.com/gui/home/upload) to analysis any links.


<br>

-------------------

### Other shortening services implement their technique to show the "preview" or some information about the shortened link.



##How to preview shortened links using different services

### 1. Tinyurl.com

##### Preview method: via subdomain

##### How to use: You can use the ```preview subdomain``` to get a preview of the shortened link.
 
 ### Example:
#### Short link: ```http://tinyurl.com/ph7xh4m```
#### Preview link: ```http://preview.tinyurl.com/ph7xh4m```

##### When you visit the preview link, you will be able to see the final destination of the shortened link.



<br>
<br>

### 2. Tiny.cc

#### Preview method: Using footer ```(~)```

 #### How to use: You can add the footer ~ to the end of the shortened link to get a preview.
### Example:
#### Short link: ```http://tiny.cc/hack_me```
#### Preview link: ```http://tiny.cc/hack_me~```

##### When you visit the preview link, you will be able to see the final destination of the shortened link.

<br>
<br>

#### There are also services that do not provide this feature, such as ```t.co``` used by Twitter. For this kind of service, online solutions like the following exist:

#### 1. [Tools Void](https://www.toolsvoid.com/unshorten-url/)

---------------

### You can have the same result resolving the ```URLs 'manually’```. For example, using ```cURL``` and reading the response headers:

![image](https://github.com/user-attachments/assets/da55cd03-a023-4918-a8a4-ff233168fd1a)

















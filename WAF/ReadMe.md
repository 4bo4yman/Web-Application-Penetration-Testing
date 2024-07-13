#### A WAF or web application firewall helps protect web applications by filtering and monitoring HTTP traffic between a web application and the Internet. It typically protects web applications from attacks such as cross-site forgery, cross-site-scripting (XSS), file inclusion, and SQL injection, among others.


![image](https://github.com/user-attachments/assets/c9424e6d-23f8-463b-8f00-a15cf976dbba)


#### Within the WAF there are two types of filtration:
**1. Whitelisting**

**2. Blacklisting**
   
- Whitelisting only allows the rules mentioned in the list
- Blacklisting allows everything except the rules mentioned in the list

The best solution to protect the web is whitelisting, but its big problem is that it reports false alarms, meaning it reports that a file contains a virus, and it is a safe file.
That's why they mostly use blacklisting

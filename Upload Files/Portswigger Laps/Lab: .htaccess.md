### Lab: Web shell upload via extension blacklist bypass

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/c1f5a2b5-6d54-483b-b0cb-8092e4d3f627)


Let's Go to web page and upload our crazy file.

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/47fb48b0-bda5-42c8-a971-2d1be15d6000)


Attempt to upload this script as your avatar. The response indicates that ***you are not allowed to upload files with a ```.php``` extension***.
 
In Burp's proxy history, find the ```POST /my-account/avatar``` request that was used to submit the file upload. In the response, notice that the headers reveal that you're talking to an ```Apache server```. Send this request to Burp Repeater. 


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/2ed1472c-45e9-44a1-a1e2-b3c19a554ed4)


In Burp Repeater, go to the tab for the POST /my-account/avatar request and find the part of the body that relates to your PHP file. Make the following changes:

  1. Change the value of the ```filename``` parameter to ```.htaccess```.
  2. Change the value of the ```Content-Type``` header to ```text/plain```.
  3. Replace the contents of the file (your PHP payload) with the following Apache directive:

  ```
  AddType application/x-httpd-php .abc
  ```

  This maps an arbitrary extension (```.abc```) to the executable MIME type ```application/x-httpd-php```. As the server uses the ```mod_php``` module, it knows how to handle this already.


![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/6a79656e-fb8b-403c-a7b2-a80b9bf14be4)


## Then:

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/e8acb21b-cca8-413d-91ce-388f5fa279c1)


Change the value of the filename parameter from ```uplaod.php``` to ```upload.aboayman```. Send the request again and notice that the file was uploaded successfully.
Switch to the other Repeater tab containing the GET ```/files/avatars/upload.aboayman``` request. In the path, replace the name of your image file with ```upload.aboayman``` and send the request. Observe that Carlos's secret was returned in the response. Thanks to our malicious .htaccess file, the .l33t file was executed as if it were a .php file.
Submit the secret to solve the lab. 

## Then lastly:

![image](https://github.com/4bo4yman/Web-Application-Penetration-Testing/assets/156849852/18ea0a69-eaa9-43b3-8758-d53a0b58e7b4)


# Nice we get the secret!

















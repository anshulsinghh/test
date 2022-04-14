# Team Members:
Anshul Singh
Zane Calini

# Grader Credentials for Server Login:
ssh: `grader@zaneanshul.tech`

pass: `Man#2008`

# Website URL:
zaneanshul.tech
To login to the website, credentials are:
user: anshul
pass: Man#2008

# Github Auto Deploy Setup:
On the server, we initialized a bare repository and a cloned repository of the github repo. As per the tutorial, the bare repository handles code pushes and checks them out into the cloned version of the github repo. The files are placed in the /var/www/html folder, which we symlinked to our actual website folder - which is /var/www/zaneanshul.tech/public_html. That is how we were able to update our website through remote pushes, which we set up on our local machine to push to prod main.

# HTML File Changes after Compression:
After enabling compression, in the response headers it shows that the Content-Endcoding is gzip.

# Removing Server Header:
We removed the server header using the libapache2-mod-security2 package. It allowed us to add a simple line to our apache config file to change the server signature:
```
<FfModule mod_security2.c>
SecServerSignature "CSE135 Server"
</IfModule>
```
We then restarted the server to update these new settings.

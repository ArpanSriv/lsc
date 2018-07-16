# Linux Server Configuration

This project is a part of the Udacity's Web Developer Nanodegree II. It involves configuring a Linux Web Server to serve a Flask Application using Mod_wsgi and Apache.

## Details of the Web Server
- IP Address : 13.232.29.223
- Public URL : http://ec2-13-232-29-223.ap-south-1.compute.amazonaws.com/catalog
- SSH Port : 2200

### Instructions to run
Run http://ec2-13-232-29-223.ap-south-1.compute.amazonaws.com/catalog to run the Item Catalog App.

### Instructions to SSH (From Linux)
1. Create a folder in your home folder by issuing the command `mkdir .ssh`
2. Create a new file using `nano id_rsa` and paste in the content of the key file provided using Ctrl + Shift + v.
3. Issue the following commands for the required security changes:
  `chmod 700 .ssh` and `chmod 600 .ssh/id_rsa`.
3. To connect to the server issue the following command in your local terminal (assuming the private key was stored in the file _.ssh/id_rsa_).
`ssh grader@13.232.29.223 -p 2200 -i .ssh/id_rsa`

### Summary of Changes Made

1. Made a new Ubuntu Server instance on Amazon Lightsail.
2. Made a user account *grader*  and gave _grader_ the sudo permissions.
3. Updated all packages.
4. Changed the SSH Port from 22 to 2200.
5. Removed the ability to login as root on the remote machine.
6. Created a SSH Key and authorized it to be used on the Remote Machine. This enabled the ability to login as _grader_ using key pair.
7. Configured the UFW Firewall according to the specifications provided.
8. Configured the timezone to UTC.
9. Installed and configured Apache and Mod WSGI to serve an application.
10. Cloned the Item Catalog Project and configured it to run on MOD WSGI + Apache Server.
11. Made .git inaccessible.
12. Configured PostgreSQL and app.py such that it connects to a new PSQL DB and not a SQLITE DB.
13. Configured Google API to serve the application at the public URL.

### List of Applications Installed
1. finger (To check the new user `grader`)
2. apache2 (Needed to serve a web application on the server)
3. libapache2-mod-wsgi (Needed to serve a python application on the Apache2 Server)
4. virtualenv (Installed with python-pip, needed for keeping a separate environment for this python project)
5. httplib2 (Helper library, required by the Python App)
6. requests (Helper library, required by the Python App)
7. sqlalchemy (Helper library, required by the Python App)
8. psycopg2 (Needed to connect to a postrgres database from python)

### References
https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps

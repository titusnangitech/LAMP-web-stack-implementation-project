


# STEP 01 - Created and connected to an EC2 instance in the us-east-1 region

![ec2 pic](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/c2cc67f8-31d6-4623-a196-23042e51a6d0)

- **Selected the us-east-1 region and launched a new EC2 instance of t2.micro family with Ubuntu Server 20.04 LTS (HVM) launch EC2**
  

![created an ec2 with an ami of ubuntu](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/94e8c5b3-0d2b-4c37-9782-4eedc5328b3d)


- **created an ec2 key pair and choose the t2 micro**
  
  
![choose the t2 micro type](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/046148d2-ab8b-42f9-8a02-f3135fda948f)


- **created a security group and made changes to the inbound rules**
  
  
![new sg with new inboud rules](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/71bdcce5-497a-4414-947b-831b1f0b9fe0)

- **security group has been created successfully**
  
  
![selected the sg that i created above](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/e4fe27a7-de03-45b5-91d9-4001f6473643)


- **the ec2 instance been successifully created and running**

![ec2 is a success](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/a43cc32b-cd97-4e2f-8bf3-6067e6694bf3)


- **populated Mobaxterm with ec2 public IP address, username and key pair details to connect to the EC2 instance**

  
![mobaxterm populated with details](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/f35b59f3-52d2-4720-9146-23dc0aee0864)



- **Switch from ubuntu user to root user**

  ```
  sudo -i
  ```
  

 ![switch to root with thesudo command](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/fb3e0696-c8dd-463d-955e-e791864e2fe3)
 
 
 - **connected successfully into the EC2 instance using Mobaxterm**

   
![connected into ubuntu](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/f1f8bc9e-653c-401b-a4f7-4892cab8c7b1)

# STEP 02 - Installing Apache web server and Updating the firewall

- **Install Apache using Ubuntu’s package manager ‘apt’**

- **first update a list of packages in the apt package manager**
```
apt update
 ```

![run apt update](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/abbcd97a-0f79-431a-8e6d-8d88d75ae57b)


- **run apache2 package installation**
```
apt install apache2
```

![install apache](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/04d52075-a25e-4aff-9145-44ba34c6bf3d)

- **To verify that apache2 is running as a Service in our OS, enter the following command**
```
systemctl status apache2
```

![verify that apche is running](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/ef385ec3-312d-4d54-b169-c96bcbe5d491)

- **server is running and can be accessed locally using both localhost and IP address**
```
curl http://localhost:80
or
 curl http://127.0.0.1:80
```

![test using curl local host](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/7a56724d-e506-4122-aac4-ef32c957264c)

** **

![curl using ip address](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/c92e0469-8a3a-447b-b97f-37342707ad8b)


- **testing how Apache HTTP server can respond to requests from the Internet. Opening a web browser of my choice and to access following url**
```
http://<Public-IP-Address>:80
```


- **I can see the Apache Ubuntu Default Page displaying which means my web server is now correctly installed and accessible through the firewall.**

![apache displayed](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/e44cd379-5ba7-4951-aa86-b7227327b53f)

# STEP 03 - Installing MySql

```
#I used ‘apt’ to acquire and install mysql software. When prompted, I confirmed installation by typing Y, and then ENTER
apt install mysql-server
```

![install mysql server](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/a6bdf9b8-b075-4f1a-b322-ab48feb0c588)

- **When installation finished, i logged in to the MySQL console by typing:**
```
mysql
```

![connecting to mysql](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/3e996ca9-37c8-4e5a-9e4f-ac1b9b2063ae)

- **This will connect to the MySQL server as the administrative database user root, which is inferred by the use of sudo when running this command. You should see output like this:**


![connecting to mysql](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/ed88c8b0-e07c-4cfa-984e-c10ac2c6324e)

- **set a password for the root user, using mysql_native_password as default authentication method. We’re defining this user’s password as PassWord.1**

```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';
```

![password lock in](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/8eba3d4b-98b8-40cb-9342-d16f78880b72)

- **Exit the MySQL shell with:**
```
mysql> exit
```


![exit mysql](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/bfeab62e-4174-4991-86ee-f9febbc1bdd7)


- **Start the interactive script by running:**

```
 mysql_secure_installation
```

![mysecure installation](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/70089ea2-b4e3-4547-adab-d840555241ee)

# STEP 04 - Installing PHP 

- **I have Apache installed to serve my content and MySQL installed to store and manage my data. PHP is the component of my setup that will process code to display dynamic content to the end user. In addition to the php package, i’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. I’ll also need libapache2-mod-php to enable Apache to handle PHP files. Core PHP packages will automatically be installed as dependencies**

- **To install these 3 packages at once, will run:**

```
apt install php libapache2-mod-php php-mysql
```

![install PHP component](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/3278cc01-2f70-4f60-ab57-e9d9c1d839cd)


- **Once the installation is finished, i ran the following command to confirm my PHP version:**
```
php -v
```
![php version](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/ef834a31-6dd3-4ca6-8934-fb2e4481f5d4)

# STEP 05 - Creating a Virtual Hosts for my website using Apache

-**Apache on Ubuntu 20.04 has one server block enabled by default that is configured to serve documents from the /var/www/html directory. We will leave this configuration as is and will add our own directory next next to the default one.

Create the directory for projectlamp using ‘mkdir’ command as follows:**

```
mkdir /var/www/projectlamp
```

- **Next, assign ownership of the directory with your current system user:**
  
```
chown -R $USER:$USER /var/www/projectlamp
```

- **Then, create and open a new configuration file in Apache’s sites-available directory using your preferred command-line editor. Here, we’ll be using vi or vim (They are the same by the way):**

```
vi /etc/apache2/sites-available/projectlamp.conf
```

- **This will create a new blank file. Paste in the following bare-bones configuration by hitting on i on the keyboard to enter the insert mode, and paste the text:**

```
<VirtualHost *:80>
    ServerName projectlamp
    ServerAlias www.projectlamp 
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/projectlamp
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

- **You can use the ls command to show the new file in the sites-available directory**

```
ls /etc/apache2/sites-available
```

- **You will see something like this;**

```
000-default.conf  default-ssl.conf  projectlamp.conf
```
- **You can now use a2ensite command to enable the new virtual host:**

```
a2ensite projectlamp
```

- **You might want to disable the default website that comes installed with Apache. This is required if you’re not using a custom domain name, because in this case Apache’s default configuration would overwrite your virtual host. To disable Apache’s default website use a2dissite command , type**

```
a2dissite 000-default
```

-**To make sure your configuration file doesn’t contain syntax errors, run:**

```
apache2ctl configtest
```

-**Finally, reload Apache so these changes take effect:**

```
systemctl reload apache2
```

-**Your new website is now active, but the web root /var/www/projectlamp is still empty. Create an index.html file in that location so that we can test that the virtual host works as expected**

```
echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) '54.88.16.160' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html
```

-**Now go to your browser and try to open your website URL using IP address.If you see the text from ‘echo’ command you wrote to index.html file, then it means your Apache virtual host is working as expected.**

```
http://54.88.16.160:80
```

![step 5](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/b157d42c-0880-499c-ab48-bb6f191453d0)

# STEP 06 Enable PHP on website

-**With the default DirectoryIndex settings on Apache, a file named index.html will always take precedence over an index.php file. This is useful for setting up maintenance pages in PHP applications, by creating a temporary index.html file containing an informative message to visitors. Because this page will take precedence over the index.php page, it will then become the landing page for the application. Once maintenance is over, the index.html is renamed or removed from the document root, bringing back the regular application page.

In case you want to change this behavior, you’ll need to edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DirectoryIndex directive:**

```
vim /etc/apache2/mods-enabled/dir.conf
```

```
<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>
```

-**After saving and closing the file, you will need to reload Apache so the changes take effect:**

```
systemctl reload apache2
```

-**Finally, we will create a PHP script to test that PHP is correctly installed and configured on your server.

Now that you have a custom location to host your website’s files and folders, we’ll create a PHP test script to confirm that Apache is able to handle and process requests for PHP files.

Create a new file named index.php inside your custom web root folder:**

```
vim /var/www/projectlamp/index.php
```


-**This will open a blank file. Add the following text, which is valid PHP code, inside the file:**

```
<?php
phpinfo();
```
![last commands](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/7f52b60c-7fc2-49d4-ba48-da89b8304beb)

-**When you are finished, save and close the file, refresh the page and you will see a page similar to this:**

![correct php server display](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/78cfb033-c42d-4491-a40a-671df5d1a58d)












  



  





  

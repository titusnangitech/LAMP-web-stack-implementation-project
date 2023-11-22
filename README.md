


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

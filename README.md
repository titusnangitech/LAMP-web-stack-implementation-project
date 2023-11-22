


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


- **connected successfully into the EC2 instance using Mobaxterm**

  
![connected into ubuntu](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/f1f8bc9e-653c-401b-a4f7-4892cab8c7b1)

# STEP 02 - Installing Apache web server and Updating the firewall

- **Install Apache using Ubuntu’s package manager ‘apt’**

```
#first update a list of packages in package manager
sudo apt update
 ```

![run apt update](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/abbcd97a-0f79-431a-8e6d-8d88d75ae57b)


```
#run apache2 package installation
sudo apt install apache2
```

![install apache](https://github.com/titusnangitech/LAMP-web-stack-implementation-project/assets/128609800/04d52075-a25e-4aff-9145-44ba34c6bf3d)

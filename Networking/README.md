## Continuation of week 2:

[Cloud networking article](https://pattern-tortoise-b8c.notion.site/Cloud-Networking-3762e96211534350b25d8158b5d8a111)

![Assignment](./images/assignment.png)

### Task 1

- Create a Vpc on AWS

- create 6 subnets 3 private 3 public three availability zones

[Helpful video](https://youtu.be/ApGz8tpNLgo)

Execution:

- Log into the AWS console

- On the search bar type VPC

![vpc](./images/vpc-searchbar.png)

- Click into `Your VPCs`
![yourvpc](./images/your-vpc.png) 

Note that there is always a default VPC and subnets in every region in your AWS account.
- Create Vpc
![create vpc](./images/create-vpc1.png)

![create vpc](./images/create-vpc2.png)

![create vpc](./images/create-vpc3.png)

![view vpc](./images/view-pvc.png)

This did not work for my overall configuration. so i created another vpc and clicked NAT GATEWAY was enabled
![vpc](./images/natgateway%20for%20config.png) (Adding this while configuring takes care of all the configurations for a NAT-Gateway)

![view subnet](./images/subnets-6.png)

![vpc](./images/vpc-created.png)

### Task 2a:

[Refrence-1](https://cloudiofy.com/how-to-connect-ec2-instance-in-a-private-subnet/)

[Reference-2](https://youtu.be/hO036v4NvQI)

- Create Linux instances in  the private subnets.

-  Allow private subnet to download from internet ie set up Nat gateway for private subnet

Execution: Launch public webserver

Launch EC2 instance
- Search for Ec2 on the search bar

![launch](./images/ec2-dashboard.png)

- Choose a name for webserver. Select Ami (Amazon linux as instructed)

![launch](./images/launch-instance1.png)

- Choose  T2 micro because of free tier

![launch](./images/launch-instance2.png)

- Create or Select a keypair

![launch](./images/launch-instance3keypair.png)

- Edit network Settings

- Choose the newly created vpc/subnet 

![launch](./images/launch-instance4.png)

- Security group
![security](./images/security-groupsprivate.png)

- Launch instance

![launch](./images/launch-instance6.png)

Tried to connect to the instance and got this error.(I had to launch a fresh instance with a new key ***my-key1***. ***My-key*** key pair was mistakenly deleted)

![error](./images/cannot-connect.png)

### Task 2b:

Create another webserver in the public subnet.

Follow same instructions as that of the private server but this time choose public subnets and security groups inbound rule should look like this.
![security](./images/security-groups.png)

- Connect to the Public server in this public server we are going to connect to the private subnet server.

![connect](./images/connect1.png)

![connect](./images/connect2.png)



### Task 3:
Create an instance in the public subnet with different operating system
- Linux
- Windows
- Mac Os

### Task3a:
Linux- Instance (I am going to launch and also set up website)

Launch  EC2 in the public subnet/Vpc
![launch](./images/linux-webserver1.png)

![linux](./images/linux-webserver2.png)

![linux](./images/linux-webserver3.png)

![linux](./images/linux-webserver4.png)

- Allow HTTP and HTTPS in inbound rule to connect to server

![linux](./images/linux-webserver5.png)

- Connect to the instance

```
ssh -i "my-key1.pem" ec2-user@ec2-54-91-59-170.compute-1.amazonaws.com

```

![linux](./images/sudo-su.png)

### Installing the Web Server:

- Elevate privileges

```
sudo su

```
- Update all of the packages on the instance

```
yum update -y

```
- Install Apache server

```
yum install httpd -y

```
- Start the webserver

```
service httpd start

```

- Check if the server is working (public ipv4 address)

![works](./images/apache-webserver.png)

### Add a static HTML file to be served

Add own custom web page.
By default, the apache web server will display the index.html file found in /var/www/html directory in the root path of the website.
In this section you will create an index.html file to be served.
Navigate to the directory mentioned above

```
cd /var/www/html

```
### Create an index.html file in this directory

```
nano index.html

```

- Add any html content to the file

```
<html><body>My webserver is running!!!😮</body></html>

```
![linux](./images/webserver-running2.png)

### Task 3b:

- Windows Os

Execution:


- Click on Launch Instance

![launch](./images/microsoft-1.png)

![launch](./images/microsoft-2.png)

![launch](./images/microsoft-3.png)

![launch](./images/microsoft-4.png)

![launch](./images/microsoft-5.png)

![launch](./images/microsoft-6.png)

![lauch](./images/microsoft-7.png)

- Connect to WIndows server

![connect](./images/microsoft-connect1.png)

![connect](./images/microsoft-connect2.png)

- Click on decrypt key. Upload the key pair you used to create the instance in my case my-key1

![connect](./images/microsoft-connect3.png)

![connect](./images/microsoft-connect35.png)

![connect](./images/microsoft-connect356.png)

![connect](./images/microsoft-connect4.png)

![connect](./images/microsoft-connect5.png)

![connect](./images/microsoft-connect6.png)













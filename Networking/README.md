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

### Task 2:

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

2. Create another webserver in the public subnet.

Follow same instructions as that of the private server but this time choose public subnets and security groups inbound rule should look like this.
![security](./images/security-groups.png)

- Connect to the Public server.

![connect](./images/connect1.png)

![connect](./images/connect2.png)









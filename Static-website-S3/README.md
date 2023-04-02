Week 1 started [here](https://jobina.hashnode.dev/technical-bootcamp-30)

Week 2:

![Timetable](./images/week2-timetable.png)

We learnt that ***Virtualization*** is when we take one physical computer and create multiple "virtual" computers inside of it. Each virtual computer is like its own little world, with its own operating system, apps, and files. And just like with building blocks, we can create multiple virtual computers using the same physical computer, without having to buy more computers.

But how do we make sure that each virtual computer stays separate and doesn't interfere with the others? That's where a hypervisor comes in. Think of the hypervisor as a special kind of building block that helps us keep each virtual computer separate and running smoothly. It makes sure that each virtual computer gets its fair share of resources (like processing power and memory), and that they don't get mixed up with each other.

We learnt how to connect to a virtual machine ie EC2 instance(AWS)
We proceeded to learn about Storage and networking. We learned about:

- Amazon Simple Storage Service (S3): This is a scalable and durable object storage service that allows you to store and retrieve any amount of data from anywhere on the web.

- Amazon Elastic Block Store (EBS): This is a block-level storage service that is used for persistent storage of data for Amazon Elastic Compute Cloud (EC2) instances.

- Amazon Elastic File System (EFS): This is a file system service that provides scalable and highly available file storage for use with Amazon EC2 instances.

- Amazon Glacier: This is a low-cost, archival storage service that is designed for data that is infrequently accessed.

- AWS Storage Gateway: This is a hybrid storage service that allows you to seamlessly and securely integrate your on-premises storage infrastructure with the AWS Cloud.

- AWS Snowball: This is a physical data transport solution that helps you transfer large amounts of data into and out of AWS.

- AWS Snowmobile: This is a secure and efficient way to transfer exabytes of data to AWS using a 45-foot-long shipping container.

- Amazon FSx for Lustre: This is a high-performance file system that is optimized for compute-intensive workloads.

- Amazon FSx for Windows File Server: This is a fully managed Windows file system that is built on Microsoft Windows Server.

- Amazon EBS-backed Amazon Machine Images (AMIs): This is a way to store an EC2 instance as a reusable Amazon Machine Image (AMI) that you can use to launch new instances.

We were asked to set up a static website using S3

### Steps:

- Login to the AWS Console

- Search for S3 in the search bar

- Click on Create bucket

![create-bucket](https://user-images.githubusercontent.com/113374279/229351178-3ca50ef5-207b-4741-85ed-83a5b6883f71.png)

- Add Bucket name

- ACL disabled 

![bucket-name](https://user-images.githubusercontent.com/113374279/229351375-8c902adb-a9af-477c-9e16-27ec000b41e7.png)

- Grant public Access

![unblock-publicaccess1](https://user-images.githubusercontent.com/113374279/229351659-e29b3a9c-43e2-4946-81e3-302a1d2eb5e2.png)

- Acknowledge that you are granting public access to the objects in the bucket.

![public-acess2](https://user-images.githubusercontent.com/113374279/229352167-3eda4379-79b7-4198-9d20-2ee83f755571.png)

- Leave everyother thing as default 

- Click on `Create bucket`

![create-ehcbucket](https://user-images.githubusercontent.com/113374279/229352235-f8566ae1-3781-42cf-ae6b-1b3b0f04ec9b.png)

![created bucket-objects](https://user-images.githubusercontent.com/113374279/229352338-38c4db11-d809-4b51-ba7b-1c4a8078facd.png)

- Click into the created bucket

- Click on properties
 
 ![properties](https://user-images.githubusercontent.com/113374279/229374329-21a455c6-ef3a-4a4b-abb5-9cd9bdcbbdbe.png)


![edit-staticwebsite](https://user-images.githubusercontent.com/113374279/229374292-69253071-27ed-40a6-87f3-6db94fd0f07f.png)

- write your file name `index.html` and the error page you want (this is optional) `error.html`

- `Save Changes`

![save-changes](https://user-images.githubusercontent.com/113374279/229374513-a5b3e86e-39ae-4213-89ce-e34e13ac5e40.png)
 
- Go to [tooplate.com](http://tooplate.com/) for free html templates.

- Upload files and folders

![upload-folders](https://user-images.githubusercontent.com/113374279/229352634-53d21598-a6f5-4685-b7d7-868da2962a8f.png)

- Click on `Permissions`

![permissions](https://user-images.githubusercontent.com/113374279/229352773-49dbd15b-dc29-4e8d-b096-c9745660b578.png)

- Edit `bucket policy` Add the following code.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::Bucket-Name/*"
            ]
        }
    ]
}

```
- Click on `save changes`

Kindly remember to edit with your own unique bucket name.

- Go to `properties` under `static website hosting`  Copy the URL and test on browser.

![url](https://user-images.githubusercontent.com/113374279/229353698-c90d7a88-c865-4218-9f24-69d5b71fa0d1.png)

![website](https://user-images.githubusercontent.com/113374279/229353743-0289c798-fe85-4d2b-a25b-1053f78b5814.png)






























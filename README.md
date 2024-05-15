# How to host a static web page using AWS S3 and CloudFront for content delivery

Simple Storage Service (S3) is a storage service provided by AWS were files can be hosted. It is scalable, highly available and it supports integration with AWS. S3 is not limited to file storage alone, it can be used for website hosting, database backups and so on.  
CloudFront is another service proided by AWS that helps distribute the content of the web through a worldwide network of data centers 
This guide shows how to host a static web page using AWS S3 and CloudFront for content delivery
## Requirements
- * AWS account  
- * The files of the web page (html, css, javascript)
### Step 1: Create a bucket on AWS S3
a) Signup or signin to your AWS account if you are an existing user  
b) Click services and type "S3" on the search bar 

![img1](images/Shot0001.png)  

c) Create a new bucket  

![img1](images/Shot0002.png)  

d) Insert your bucket name it must be unique within the global name space and it must adhere to the bucket naming rules  

![img1](images/Shot0003.png)  

e) Scroll down, untick **block all public access**. This has to be done because blocking public access is a default setting of AWS S3

![img1](images/Shot0004.png)  

f) Scroll down and click create bucket  

![img1](images/Shot0005.png)  

g) On the bucket dashboard click on the newly created bucket  

![img1](images/Shot0007.png)  

h) Click on upload to upload files of the web content   

![img1](images/Shot0008.png)  

i) Click properties  

![img1](images/Shot1.png)  
 
j) Scroll down and click edit on static website hosting and 

![img1](images/Shot2.png)   

j) enable it. Input the name of your home page  

![img1](images/Shot0011.png)   


k) Scroll down and click save changes 

![img1](images/Shot0012.png)

L) click on Permissions  

![img1](images/Shot0013.png)

M) Scroll down till you get to Bucket policy then click edit  

![img1](images/Shot0014.png)

N) Input this code  
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::izikinvoicecreator-aws/*"
        }
    ]
}  

![img1](images/Shot0016.png)

O) Click save changes 

![img1](images/Shot0015.png)  

P) Click properties 

![img1](images/Shot0017.png)   

Q) Scroll down to static web hosting, scroll down copy the link and paste on your browser. The static web page should be  up

![img1](images/Shot0018.png)   

### Step 2: Create CloudFront Distribution
a) Click services and type "CloudFront" on the search bar

![img1](images/Shot0021.png)   

b) Click create  cloudfront distribution

![img1](images/Shot0022.png)

c) On the origin domain input bar a suggestion pop should come up showing the origin domain name then click it

![img1](images/Shot0023.png)  

d) Insert index.html as the default root object

![img1](images/Shot0023.png)  

e} Click create distribution 

![img1](images/Shot0025.png)

F) Deployment is dependant on your internet speed butyou can track the progress

![img1](images/Shot0027.png) 

g) When it is done it will show enabled as shown in the image below  

![img1](images/Shot0028.png)  

h) copy your distribution domain name and paste it on your browser. 

![img1](images/Shot0030.png) 

The webpage 

![img1](images/Shot0029.png)   




























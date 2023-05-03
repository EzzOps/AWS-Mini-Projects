# Implementing a simple serverless application which uses Web Identity Federation.  

## The application runs using the following technologies

- S3 for front-end application hosting

- Google API Project as an ID Provider

- Cognito and IAM Roles to swap Google Token for AWS credentials

The application runs from a browser, gets the user to login using a Google ID and then loads all images from a private S3 bucket into a browser using presignedURLs.  

This advanced demo consists of 6 stages :-  

- STAGE 1 : Provision the environment and review tasks    
![image](https://user-images.githubusercontent.com/73319030/235738466-1447b8fa-96dc-4b82-b4f1-b9d9651af324.png)
- STAGE 2 : Create Google API Project & Client ID  
![image](https://user-images.githubusercontent.com/73319030/235866001-ae0c0145-65f2-4459-8c64-98e8f0736197.png)
- STAGE 3 : Create Cognito Identity Pool  
![image](https://user-images.githubusercontent.com/73319030/235763332-5831a3e8-2a3d-4084-8800-0dd2377b6e40.png)
- STAGE 4 : Update App Bucket & Test Application
![image](https://user-images.githubusercontent.com/73319030/235770753-94814403-d560-4291-9d39-d41a22683dfa.png)

_notes_

_ you can't use AWS resources with anything but AWS credentials. And so this OAth token ( Google API Project as an ID Provider) can't be used to access anything inside AWS, so the swaping between google token and cognito is  important
 _ By design, delivering data out of CloudFront can be more cost effective than delivering it from S3 directly to your users.

_  In addition, data transfer out for content by using CloudFront is often more cost effective than serving files directly from S3, and there is no data transfer fee from S3 to CloudFront. You only pay for what is delivered to the internet from CloudFront

![image](https://user-images.githubusercontent.com/73319030/235865002-ea8b1c28-e177-4384-8627-5c853b6d1e6a.png)
![image](https://user-images.githubusercontent.com/73319030/235865031-710e0f6d-bdcd-4f77-a7c6-b00f834eaaa7.png)


## Credits
**[Mini-project - Simple WEB Identity Federation App]**

https://github.com/acantril/learn-cantrill-io-labs/tree/master/aws-cognito-web-identity-federation

https://www.youtube.com/playlist?list=PLTk5ZYSbd9Mh_T2ymo5TAm-RqOamz59Gd

**[Amazon S3 + Amazon CloudFront](https://aws.amazon.com/blogs/networking-and-content-delivery/amazon-s3-amazon-cloudfront-a-match-made-in-the-cloud/)**

### Steps to create a VPC

+ Choose Create VPC and select VPC and more in the VPC console. You can preview the VPC resources that you are about to create all on the same page
+ In Name tag auto-generation, you can specify a prefix value for Name tags. This value is used to generate Name tags for all VPC resources in the preview
- IPv4 CIDR block (default)
- Choose the number of Availability Zones (AZs) up to 3 (in this case using 2)
- The number of public and private subnet types changes based on the number of AZs and shows the total number of each subnet type it will create
- Choose number of AZ in which to create NAT gateways(Note that there is a charge for each NAT gateway)
- To route traffic to Amazon Simple Storage Service (Amazon S3) buckets more securely, you can choose the S3 Gateway endpoint by default(in this case none) 
- Choose Create VPC at the bottom of the page
![alt text](image.png)


### Steps to create an EC2 Auto-scaling group
+ Step 1: Create a launch template
+ Step 2: Create a single-instance Auto Scaling group
+ Step 3: Verify your Auto Scaling group
+ Step 4: Terminate an instance in your Auto Scaling group
+ Step 5: Next steps
+ Step 6: Clean up



**bold text**
*italicized text*
> blockquote
[title](https://www.example.com)





# VPC-Peering-and-Logging
## Architecture
## Creating VPC
This VPC is for App Server.
1. Sign into the AWS Console.
2. Select 'VPC and more', provide a suitable name and IPV4 CIDR block.
3. Choose number of public subnets and click on create.
4. Crreate another VPC for Web Server in different availability zone.

 Navigate to 'Security Group' and allow "all traffic" for Inbound Rules.

 ## Creating EC2 Instance
 1. Launch an EC2 instance with modification in Network Setting for App Server.
 2. Choose the subnet and 'Enable' Auto Assign IP Address.
 3. Create another instance for Web Server.
## Navigate to Different Region
Create VPC for DB Server and an EC2 Instance. 



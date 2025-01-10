# VPC-Peering
## Architecture
![VPC PC Arch](https://github.com/user-attachments/assets/b1daeada-2802-41f5-bcbf-9c6def9f20f5)

## Creating VPC
This VPC is for App Server.
1. Sign into the AWS Console.
2. Select 'VPC and more', provide a suitable name and IPV4 CIDR block.
![1](https://github.com/user-attachments/assets/9aac937e-28f6-4823-9233-f3bda848d509)
![2](https://github.com/user-attachments/assets/ca0e6ce7-1e39-4796-82c4-0e872a64a761)
3. Choose number of public subnets and click on create.
4. Crreate another VPC for Web Server in different availability zone.

 Navigate to 'Security Group' and allow "all traffic" for Inbound Rules.
![3](https://github.com/user-attachments/assets/5806c2c2-d678-465e-8c4d-12909f8c0ea7)
![5 Web](https://github.com/user-attachments/assets/ba37f019-fce7-4197-a723-8b67731a789e)

 ## Creating EC2 Instance
 1. Launch an EC2 instance with modification in Network Setting for App Server.
 ![4](https://github.com/user-attachments/assets/cc2f2f03-7225-4afd-8b94-0ac99fa85a12)
 2. Choose the subnet and 'Enable' Auto Assign IP Address.
 3. Create another instance for Web Server.
## Navigate to Different Region
Create VPC for DB Server and an EC2 Instance. 
![6](https://github.com/user-attachments/assets/9389bf41-2610-4c1f-8267-99809f74ee42)
![7 Ohio SG 7](https://github.com/user-attachments/assets/c72c07d7-667b-4f1c-b0bf-721e0b67528a)
![8](https://github.com/user-attachments/assets/8fc93d19-410b-41b5-88bd-54c37ffa295e)


## VPC Peering within Region
1. Establish VPC Peering request from either one of the VPCs and accept the request.
![11 VPC Peering 1](https://github.com/user-attachments/assets/64b18ee5-f08e-4f43-933c-fafc29e56735)
2. Navigate to the Route Table tab and click on 'App Server', edit the Destination IP (Web Server IP address) address along with the target selected as 'Peering Connection' and choose the Peering Request from the drop down options.
![12 AS RT](https://github.com/user-attachments/assets/36faa366-e431-4bbe-9a16-20d6cbb04c34)
![13 AS RT](https://github.com/user-attachments/assets/aa4d8adc-90af-487c-b60b-aad05ecf02e4)
3. Repeat the same steps for 'Web Server'.
4. PuTTY into the App Server from the App Server's Access Key and Instance IP.
![9 Putty AS](https://github.com/user-attachments/assets/2af9d136-0f01-433c-8f2d-6ab140145a9d)
5. PuTTY into the Web Server from the Web Server's Accesss Key and Instance IP.
![10 Putty WS](https://github.com/user-attachments/assets/c5998879-dcb4-499c-afa4-77ef26eacc88)
6. Ping each other to check connectivity.
![14 Peering Conncected ASWS](https://github.com/user-attachments/assets/dcc8919c-abbc-4f11-8981-da7f219472c7)

## VPC Peering with Another Region
1. Establish the VPC Peering request to another Region by specifying the VPC ID.
![15 DB_App PC](https://github.com/user-attachments/assets/e6d04f60-224d-4336-9d71-3d7946f3d142)
2. Accept the peering request from the another region and configure the Route Table to add the IP address of 'App Server'.
3. Configure the Route Table of 'App Server' and add the IP address of 'Database Server'.
![16 PC](https://github.com/user-attachments/assets/b697cedf-415e-4a6a-8845-bcc59acf0004)
![17 DB AS RT](https://github.com/user-attachments/assets/f4200e5e-7803-4044-a83c-550009927615)
![18 AS DB RT](https://github.com/user-attachments/assets/cedcfa49-b666-4a61-9532-6e89035ba0f6)


Establish Peering Connection between 'Web Server' and 'Database Server', following the same steps as above.
![19 Web_DB PC](https://github.com/user-attachments/assets/b51871a9-fa18-4277-ab2b-c314422c8b5c)

## Checking Connectivity among VPC
![VPC Peering Estd](https://github.com/user-attachments/assets/fcdc7584-738d-4ba6-bfe7-acba3b79a73c)
Ping 'App Server' to 'Database Server'.
Ping 'Web Server' to 'Database Server'.
Ping 'Database Server' from 'App Server and Web Server'.

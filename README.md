# AWS Highly Available VPC Architecture Project

## Project Overview
This project demonstrates how to build a highly available architecture in AWS using public and private subnets.

## Services Used
- Amazon VPC
- Amazon EC2
- Application Load Balancer
- NAT Gateway
- Internet Gateway
- Bastion Host

## Architecture
Internet
   ↓
Application Load Balancer
   ↓
Target Group
   ↓        ↓
EC2 Server1 EC2 Server2
Port 8000   Port 8000

Project Implementation:

Step 1: Design and configure a VPC: Create a VPC with custom IP ranges. Set up public and private subnets. Configure route tables and associate subnets.

Step 2: Implement network security: Set up network access control lists (ACLs) to control inbound and outbound traffic. Configure security groups for EC2 instances to allow specific ports and protocols.

Step 3: Provision EC2 instances: Launch EC2 instances in both the public and private subnets. Configure security groups for the instances to allow necessary traffic. Create and assign IAM roles to the instances with appropriate permissions.

Step 4: Networking and routing: Set up an internet gateway to allow internet access for instances in the public subnet. Configure NAT gateway or NAT instance to enable outbound internet access for instances in the private subnet. Create appropriate route tables and associate them with the subnets.

Step 5: SSH key pair and access control: Generate an SSH key pair and securely store the private key. Configure the instances to allow SSH access only with the generated key pair. Implement IAM policies and roles to control access and permissions to AWS resources.

Step 6: Test and validate the setup: SSH into the EC2 instances using the private key and verify connectivity. Test network connectivity between instances in different subnets. Validate security group rules and network ACL settings.

Step 7: Create Web Page on both servers and Start Python Web Server on port 8000
python3 -m http.server 8000

Step 8: Access Application
Open browser and visit:
http://LOAD_BALANCER_DNS

## Testing
Load balancing verified using curl and browser testing.

Server 1 Output:
My First AWS Project to Demonstrate apps in private subnet

Server 2 Output:
My Second AWS Project to Demonstrate apps in private subnet

By implementing this project, I gained hands-on experience in setting up a secure VPC with EC2 instances, implemented networking and routing, configured security groups and IAM roles, and ensured proper access control. This project provided a practical understanding of how these AWS services work together to create a secure and scalable infrastructure for applications.

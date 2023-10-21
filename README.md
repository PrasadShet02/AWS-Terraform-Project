# AWS Infrastructure Setup with Terraform

This repository contains Terraform code to set up an AWS infrastructure with high availability and fault tolerance.

## Architecture Overview

The architecture consists of the following components:

- Virtual Private Cloud (VPC)
- Subnets
- Internet Gateway
- Route Table
- Security Groups
- S3 Bucket
- EC2 Instances
- Application Load Balancer (ALB)

## How it Works

1. **VPC Creation**: Creates a Virtual Private Cloud (VPC) with the specified CIDR block.

2. **Subnet Creation**: Sets up two subnets within the VPC, each associated with an availability zone and configured for public accessibility.

3. **Internet Gateway Creation**: Attaches an internet gateway to the VPC to enable communication with the internet.

4. **Route Table Creation**: Configures a route table to route traffic outside the VPC through the internet gateway.

5. **Security Group Creation**: Sets up a security group to control inbound and outbound traffic for the instances, allowing HTTP and SSH access from any source.

6. **S3 Bucket Creation**: Creates an S3 bucket for storing data.

7. **EC2 Instance Creation**: Launches two EC2 instances, assigns them to different subnets, and applies the created security group and user data for configuration.

8. **Application Load Balancer (ALB) Creation**: Sets up an ALB with defined security groups and subnets for load balancing incoming traffic.

9. **Target Group Creation**: Creates a target group associated with the ALB for routing requests to registered instances.

10. **Target Group Attachments**: Attaches the created instances to the target group to distribute incoming traffic.

11. **ALB Listener Creation**: Configures an ALB listener to process and forward incoming connections to the target group.

12. **Output**: Provides the DNS name of the ALB as output, allowing access to the application.

## Usage

To set up the infrastructure, follow these steps:

1. Clone the repository.
2. Navigate to the directory containing the Terraform code.
3. Enter your ami id in `main.tf` file
4. Run `terraform init` to initialize the working directory.
5. Run `terraform apply` to apply the changes and create the infrastructure.

## Output

After running the Terraform code, you can access the application using the provided DNS name of the Application Load Balancer.

Happy Learning!

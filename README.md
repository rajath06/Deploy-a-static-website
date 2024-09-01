AWS Static HTML Web App Project
Overview
This project demonstrates the creation of a Virtual Private Cloud (VPC) in AWS, intended for hosting servers in a production environment. The setup includes the deployment of servers across two Availability Zones (AZs) using an Auto Scaling group and an Application Load Balancer (ALB). The servers are secured within private subnets and can connect to the internet through a NAT gateway.

Project Details
Architecture
VPC Creation: Establish a Virtual Private Cloud to serve as the foundation for the infrastructure.
Auto Scaling Group: Deploy an Auto Scaling group in multiple Availability Zones to ensure high availability.
Application Load Balancer (ALB): Use an ALB to distribute HTTP/HTTPS traffic across multiple targets at the application layer (Layer 7).
Private Subnets: Place the servers within private subnets for added security.
NAT Gateway: Set up NAT gateways in both AZs to allow the servers to access the internet while remaining in private subnets.
Bastion Host: Deploy a bastion host (jump host) within a public subnet to securely access the private instances.
Elastic IP Addresses: Use Elastic IP addresses to maintain a static IP for instances even after they are terminated.
Deployment Steps
Create a VPC: Start by creating a VPC that will host the entire infrastructure.
Launch EC2 Instances: Create EC2 instances within an Auto Scaling group and configure the necessary inbound rules.
Setup Auto Scaling Groups: Configure Auto Scaling groups using launch templates to manage the EC2 instances.
Bastion Host Configuration: Since the instances are private and lack public IPs, use a bastion host to access them.
Deploy the Static Website: Deploy the static HTML website within one of the subnets.
Create a Target Group: Configure a target group using the load balancer to manage traffic to the EC2 instances.
Final Hosting: Ensure the website is accessible through the Application Load Balancer.
Key Notes
Elastic IP Address: Elastic IP addresses remain attached to the instance even after deletion, ensuring consistent IP addressing.
Jump Host: The jump host is essential for connecting to the private servers via the public subnet.
Application Load Balancer (ALB): The ALB operates at Layer 7, managing HTTP and HTTPS traffic efficiently across multiple targets.
Repository Content
Reference Diagram: A detailed architecture diagram depicting the setup.
Deployment Scripts: Scripts used to deploy the infrastructure and the web app on an EC2 instance.

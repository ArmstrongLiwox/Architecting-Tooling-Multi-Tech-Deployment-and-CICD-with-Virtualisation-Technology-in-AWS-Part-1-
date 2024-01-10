# Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS

The Architecture determines what will be built.

## Scenario

A small to medium-sized digital marketing agency, **DigitalBoost**, wants to enhance its online presence by creating a ***high-performance*** WordPress-based website for their clients. 
The agency needs a *scalable*, *secure*, and *cost-effective* solution that can handle increasing traffic and seamlessly integrate with their existing infrastructure. 
Your task as an AWS Solutions Architect is to design and implement a WordPress solution using various AWS services, such as ***Networking***, ***Compute***, ***Object Storage***, and ***Databases***.

# Project Requirement

1. High-performance: Highly available
2. Scalable : infrastructure can easier scale
3. Secure:
4. Cost-effective: something their budget can accomodate

# Some Considerations
1. Proximity to DigitalBoost clients
2. Available services in the chosing region. Reduce Latency as much as possible (CLOUD-FRONT)
3. Your webserver and database should be in a private subnet. it should be not be exposed to the public
4. Bastion Host gives access to other resources that are private
5. the content of the website will be served via the Load-Balancer
6. Load-Balancer will be in the public subnet
7. one will be a backup
8. Having different subnets does not cost you extra money

# Task

draw.io
![draw io](https://github.com/ArmstrongLiwox/Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS-Part-1-/assets/143335106/4ede15a3-58b4-482b-bf20-fac9cc20deef)

# Excecution

Region : US East (N. Virginia) us-east-1 has the highest number of availability zones

> let us focus on the cloud
> First deal with region (High availablity). each region has at least three availability zones.
> Second is Network - VPC
> Bastion Host gives access to other resources that are private

![region](https://github.com/ArmstrongLiwox/Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS-Part-1-/assets/143335106/f73ef97c-b5fe-441c-ae00-93aa08220e56)

![vpc](https://github.com/ArmstrongLiwox/Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS-Part-1-/assets/143335106/7b974523-bc8d-4210-b1a5-9612509d9d4e)

Your NAT gateway is always in a public subnet

Your VPC must have a connection in an internet gateway

difference is at the route tables level

public subnet is connected to an internet gateway in its route table 
private subnet is connected to a NAT gateway in its route table 

Having different subnets does not cost you extra money
the seperation is for more security

![az1](https://github.com/ArmstrongLiwox/Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS-Part-1-/assets/143335106/c589cb68-73b1-45f5-a842-5272ef2db022)

![az2](https://github.com/ArmstrongLiwox/Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS-Part-1-/assets/143335106/ed6c72cf-a394-4ef6-b552-cacb554845fc)


mount the EFS : Elastic file system ()

NFS : network file store

![draft](https://github.com/ArmstrongLiwox/Architecting-Tooling-Multi-Tech-Deployment-and-CICD-with-Virtualisation-Technology-in-AWS-Part-1-/assets/143335106/11b640f0-a042-4d81-9c91-ab87b05392c3)


s3: media (elastic)
ebs: os
efs: configuration files (elastic)






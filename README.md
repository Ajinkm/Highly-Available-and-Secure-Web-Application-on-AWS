# Highly-Available-and-Secure-Web-Application-on-AWS
This project focuses on building a production-ready web application on AWS using a secure VPC, EC2, ALB, Auto Scaling, RDS, S3, IAM, and CloudWatch, following real-world best practices for availability, security, and scalability.

#  Project Overview

This project demonstrates the design and deployment of a **highly available, secure, and scalable web application on AWS** using core cloud and DevOps services. The architecture follows **real-world production best practices**, including network isolation, load balancing, auto scaling, monitoring, and secure access control.

The application runs on EC2 instances behind an Application Load Balancer, stores data in Amazon RDS, uses Amazon S3 for storage, and is fully monitored using Amazon CloudWatch.

---

## Project Workflow

<img width="611" height="481" alt="vpc-example-private-subnets" src="https://github.com/user-attachments/assets/f970942e-b9d7-4a88-a6aa-41f23ba10d30" />

---

## 🏗️ Architecture Summary

* Custom **VPC** with public and private subnets across multiple Availability Zones
* **Application Load Balancer (ALB)** for traffic distribution
* **Auto Scaling Group (ASG)** for high availability and scalability
* **EC2 instances** to host the web application
* **Amazon RDS** in private subnets for database management
* **Amazon S3** for object storage
* **IAM roles and policies** for secure access
* **CloudWatch** for monitoring, logging, and alarms

---

##  AWS Services Used

* Amazon VPC
* Amazon EC2
* Application Load Balancer (ALB)
* Auto Scaling
* Amazon RDS (MySQL / PostgreSQL)
* Amazon S3
* AWS IAM
* Amazon CloudWatch

---

## Security Design

* EC2 instances do **not** have public IPs
* Database is deployed in **private subnets only**
* Security Groups allow **restricted traffic flow**:

  * Internet → ALB
  * ALB → EC2
  * EC2 → RDS
* IAM roles used instead of access keys

---

##  Project Implementation Steps

1. **IAM Setup**

   * Created IAM users, roles, and policies
   * Assigned IAM role to EC2 for secure AWS access

2. **VPC Configuration**

   * Created a custom VPC with public and private subnets
   * Configured route tables and Internet Gateway

3. **Security Groups**

   * Defined inbound and outbound rules for ALB, EC2, and RDS

4. **EC2 Deployment**

   * Launched EC2 instances with user data scripts
   * Installed and configured web server

5. **Load Balancer Setup**

   * Created Application Load Balancer
   * Configured target groups and listeners

6. **Auto Scaling Configuration**

   * Created Launch Template
   * Configured scaling policies based on CPU utilization

7. **RDS Deployment**

   * Created database instance in private subnets
   * Configured DB subnet group and security group

8. **S3 Integration**

   * Created S3 bucket with versioning enabled
   * Used IAM role for EC2 to access S3

9. **Monitoring with CloudWatch**

   * Enabled EC2 and ALB monitoring
   * Created alarms for CPU utilization and instance health

---

##  Testing and Validation

* Verified load balancing across multiple EC2 instances
* Tested Auto Scaling by increasing CPU load
* Ensured database was inaccessible from the public internet
* Monitored metrics and logs using CloudWatch

---

## Key Learnings

* Designing secure and scalable AWS architectures
* Implementing high availability using multi-AZ deployments
* Using IAM roles for secure access management
* Monitoring and auto-scaling applications in production-like environments
* Applying DevOps and cloud best practices

---

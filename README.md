# 🚀 Two-Tier Web Application Deployment using AWS CloudFormation

Deployed a production style 2 Tier web application on AWS using **Infrastructure as Code (IaC)** with **AWS CloudFormation Nested Stacks**. This project demonstrates automated provisioning of networking, compute, security, and database resources using modular CloudFormation templates.

---

## 📌 Project Overview

This project provisions a complete AWS infrastructure for a 2 Tier web application using a **Master CloudFormation Stack** and multiple **Nested Stacks**.

The infrastructure is modular, reusable, and follows Infrastructure as Code (IaC) principles, making deployments consistent and repeatable.

---

## 🏗️ Architecture

```
                          Internet
                              │
                    Internet Gateway
                              │
                     Public Route Table
                              │
                     Public Subnet
                              │
                     EC2 Web Server
                    (Apache + HTML)
                              │
                  Security Group (HTTP/SSH)
                              │
                    Private Route Table
                              │
                     Private Subnet
                              │
                         Amazon RDS
                           (MySQL)
```

---

## ☁️ AWS Services Used

| Service | Purpose |
|----------|----------|
| AWS CloudFormation | Infrastructure as Code (IaC) |
| Amazon EC2 | Web Server |
| Amazon RDS (MySQL) | Relational Database |
| Amazon VPC | Network Isolation |
| Internet Gateway | Internet Connectivity |
| Route Tables | Traffic Routing |
| Security Groups | Firewall Rules |
| Amazon S3 | Storage for Nested CloudFormation Templates |
| IAM | AWS Permissions |

---

## 📂 Project Structure

```text
aws-cloudformation-2-tier-webapp/
│
├── master.yaml
│
├── templates/
│   ├── networking.yaml
│   ├── security.yaml
│   ├── compute.yaml
│   └── database.yaml
│
├── screenshots/
│
└── README.md
```

---

## 📖 CloudFormation Stack Structure

### Master Stack

Responsible for deploying all NESTED stacks.

- Networking Stack
- Security Stack
- Compute Stack
- Database Stack

---

### Networking Stack

Creates:

- VPC
- Internet Gateway
- Public Subnet
- Private Subnet
- Route Tables
- Route Associations

---

### Security Stack

Creates:

- EC2 Security Group
- RDS Security Group

Configured to allow:

- HTTP (80)
- SSH (22)
- MySQL (3306)

---

### Compute Stack

Creates:

- EC2 Instance
- Apache Web Server
- UserData Script
- EC2 Outputs

---

### Database Stack

Creates:

- Amazon RDS MySQL
- DB Subnet Group
- Database Configuration

---

## ⚙️ Features

- Infrastructure as Code (IaC)
- Nested CloudFormation Stacks
- Modular Template Design
- Parameterized Deployment
- Region Mapping
- EC2 UserData Automation
- Public & Private Subnet Architecture
- Security Group Configuration
- Automated Infrastructure Provisioning

---

## 🚀 Deployment Steps

### 1. Clone Repository
```
git clone https://github.com/<your-username>/aws-cloudformation-2-tier-webapp.git
```

### 2. Upload Nested Templates

Upload all templates inside the **templates/** folder to an S3 bucket.


### 3. Update Template URLs

Update the `TemplateURL` values inside `master.yaml`.


### 4. Deploy Master Stack

Deploy the CloudFormation Master Stack from the AWS Console.


### 5. Wait for Stack Completion

Ensure the stack reaches:

```
CREATE_COMPLETE
```

### 6. Access the Web Server

Open the EC2 Public IP in your browser.

---

## 📷 Project Screenshots

ADDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDD HEREEEEEEEEEEEEEEEEE

---

## 📌 Future Enhancements

- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- NAT Gateway
- Bastion Host
- Amazon Route 53
- AWS Certificate Manager (HTTPS)
- CloudWatch Monitoring
- CloudFormation Drift Detection
- CI/CD using AWS CodePipeline & CodeBuild
- Dockerized application deployment

---

## 👨‍💻 Author

**Himanshu Saindlya**
AWS Cloud Enthusiast

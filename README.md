# AWS Three-Tier Architecture Project

This project demonstrates the deployment of a **Three-Tier Architecture** on AWS to achieve **high scalability, availability, and fault tolerance**.  
The architecture separates the application into three layers:
- **Presentation Layer (Frontend)** – React application hosted on EC2 & served via Apache
- **Application Layer (Backend)** – Node.js backend running on EC2
- **Data Layer (Database)** – MySQL RDS in a private subnet

---

## 📌 Features
- **VPC with Public & Private Subnets**
- **Internet Gateway, NAT Gateway & Route Tables**
- **Application Load Balancer (ALB) for Frontend & Backend**
- **Auto Scaling Groups for Web & App tiers**
- **Amazon RDS (MySQL) in Multi-AZ setup**
- **Amazon Route 53 for DNS**
- **CloudFront for static content delivery**
- **AWS Certificate Manager (ACM) for SSL**

---

## 🛠️ Prerequisites
- AWS Account
- Basic knowledge of Linux & Networking
- Domain Name (optional, for Route 53 & SSL)
- Key Pair for EC2 access
- Git installed

---

## 🚀 Deployment Steps
1. **VPC Setup**
   - Create VPC, subnets (public & private), Internet Gateway, NAT Gateway, Route Tables.

2. **Security**
   - Configure **Security Groups** for ALB, EC2, and RDS.

3. **RDS Setup**
   - Launch MySQL RDS instance in private subnets.
   - Store DB credentials in `.env`.

4. **Frontend Setup**
   ```bash
   git clone https://github.com/<your-username>/aws_three_tier_project.git
   cd aws_three_tier_project/client
   npm install
   npm run build
   sudo cp -r build/* /var/www/html/

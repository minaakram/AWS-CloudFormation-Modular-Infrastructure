# Automating AWS Infrastructure with CloudFormation (Modular Approach)

## 📌 Project Overview
This project demonstrates a professional approach to **Infrastructure as Code (IaC)**. I deployed a multi-layer architecture on AWS using **CloudFormation**, focusing on modularity, security, and data resilience.

## 🏗️ Modular Architecture
I decoupled the infrastructure into two distinct layers to ensure reusability:
1.  **Networking Layer**: [lab-network.yaml](./templates/lab-network.yaml) - Deploys a custom VPC, Public Subnets, and IGW.
2.  **Application Layer**: [lab-application.yaml](./templates/lab-application.yaml) - Deploys an Apache Web Server on EC2, dynamically importing network values from the first stack.

## 🚀 Key Technical Features
* **Cross-Stack Referencing**: Used `Fn::ImportValue` to link the application stack to the network stack dynamically.
* **Safe Updates**: Performed a stack update using **Change Sets** to enable HTTPS (Port 443) without resource replacement.
* **Visual Architecture**: Analyzed and modified the design using **AWS Infrastructure Composer**.
* **Data Protection**: Implemented a `DeletionPolicy: Snapshot` on the EBS volume to ensure data persistence even after stack deletion.

## 📸 Implementation Gallery

### 1. Successful Stack Deployment
![CloudFormation Stacks](./screenshots/Stacks.png)
*Both Networking and Application stacks in CREATE_COMPLETE status*.

### 2. Infrastructure Visualization
![Infrastructure Composer](./screenshots/Infrastructure%20Composer.png)
*Logical view of resources via AWS Infrastructure Composer*.

### 3. Security Group Update (Port 443)
![Security Group](./screenshots/Update%20security%20group.png)
*Adding HTTPS support through a documented stack update*.

### 4. Backup Verification (EBS Snapshot)
![EBS Snapshot](./screenshots/Snapshot.png)
*Snapshot created automatically based on the DeletionPolicy*.

## 🛠️ Tools Used
* **Cloud Provider**: AWS (VPC, EC2, CloudFormation, S3)
* **IaC**: YAML
* **Visualization**: AWS Infrastructure Composer

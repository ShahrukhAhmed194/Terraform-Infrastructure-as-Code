# AWS Infrastructure as Code (Terraform)

A modular Terraform-based Infrastructure as Code (IaC) project for provisioning AWS networking and compute resources using reusable modules.

## 🚀 Overview

This project provisions a structured AWS infrastructure using Terraform modules, following a modular and maintainable architecture.

## 🏗️ Infrastructure Components

The project creates the following AWS resources:

- **VPC:** Creates an AWS Virtual Private Cloud.
- **Subnets:** Creates public and private subnets.
- **Route Tables:** Configures routing for public and private subnets.
- **Security Groups:** Defines network access rules for EC2 instances.
- **Key Pair:** Generates and manages an EC2 SSH key pair.
- **EC2 Instances:** Provisions EC2 instances in public and private subnets.

## 📁 Project Structure

```text
.
├── main.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars
├── modules/
│   ├── vpc/
│   ├── subnets/
│   ├── route_tables/
│   ├── security_groups/
│   ├── key_pair/
│   └── ec2/
└── README.md
```

## ⚙️ Prerequisites

- AWS Account
- AWS CLI configured with appropriate credentials
- Terraform installed
- An AWS IAM user or role with the required permissions

## 🔧 Configuration

Update `terraform.tfvars` with your desired configuration:

```hcl
project_name         = "my-project"
vpc_cidr             = "10.0.0.0/16"
public_subnet_cidr   = "10.0.1.0/24"
private_subnet_cidr  = "10.0.2.0/24"
availability_zone    = "us-east-1a"
my_ip                = "YOUR_PUBLIC_IP/32"
key_name             = "my-key"
private_key_path     = "./keys/my-key.pem"
instance_type        = "t2.micro"
```

## 🚀 Deployment

**1. Clone the repository**

```bash
git clone https://github.com/your-username/your-repository.git
cd your-repository
```

**2. Initialize Terraform**

```bash
terraform init
```

**3. Validate the configuration**

```bash
terraform validate
```

**4. Review the execution plan**

```bash
terraform plan
```

**5. Deploy the infrastructure**

```bash
terraform apply
```

Type `yes` to confirm the deployment.

## 🧹 Destroy Infrastructure

To remove the provisioned AWS resources:

```bash
terraform destroy
```

Type `yes` to confirm.

## 🔒 Security Considerations

- Restrict SSH access using your public IP address.
- Store AWS credentials securely.
- Never commit private SSH keys or sensitive Terraform state files.
- Add `terraform.tfvars`, `.terraform/`, `*.tfstate`, and private key files to `.gitignore`.
- Use appropriate IAM permissions when deploying infrastructure.

## 🛠️ Technologies Used

- **AWS** – Cloud Infrastructure
- **Terraform** – Infrastructure as Code
- **AWS CLI** – AWS Resource Management
- **HCL** – Terraform Configuration Language

## 📌 Notes

This project uses reusable Terraform modules to keep infrastructure components organized, maintainable, and scalable.

---

**Built with Terraform ❤️**

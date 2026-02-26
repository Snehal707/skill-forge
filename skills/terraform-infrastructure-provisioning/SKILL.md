---
name: terraform-infrastructure-provisioning
description: Deploy and manage cloud infrastructure using Terraform's declarative configuration language
version: 1.0.0
metadata:
  skill_forge:
    domain: "terraform"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [terraform, infrastructure-as-code, cloud, devops, hashicorp]
    category: devops
---

# Terraform Infrastructure Provisioning

## When to Use
When you need to provision, modify, or destroy cloud infrastructure resources using declarative configuration files instead of manual processes or imperative scripts.

## Prerequisites
- Terraform CLI installed (version 1.0+)
- Cloud provider credentials configured (AWS CLI, Azure CLI, or GCP CLI)
- Text editor for writing .tf files
- Basic understanding of your target cloud platform

## Procedure
1. Initialize a new Terraform project: `terraform init`
2. Create main configuration file: `touch main.tf`
3. Define provider and resources in main.tf:
   terraform {
     required_providers {
       aws = {
         source  = "hashicorp/aws"
         version = "~> 5.0"
       }
     }
   }
   
   provider "aws" {
     region = "us-west-2"
   }
   
   resource "aws_instance" "example" {
     ami           = "ami-0c55b159cbfafe1d0"
     instance_type = "t2.micro"
   }
   ```
4. Plan the deployment: `terraform plan`
5. Apply the configuration: `terraform apply`
6. Confirm with `yes` when prompted
7. To modify resources, edit .tf files and repeat steps 4-6
8. To destroy resources: `terraform destroy`

## Verification
- Check `terraform show` to see current state
- Verify resources exist in cloud provider console
- Run `terraform plan` should show "No changes" if state matches configuration

## Pitfalls
- Always run `terraform plan` before `apply` to review changes
- Never edit resources manually in cloud console after Terraform manages them
- Use remote state storage for team collaboration
- Keep .terraform directory and terraform.tfstate files secure
- Provider version mismatches can cause compatibility issues

## Sources
- https://developer.hashicorp.com/terraform
- https://en.wikipedia.org/wiki/Terraform_(software)
- https://registry.terraform.io/
- https://github.com/hashicorp/terraform
- https://learn.microsoft.com/en-us/azure/developer/terraform/overview
```
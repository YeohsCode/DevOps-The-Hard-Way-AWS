# 翻译待定

**注意：此文件是原始英文内容的占位符，等待翻译成中文。以下是原始内容，仅供参考。**

---

# Create an S3 bucket to store Terraform state files

In this lab you will create an S3 bucket that will be used to store Terraform state files

## Create The Terraform Configurations

1. You can find the Terraform configuration for the S3 bucket [here](https://github.com/AdminTurnedDevOps/DevOps-The-Hard-Way-AWS/tree/main/terraform-state-s3-bucket). The Terraform configuration files are used to create an S3 bucket that will store your TFSTATE.

The Terraform `main.tf` will do a few things:
- Create the S3 bucket in the `us-east-1` region
- Ensure that version enabling is set to `True`
- Utilize AES256 encryption 

2. Create the bucket by running the following:
- `cd terraform-state-s3-bucket`
- `terraform init` - To initialize the working directory and pull down the provider
- `terraform plan --var-file=../eks-vpc-terraform-module/dev.tfvars` - To go through a "check" and confirm the configurations are valid. You will need to change the `tfvars` file between dev and prod
- `terraform apply --var-file=../eks-vpc-terraform-module/dev.tfvars' - To create the resource. You will need to change the `tfvars` file between dev and prod

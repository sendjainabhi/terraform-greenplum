# Terraform-Greenplum-AWS 

This Terraform module will help users/customers to quickly build the Greenplum infra on AWS. 

This module will create following AWS resources for Greenplum(GP) deployment on AWS
  - VPC 
  - Subnets
  - Security group
  - 1 GP coordinator(cdw) ec2 node by default.You can add another GP coordinator node by modifying the configuration on `variables.tf` property `instances`.
  - 3 segment ec2 nodes by default. You can control the count of segment nodes by modifying the configuration `variables.tf` property `count_sdw`. To modify the segments nodes configuration you can modify the property `instances-sdw`
   

## Pre-requisite 
  - Terraform cli
  - AWS credentials 

## Instructions to execute terraform module for Greenplum
 
1. Download the terraform code in local machine and change the directory to `cd \terraform-aws` 

2. Set the AWS environment variables.Set the AWS region in `main.tf` provider property. 
    ```
        export AWS_ACCESS_KEY_ID=""
        export AWS_SECRET_ACCESS_KEY=""
        export AWS_SESSION_TOKEN=""
    ```
   
3. Initialize Terraform:
 - Use the `terraform init` command to initialize the working directory. This downloads the necessary provider plugins and sets up the environment.
 - Run the command from the directory containing your Terraform configuration files. 

4. Plan Your Infrastructure Changes:
 - Use the `terraform plan` command to create an execution plan. This shows you what changes Terraform will make to your infrastructure.
 - Review the plan carefully to ensure it matches your expectations

5. Apply the Changes:
 - Use the `terraform apply` command to apply the planned changes to your infrastructure.
 - Terraform will prompt you for confirmation before applying the changes. 

6. Destroy Infrastructure (Optional):
 - Use the `terraform destroy` command to remove the infrastructure you created.
 - This command will prompt for confirmation before deleting any resources. 

# Terraform AWS EC2 Deployment

This project contains Terraform scripts to deploy an EC2 instance on AWS.

## Prerequisites

- Terraform installed (version 1.2.0 or higher)
- AWS account with appropriate permissions
- AWS access key and secret key

## Setup

1. Clone this repository
2. Create a `terraform.tfvars` file with your AWS credentials:
   ```
   aws_region     = "ap-south-1"  # Change to your preferred region
   aws_access_key = "YOUR_ACCESS_KEY"
   aws_secret_key = "YOUR_SECRET_KEY"
   ```

**Important:** Never commit your `terraform.tfvars` file to version control. It contains sensitive credentials.

**Note:** If you change the AWS region, you must also update the AMI ID in the EC2 resource as AMI IDs are region-specific. You can find the appropriate AMI ID for your region using the [AWS EC2 AMI finder tool](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/finding-an-ami.html#finding-quick-start-ami).

## Terraform Commands

### Initialize

```
terraform init
```

This command initializes the working directory, installs providers, and prepares your environment.

### Plan

```
terraform plan
```

This command creates an execution plan showing what actions Terraform will take when applied. It's a preview of changes without making any actual modifications.

### Apply

```
terraform apply
```

This command applies the changes required to reach the desired state of the configuration. You'll be prompted to confirm before any changes are made. Use `terraform apply -auto-approve` to skip confirmation.

### Destroy

```
terraform destroy
```

This command destroys all resources created by your Terraform configuration. Use with caution as this action is irreversible.

## Security Best Practices

- Store credentials securely, never in version control
- Consider using AWS profiles or environment variables instead of hardcoded credentials
- Rotate access keys regularly
- Use IAM roles with least privilege principles

## Additional Resources

- [Terraform AWS Provider Documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)
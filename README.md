# Purpose

Demonstrate how to use Terraform to create a Key Vault and Key Vault Secret.

It will take a local environment variable called TF_VAR_my_test_variable and upload the value into a Key Vault Secret called my_test_variable.

# Prerequisites

- Azure CLI
- Terraform CLI
- Azure Subscription

# Setup Azure CLI

1. Login to Azure using the Azure CLI

    ```bash
    az login
    ```
2. Set the subscription. e.g. for azure-sandbox-field-eng

Can be done during the az login process, or after using:

    ```bash
    az account set --subscription edd4cc45-85c7-4aec-8bf5-648062d519bf
    ```
# Run this terraform project

1. Clone this repository
2. Run `terraform init -upgrade`
3. Run `export TF_VAR_my_test_variable="your_secret_value"` : This will set the value for the keyvault secret created by this terraform project. In Azure Devops, this would be set via a variable group.
4. Run `terraform plan`
5. Run `terraform apply`

Then check the Key Vault in the Azure Portal to see the secret.

# Cleanup

Run `terraform destroy` to clean up all resources created by this terraform project.


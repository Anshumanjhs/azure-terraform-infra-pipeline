# Azure Infra Deployment Using Terraform
Note that this is intended to be a demonstration and it **does not** set up a production-quality, well-tuned and highly available environment. It is intended to be a demonstration and provide a quick-start
for anyone who wants to try the functionality of such a setup.

This demonstrates the deployment of infrastructure on Azure.

# Requirements
1. terraform have to be installed on the machine to run this code.
2. subcription details for Azure, this can be setup using the azure cli, when login to a device is done through the shell, only the subscription_id and client_id will be required to run the terraform scripts.
```
    subscription_id = "xxxxxxxx"
    client_id       = "xxxxxxxx"
```
3. ssh_keys - generate ssh keys for logging to the servers once they have been created
4. variables.tf - variables defined in this file are for testing purposes only and these can be changed.


# Tools
## 1. Terraform
Best practice are followed by separating the resources into different terraform files
1. main.tf - VMs to be deployed
2. variables.tf - variables used in creating the enviroment
3. security.tf - security rules and groups being applied
4. storage.tf - storaged being used (EBS Volumes)
5. network.tf - network components(VPC,subnets and gateways)
7. database.tf - databases(RDS)
8. loadbalancer.tf - ELBs 
6. output.tf - example output

# Run the terraform

```
    terraform validate
    terraform init -input=false 
    terraform plan -out=tfplanefs 
    terraform apply -input=false tfplanefs 
    terraform destroy 
```

# Missing tests
This is missing tests not built into terraform code

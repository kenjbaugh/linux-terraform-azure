# linux-terraform-azure
Terraform configuration for setting up dev environment in Azure

Created the following resources in an Azure dev account using Terraform in provided main.tf file
  1. Set Azure as the provider
  2. Resource Group: Deployed in the West US 2 region
  3. Virtual Network: Only configured a single address space for the virtual network in a list
  4. Subnet: Referenced the configured virtual network within a list with a single subnet
  5. Network Security Group: Configured a network security group within the specified dev environment resource group, and also added a network security rule linked to the configured subnet to only accept incoming connections on TCP port 22 for SSH used for remotely accessing an Ubuntu Linux machine
  6. Public IP Address: Set for the configuration of a dynamically allocated IP address to be determined only after the resource has been deployed in Azure
  7. Network Interface: Used for configuring a single network interface card within the dev environment resource group; Also configured to set an internal dynamically allocated IP address that will be assigned to the Ubuntu Linux virtual machine within the previously configured subnet
  8. Linux Virtual Machine: Used for configuring the size and an admin account for the Linux virtual machine image in the West US 2 region within the dev resource group
  9. Admin SSH Key: Created an RSA SSH key pair on my local machine and added the folder path to the generated public key file with the specified user account previously configured in the Linux Virtual Machine resource
  10. Operating System Disk: For setting disk properties for the virtual machine
  11. Virtual Machine Image Reference: Configured for the Linux machine to be Ubuntu on version 6.04-LTS

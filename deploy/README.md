# Deploy the solution

In this section you will provision all Azure resources required to complete labs. We will use a pre-defined ARM template with the definition of all Azure services used to ingest, store, process and visualize data.

The ARM template (template-latest.json) is used to provision the SQL VM migration to Azure SQL Managed Instance PoC.

## Instructions

Right-click or `Ctrl + click` the button below to open the Azure Portal in a new window. This will redirect you to the Custom Deployment wizard in the Azure Portal.

Select the Azure subscription that you would like to use for the lab.
Specify a name for the resource group. The template will deploy 20 Azure resources in a resource group.
Specify the region for the resource group.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Fsql_1click_pocs%2Finitial-draft%2Fdeploy%2Fdeploy.json)

## Deployment diagram

![resource-visualizer](../media/resource-visualizer.png)

## Azure Resources
The template provisions the following resources in the Azure subscription

- Azure Resource Group
- Azure Storage Account
- Azure SQL Managed Instance
- VNet for Azure SQL Managed Instance
- NSG for Azure SQL Managed Instance
- Virtual network traffic routing
- Azure SQL VM
- Network interface for Azure SQL VM
- VNet for Azure SQL VM
- Public IP for Azure SQL VM
- NSG for Azure SQL VM
- JumpBox VM
- Network interface for JumpBox VM
- VNet for JumpBox VM
- NSG for JumpBox VM
- Public IP for JumpBox VM

> [!IMPORTANT]
> Please note that it takes 6 to 8 hours approximately to provision all these resources in an Azure subscription.

Some of the Azure services provisioned require a globally unique name and a “suffix” has been added to their names to ensure uniqueness.

| Azure Service | Name   | Pricing Tier    | How to |
|:----          |:----- | :----   |:----- |
| Resource Group | 1clickPoC |   | [Create a Resource Group](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal#create-resource-groups)
| Storage Account | storage*suffix* |    |[Create a storage account](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-portal)|
| SQL Server on Azure VM| sqlvm-*suffix* | Standard_D8s_v3 |[Provision SQL Server on Azure VM](https://learn.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/create-sql-vm-portal?view=azuresql) |
| Azure SQL Managed Instance | sqlmi-*suffix*| GP_Gen5 8vCore|[Create an Azure SQL Managed Instance](https://learn.microsoft.com/en-us/azure/azure-sql/managed-instance/instance-create-quickstart?view=azuresql)|

### Credential

|  | Admin User Name   | Password    |
|:----          |:----- | :----   |
| SQL VM | sqladmin | My\$upp3r\$ecret |
| Azure SQL MI | sqladmin | My\$upp3r\$ecret |
| JumpBox VM | sqladmin | My\$upp3r\$ecret |

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.

## Page Navigator

[Index: Table of Contents](../index.md)

[Prev: SQL VM migration to Azure SQL Managed Instance POC](../README.md)

[Next: Assessment](../assessment/README.md)

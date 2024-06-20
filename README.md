# Contact Database Application

This project is a Contact Database Application designed to manage contact information. It is built to run on Azure, leveraging Azure App Services for hosting the web application and Azure SQL Database for storing contact data.

## Architecture

The application is designed with a simple architecture that includes:

- **Azure App Service**: Hosts the web application.
- **Azure SQL Database**: Stores the contact information.

## Deployment

The deployment of this application to Azure is managed through an Azure Resource Manager (ARM) template. The ARM template allows for the declarative setup of all Azure resources needed by the application.

### ARM Template Overview

The ARM template included in this project (`deploy.json`) defines the following resources:

- **Azure App Service Plan**: Specifies the hosting plan for the Azure App Service. This determines the pricing tier and capabilities of the hosting environment.
- **Azure App Service**: The web application hosting environment.
- **Azure SQL Server**: The SQL server instance.
- **Azure SQL Database**: The database where contact information is stored.

### Parameters

The ARM template uses parameters to allow customization of the deployment without changing the template itself. The parameters include:

- `appName`: The name of the Azure App Service.
- `appServicePlanName`: The name of the Azure App Service Plan.
- `sqlServerName`: The name of the Azure SQL Server.
- `sqlDatabaseName`: The name of the Azure SQL Database.
- `location`: The Azure region where the resources will be deployed.

A `parameters.json` file is used to provide values for these parameters during deployment.

### Deployment Steps

1. **Prerequisites**: Ensure you have the Azure CLI installed and are logged in to your Azure account.

2. **Validate the ARM Template**:

```bash
	az group deployment validate --resource-group <YourResourceGroupName> --template-file deploy.json --parameters @parameters.json
```

3. **Deploy the ARM Template**:

    

Replace `<YourResourceGroupName>` with the name of your Azure resource group.

## Security Considerations

- Ensure that the SQL Server administrator password is strong and securely managed. Consider using Azure Key Vault for storing secrets.
- Review the Azure App Service and Azure SQL Database pricing tiers and adjust them according to your budget and performance requirements.

## Conclusion

This project demonstrates a simple yet effective way to deploy a Contact Database Application to Azure using an ARM template. By leveraging Azure services, the application benefits from the scalability, security, and reliability of Azure.

---
title: "CommvaultSecurityIQ (using Azure Functions) connector for Microsoft Sentinel"
description: "Learn how to install the connector CommvaultSecurityIQ (using Azure Functions) to connect your data source to Microsoft Sentinel."
author: cwatson-cat
ms.topic: generated-reference
ms.date: 11/20/2024
ms.service: microsoft-sentinel
ms.author: cwatson
ms.collection: sentinel-data-connector
---

# CommvaultSecurityIQ (using Azure Functions) connector for Microsoft Sentinel

This Azure Function enables Commvault users to ingest alerts/events into their Microsoft Sentinel instance. With Analytic Rules,Microsoft Sentinel can automatically create Microsoft Sentinel incidents from incoming events and logs.

This is autogenerated content. For changes, contact the solution provider.

## Connector attributes

| Connector attribute | Description |
| --- | --- |
| **Application settings** | apiUsername<br/>apipassword<br/>apiToken<br/>workspaceID<br/>workspaceKey<br/>uri<br/>logAnalyticsUri (optional)(add any other settings required by the Function App)Set the <code>uri</code> value to: <code>&lt;add uri value&gt;</code> |
| **Azure function app code** | Add%20GitHub%20link%20to%20Function%20App%20code |
| **Log Analytics table(s)** | CommvaultSecurityIQ_CL<br/> |
| **Data collection rules support** | Not currently supported |
| **Supported by** | [Commvault](https://www.commvault.com/support) |

## Query samples

**Last 10 events/alerts **

   ```kusto
CommvaultSecurityIQ_CL 

   | where TimeGenerated > ago(24h) 

   | limit 10
   ```



## Prerequisites

To integrate with CommvaultSecurityIQ (using Azure Functions) make sure you have: 

- **Microsoft.Web/sites permissions**: Read and write permissions to Azure Functions to create a Function App is required. [See the documentation to learn more about Azure Functions](/azure/azure-functions/).
- **Commvault Environment Endpoint URL**: Make sure to follow the documentation and set the secret value in KeyVault
- **Commvault QSDK Token**: Make sure to follow the documentation and set the secret value in KeyVault


## Vendor installation instructions


> [!NOTE]
   >  This connector uses Azure Functions to connect to a Commvault Instance to pull its logs into Microsoft Sentinel. This might result in additional data ingestion costs. Check the [Azure Functions pricing page](https://azure.microsoft.com/pricing/details/functions/) for details.


>**(Optional Step)** Securely store workspace and API authorization key(s) or token(s) in Azure Key Vault. Azure Key Vault provides a secure mechanism to store and retrieve key values. [Follow these instructions](/azure/app-service/app-service-key-vault-references) to use Azure Key Vault with an Azure Function App.


**STEP 1 - Configuration steps for the Commvalut QSDK Token**

[Follow these instructions](/cloud-app-security/api-authentication) to create an API Token.


**STEP 2 - Choose ONE from the following two deployment options to deploy the connector and the associated Azure Function**

>**IMPORTANT:** Before deploying the CommvaultSecurityIQ data connector, have the Workspace ID  and Workspace Primary Key (can be copied from the following), as well as the Commvault Endpoint URL and QSDK Token, readily available.




**Option 1 - Azure Resource Manager (ARM) Template**

Use this method for automated deployment of the Commvault Security IQ data connector.

1. Click the **Deploy to Azure** button below. 

	[![Deploy To Azure](https://aka.ms/deploytoazurebutton)](https://aka.ms/sentinel-CommvaultSecurityIQ-azuredeploy)
2. Select the preferred **Subscription**, **Resource Group** and **Location**. 
3. Enter the **Workspace ID**, **Workspace Key**, **API Username**, **API Password**, 'and/or Other required fields'. 
>Note: If using Azure Key Vault secrets for any of the values above, use the`@Microsoft.KeyVault(SecretUri={Security Identifier})`schema in place of the string values. Refer to [Key Vault references documentation](/azure/app-service/app-service-key-vault-references) for further details. 
4. Mark the checkbox labeled **I agree to the terms and conditions stated above**. 
5. Click **Purchase** to deploy.


**Option 2 - Manual Deployment of Azure Functions**

 Use the following step-by-step instructions to deploy the CommvaultSecurityIQ data connector manually with Azure Functions.

1. Create a Function App

1.  From the Azure Portal, navigate to [Function App](https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Web%2Fsites/kind/functionapp).
2. Click **+ Add** at the top.
3. In the **Basics** tab, ensure Runtime stack is set to **'Add Required Language'**. 
4. In the **Hosting** tab, ensure **Plan type** is set to **'Add Plan Type'**.
5. 'Add other required configurations'. 
5. 'Make other preferable configuration changes', if needed, then click **Create**.

2. Import Function App Code

1. In the newly created Function App, select **Functions** from the navigation menu and click **+ Add**.
2. Select **Timer Trigger**.
3. Enter a unique Function **Name** in the New Function field and leave the default cron schedule of every 5 minutes, then click **Create Function**.
4. Click on the function name and click **Code + Test** from the left pane.
5. Copy the **Function App Code** and paste into the Function App `run.ps1` editor.
6. Click **Save**.

3. Configure the Function App

1. In the Function App screen, click the Function App name and select **Configuration**.
2. In the **Application settings** tab, select **+ New application setting**.
3. Add each of the following 'x (number of)' application settings individually, under Name, with their respective string values (case-sensitive) under Value: 
		apiUsername
		apipassword
		apiToken
		workspaceID
		workspaceKey
		uri
		logAnalyticsUri (optional)
(add any other settings required by the Function App)
Set the `uri` value to: `<add uri value>` 
>Note: If using Azure Key Vault secrets for any of the values above, use the`@Microsoft.KeyVault(SecretUri={Security Identifier})`schema in place of the string values. Refer to [Azure Key Vault references documentation](/azure/app-service/app-service-key-vault-references) for further details.
 - Use logAnalyticsUri to override the log analytics API endpoint for dedicated cloud. For example, for public cloud, leave the value empty; for Azure GovUS cloud environment, specify the value in the following format: `https://<CustomerId>.ods.opinsights.azure.us`. 
4. Once all application settings have been entered, click **Save**.



## Next steps

For more information, go to the [related solution](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/commvault.microsoft-sentinel-solution-commvaultsecurityiq?tab=Overview) in the Azure Marketplace.

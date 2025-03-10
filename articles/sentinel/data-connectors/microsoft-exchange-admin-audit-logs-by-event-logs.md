---
title: "Microsoft Exchange Admin Audit Logs by Event Logs connector for Microsoft Sentinel"
description: "Learn how to install the connector Microsoft Exchange Admin Audit Logs by Event Logs to connect your data source to Microsoft Sentinel."
author: cwatson-cat
ms.topic: generated-reference
ms.date: 11/20/2024
ms.service: microsoft-sentinel
ms.author: cwatson
ms.collection: sentinel-data-connector
---

# Microsoft Exchange Admin Audit Logs by Event Logs connector for Microsoft Sentinel

[Option 1] - Using Azure Monitor Agent - You can stream all Exchange Audit events from the Windows machines connected to your Microsoft Sentinel workspace using the Windows agent. This connection enables you to view dashboards, create custom alerts, and improve investigation. This is used by Microsoft Exchange Security Workbooks to provide security insights of your On-Premises Exchange environment

This is autogenerated content. For changes, contact the solution provider.

## Connector attributes

| Connector attribute | Description |
| --- | --- |
| **Log Analytics table(s)** | Event<br/> |
| **Data collection rules support** | Not currently supported |
| **Supported by** | [Community](https://github.com/Azure/Azure-Sentinel/issues) |

## Query samples

**All Audit logs**

   ```kusto
Event 
   | where EventLog == 'MSExchange Management' 
   | sort by TimeGenerated
   ```



## Prerequisites

To integrate with Microsoft Exchange Admin Audit Logs by Event Logs make sure you have: 

- ****: Azure Log Analytics will be deprecated, to collect data from non-Azure VMs, Azure Arc is recommended. [Learn more](/azure/azure-monitor/agents/azure-monitor-agent-install?tabs=ARMAgentPowerShell,PowerShellWindows,PowerShellWindowsArc,CLIWindows,CLIWindowsArc)
- **Detailed documentation**: >**NOTE:** Detailed documentation on Installation procedure and usage can be found [here](https://aka.ms/MicrosoftExchangeSecurityGithub)


## Vendor installation instructions


> [!NOTE]
   >  This solution is based on options. This allows you to choose which data will be ingest as some options can generate a very high volume of data. Depending on what you want to collect, track in your Workbooks, Analytics Rules, Hunting capabilities you will choose the option(s) you will deploy. Each options are independent for one from the other. To learn more about each option: ['Microsoft Exchange Security' wiki](https://aka.ms/ESI_DataConnectorOptions)

>This Data Connector is the **option 1** of the wiki.

1. Download and install the agents needed to collect logs for Microsoft Sentinel

Type of servers (Exchange Servers, Domain Controllers linked to Exchange Servers or all Domain Controllers) depends on the option you want to deploy.


2. [Option 1] MS Exchange Management Log collection - MS Exchange Admin Audit event logs by Data Collection Rules

The MS Exchange Admin Audit event logs are collected using Data Collection Rules (DCR) and allow to store all Administrative Cmdlets executed in an Exchange environment.



> [!NOTE]
   >  This data connector depends on a parser based on a Kusto Function to work as expected. Parsers are automatically deployed with the solution. Follow the steps to create the Kusto Functions alias : [**ExchangeAdminAuditLogs**](https://aka.ms/sentinel-ESI-ExchangeCollector-ExchangeAdminAuditLogs-parser)




## Next steps

For more information, go to the [related solution](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/microsoftsentinelcommunity.azure-sentinel-solution-exchangesecurityinsights?tab=Overview) in the Azure Marketplace.

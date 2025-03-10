---
title: Availability zone migration guidance overview for Microsoft Azure products and services
description: Availability zone migration guidance overview for Microsoft Azure products and services
author: anaharris-ms
ms.service: azure
ms.subservice: azure-availability-zones
ms.topic: conceptual
ms.date: 11/08/2022
ms.author: anaharris
ms.custom: subject-reliability
---

# Availability zone migration guidance overview for Microsoft Azure products and services

Azure services that support availability zones, including zonal and zone-redundant offerings, are continually expanding.  For that reason, resources that don't currently have availability zone support, may have an opportunity to gain that support. The Migration Guides section offers a collection of guides for each service that requires certain procedures in order to move a resource from non-availability zone support to availability support. You'll find information on prerequisites for migration, download requirements, important migration considerations and recommendations.

The table below lists each product that offers migration guidance and/or information. 

## Azure services migration guides

### ![An icon that signifies this service is foundational.](media/icon-foundational.svg) Foundational services 

| **Products**  | 
| --- | 
| [Azure Application Gateway (V2)](migrate-app-gateway-v2.md) |
| [Azure Backup and Azure Site Recovery](migrate-recovery-services-vault.md)  | 
| [Azure ExpressRoute](/azure/expressroute/expressroute-howto-gateway-migration-portal) |
| [Azure Functions](migrate-functions.md)|
| [Azure Load Balancer](migrate-load-balancer.md)|
| [Azure Service Fabric](migrate-service-fabric.md)  | 
| [Azure SQL Database](migrate-sql-database.md) |
| [Azure Storage account: Blob Storage, Azure Data Lake Storage, Files Storage](migrate-storage.md) |
| [Azure Storage: Managed Disks](migrate-vm.md)|
| [Azure Virtual Machines and Azure Virtual Machine Scale Sets](migrate-vm.md)|  


\*VMs that support availability zones: AV2-series, B-series, DSv2-series, DSv3-series, Dv2-series, Dv3-series, ESv3-series, Ev3-series, F-series, FS-series, FSv2-series, and M-series.

### ![An icon that signifies this service is mainstream.](media/icon-mainstream.svg) Mainstream services

| **Products**   | 
| --- | 
| [Azure API Management](migrate-api-mgt.md)|
| [Azure App Configuration](migrate-app-configuration.md)|
| [Azure App Service](reliability-app-service.md#availability-zone-support)|
| [Azure Batch](reliability-batch.md#availability-zone-migration)|
| [Azure Cache for Redis](migrate-cache-redis.md)|
| [Azure AI Search](migrate-search-service.md)|
| [Azure Container Apps](reliability-azure-container-apps.md#availability-zone-migration)|
| [Azure Container Instances](migrate-container-instances.md)|
| [Azure Container Registry](/azure/container-registry/zone-redundancy?toc=/azure/reliability) |
| [Azure Cosmos DB](/azure/cosmos-db/high-availability?toc=/azure/reliability) |
| [Azure Database for MySQL - Flexible Server](migrate-database-mysql-flex.md)|
| [Azure Database for PostgreSQL](/azure/postgresql/flexible-server/how-to-manage-high-availability-portal#enable-high-availability-during-server-creation)|
| [Azure Elastic SAN](reliability-elastic-san.md#availability-zone-migration)|
| [Azure Functions](reliability-functions.md#availability-zone-migration)|
| [Azure HDInsight](reliability-hdinsight.md#availability-zone-migration)|
| [Azure Kubernetes Service](/azure/aks/availability-zones?toc=/azure/reliability)|
| [Azure Logic Apps](/azure/logic-apps/set-up-zone-redundancy-availability-zones?tabs=standard&toc=/azure/reliability)|
| [Azure Monitor: Log Analytics](migrate-monitor-log-analytics.md)|
| [Azure Service Bus](/azure/service-bus-messaging/service-bus-outages-disasters#availability-zones)|
| [Azure SQL Managed Instance](migrate-sql-managed-instance.md)|



## Workload and general guidance
| **Workloads**   | 
| --- | 
| [Azure Kubernetes Service (AKS) and MySQL Flexible Server](migrate-workload-aks-mysql.md)|

## Next steps

> [!div class="nextstepaction"]
> [Azure services with availability zones](availability-zones-service-support.md)

> [!div class="nextstepaction"]
> [Azure regions with availability zones](availability-zones-region-support.md)

> [!div class="nextstepaction"]
> [Availability of service by category](availability-service-by-category.md)

> [!div class="nextstepaction"]
> [Microsoft commitment to expand Azure availability zones to more regions](https://azure.microsoft.com/blog/our-commitment-to-expand-azure-availability-zones-to-more-regions/)

> [!div class="nextstepaction"]
> [Build solutions for high availability using availability zones](/azure/architecture/high-availability/building-solutions-for-high-availability)

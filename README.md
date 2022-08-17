# MICROSOFT USE CASE DATA MORDERNIZATION:-

| __IN-HOUSE TECHNOLOGY STACK FOR THE USE CASE:-__ |
| --------- |
| .NET Application. |
| SQL Server 2008 R2 (Dedicated Server for Database and Datawarehouse. |
| SQL Server Analysis Services (SSAS - Tabular) - Component of Microsoft SQL Server database used as Analytical Processing and Data Mining Tool to Analyze information spread out across multiple databases, or in tables or files. |
| SQL Server Integration Services (SSIS) - Component of Microsoft SQL Server database software that can be used for Data Extraction, Transformation, and Loading. |
| SQL Server Reporting Services (SSRS) - Component of Microsoft SQL Server database software that can be used to prepare and deliver a variety of interactive reports. |

| __NOTES:-__ |
| --------- |

| __DIFFERENCE BETWEEN DATABASE AND DATAWAREHOUSE:-__ |
| --------- |
| __DATABASE:__ Any collection of data organized for storage, accessibility, and retrieval. |
| __DATAWAREHOUSE:__ Type of database that integrates copies of transaction data from different source systems and provisions them for analytical use. |

| __OLTP (ONLINE TRANSACTION PROCESSING):-__ |
| --------- |
| Azure SQL Managed Instance |

| __OLAP (ONLINE ANALYTICAL PROCESSING):-__ |
| --------- |
| Azure SQL Analysis Services |


| __EQUIVALENT AZURE SERVICES IN COMPARISON TO IN-HOUSE TECHNOLOGY STACK FOR THE USE CASE:-__ |
| --------- |
| __Azure Web App (App Services - Windows)__ - To Host .Net Application. |
| __Azure SQL Managed Instance__ - For Hosting Database. |
| __Azure Datalake Store (ADLS)__ - For Datawarehouse. |
| __Azure Analysis Services/PowerBI Premium__ - For Tabular Cube Model. |
| __Azure-SSIS Integration runtime in Azure Data Factory__ - For SQL Server Integration Services.  |
| __PowerBI__ - For Prepare and Deliver Reports. |


| __REFERENCE DOCUMENTATION ON THE ABOVE SELECTED SERVICES:-__ |
| --------- |
| [Azure WebApp](https://docs.microsoft.com/en-us/azure/app-service/overview) |
| [Azure SQL Managed Instance](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview?view=azuresql) |
| [Azure Datalake Store](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction) |
| [Azure Analysis Services](https://docs.microsoft.com/en-us/azure/analysis-services/analysis-services-overview) |
| [PowerBI Premium](https://docs.microsoft.com/en-us/power-bi/enterprise/service-premium-what-is) |
| [Azure-SSIS Integration runtime in Azure Data Factory](https://docs.microsoft.com/en-us/azure/data-factory/create-azure-ssis-integration-runtime) |
| [PowerBI](https://docs.microsoft.com/en-us/power-bi/) |

| __REFERENCE ARCHITECTURE:-__ |
| --------- |
| ![image](https://user-images.githubusercontent.com/29681063/184550726-658cdb1f-88fe-4a6d-8f06-9060c115685b.png) |


| __BILL OF MATERIAL (BOM):-__ |
| --------- |

| __AZURE SERVICES__ | __PURPOSE__ |
| --------- | --------- |
| __Resource Group__ | Placeholder for all Azure Resources. |
| __Azure Key Vault__ | To Store Credentials. |
| __Log Analytics__ | To Store and Query Logs, Monitoring and Incident Management. |
| __Storage Account__ | To Store and Archive Logs, Backup.... |
| __Managed Identity__ | For Authentication and Authorization. |
| __App Service Plan (Windows)__ | Defines the Compute Resources for a Webapp. |
| __App Services (WebApp)__ | For Hosting Web Application, REST APIs and Mobile Backend. |
| __Application Insights__ | To Monitor Application deployed in App Services. |
| __Azure SQL Managed Instance__ | PaaS SQL Database. |
| __Azure Data Lake Store__ | Storage for Big Data Analytic Workloads. |
| __Azure Analysis Services__ | PaaS Data Model. |
| __Azure-SSIS Integration Runtimes In Azure Data Factory__ | Microsoft Managed Virtual Machines running SSIS Engine which allows to Natively run SSIS Packages.  |
| __PowerBI__ | SaaS - Data Analysis Tool. |
|  __PowerBI Premium Gen2__| Data Analysis Including Azure Analysis Services Capabilities. |


| __FEATURE COMPARISON (AZURE ANALYSIS SERVICES VS POWERBI PREMIUM GEN2:-__ |
| --------- |
| Reference Documentation Can be Found [Here](https://docs.microsoft.com/en-us/power-bi/guidance/migrate-azure-analysis-services-to-powerbi-premium) |
| __Important Pointers Screenshot:-__ |
| ![image](https://user-images.githubusercontent.com/29681063/185004812-2d805fdf-ae80-4c89-9977-d7a0995966b3.png) |
| ![3](https://user-images.githubusercontent.com/29681063/185005183-83d40269-fe40-4878-aed9-6e58a424eae6.jpg) |
| ![4](https://user-images.githubusercontent.com/29681063/185005709-78702c8a-f35b-42b3-9c44-e24f4d8d4fa8.jpg) |
| ![5](https://user-images.githubusercontent.com/29681063/185006000-fbf1d122-7d2a-4767-a44d-23eb979f024b.jpg) |

| __HOW TO MIGRATE DATA FROM INHOUSE SQL SERVER TO AZURE SQL MANAGED INSTANCE:-__ |
| --------- |
| This Can be Achieved using DMA - Data Migration Assistant. |

| __DMA CAPABILITIES:-__ |
| --------- |
| Migrate an on-premises SQL Server instance to a modern SQL Server instance (On-Prem or Azure).  |
| Discovers the compatibility issues that can block Migration to Target SQL Instance. Provides Recommendations to help resolve issues. |
| Detects partially supported or unsupported features. Provides Recommendations to help resolve issues. |
| Discover New Features in the Target SQL Instance that the database can benefit from after an upgrade. |
| After a successful migration, applications can connect to the target SQL Server databases seamlessly. |

| __IMPORTANT NOTE: DMA__ |
| --------- |
| DMA does not support database migrations to Azure SQL Managed Instance. |
| Azure SQL Migration Extension for Azure Data Studio supports both online and offline database migrations to Azure SQL Managed Instance. |


| __SECURITY AND VULNERABILITY MANAGEMENT OF AZURE SQL MANAGED INSTANCE:-__ | 
| --------- |
| Setting up Private Endpoint. | 
| Configure Required Firewall Rules. | 
| Setting up Azure Active Directory Admin (It can be an AAD User or AAD Group). |
| Configuring Required Role Based Access Control(RBAC). |
| Setting up Audit and Vulnerability Assessment in Azure SQL Managed Identity and Populating the Report in Storage Account With Email Notification.
| Web Application running on Azure App Services, if needed to Connect to Azure SQL managed Instance, it will be using the System/User Assigned Managed Identity of the App Service rather than local SQL Username and Password. |


| __SCALING:-__ | 
| --------- |

| __AZURE SERVICES:-__ | __SCALE OPTIONS:-__ | 
| --------- | --------- |
| Azure Web App | Scaling happens on App Service Plan to which App Service is associated. 1) Scale Up (Vertical Scaling) - Change the Pricing Tier to Increase vCPU and Memory. 2) Scale out (Horizontal Scaling) - Increase the Instance Count. |
| Azure Analysis Services | 1) Scale QPUs (Query Processing Unit) - Pricing Tier 2) Scale Query Replica (Available in Standard Pricing Tier) |
| Azure SQL Managed Instance  | Compute and Storage of the SQL Database Can be Scaled. |


| __PROPOSED NO. OF ENVIRONMENTS:-__ |
| --------- |
| DEV |
| UAT |
| PROD |

| __PROPOSED GUIDELINES FOR ENVIRONMENTS:-__ |
| --------- |
| Azure Resources SKU of DEV Environment will be on the lower side as compared to UAT and PROD. |
| UAT and PROD will have like to like configuration with the sole purpose that if there is any issue in production, it can be reproduced in UAT. |


| __PROPOSED GUIDELINES FOR MIGRATION:-__ |
| --------- |
| POC (Proof-of-Concept) or MVP (Minimal-Viable-Product) based on the above requirement gathering - Focus on Functional Testing rather than Performance Testing during the POC phase. |
| If MVP is successful, we will create the Non-Prod Environment( DEV, UAT) |
| Performance Testing will be done on the Non-Prod Environment (UAT) |
| Based on the success criteria defined, an equivalent like to like Production environment will be deployed. |


| __PROPOSED TIMELINES FOR MIGRATION:-__ |
| --------- |
| __POC:__ 1 Month |
| __Non-Prod (DEV and UAT) BUILD, DEPLOY and FUNCTIONAL TESTS:__ 2 Months |
| __Non-Prod (DEV and UAT) PERFORMANCE TESTS and MIGRATION:__ 1 Month |
| __Prod BUILD, DEPLOY and PERFORMANCE TESTS:__ 1 Month |
| __GOLIVE Planning and CUTOVER:__ 1 Month |


| __CALLING OUT EXCEPTIONS:-__ |
| --------- |
| Customer should have Robust Network Infrastructure - Azure __HUB AND SPOKE__. Building Hub and Spoke is __OUT OF SCOPE.__ | 
| Customer should have Resilient Bandwidth Connecting Azure and In-House Datacentre. Setting up this connectivity is __OUT OF SCOPE.__ |
| Customer's .NET Application Should be easily deployed in App Services (__No Refactor Required__).
| Azure DevOps is the CI/CD platform. |


| __BUSINESS CONTINUITY AND DISASTER RECOVERY (BCDR):-__ |
| --------- |
| In the peered region, a subset of the environment(application infrastructure) should be created. Why Subset? 1.1. During a Disaster, the Application should be running with Limited Functionality. 1.2. Cost - Important Factor - As this will be a cold site (an infrastructure which may be used in the Event of Disaster or DR Tests.) |
| Dotnet Application Running on App services (Application code resides in Azure Git and can be deployed immediately using Azure DevOps pipeline) |
| Azure SQL Managed Instance with Geo-Replication. |
| Azure Analysis Services Backup in Storage Account Residing in Peered Region. |
| Azure-SSIS Integration Runtime in Azure Data Factory Deployed in Peered Region. |


| __CUSTOMER REQUIREMENTS/NEEDS__ | __IF REQUIREMENTS HAVE BEEN MET:-__ |
| --------- | --------- |
| Migration from In-House SQL to Azure SQL Managed Instance. | Yes |
| All PaaS Service Required. | Yes |
| All Tech Stack to be Migrated to Azure. | Yes |
| If Migration can be done in 6 Months. | Yes (Considering the Exceptions called out) |
| Scalability. | Yes |
| Security and Vulnerability of Azure SQL Managed Instance. | Yes |
| BCDR (Business Continuity and Disaster Recovery) - In the event of a regional outage, we would like to be able to resume the applications within minutes and recover the data warehouse within 48 hours. | Yes |


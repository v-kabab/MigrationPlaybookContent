## Preparing for database migration

As you prepare for migrating your database to the cloud, verify that your source environment is supported and that you have addressed any prerequisites. This will help to ensure an efficient and successful migration.

### Overview

This scenario describes how to migrate a SQL Server instance to Azure SQL Database. 

### Offline versus online migrations

When you migrate SQL Server databases to Azure by using Azure Database Migration Service, you can perform an offline or an online migration. With an *offline* migration, application downtime begins when the migration starts. For an *online* migration, downtime is limited to the time required to cut over to the new environment when the migration completes. It's recommended to test an offline migration to determine whether the downtime is acceptable; if not, perform an online migration.

### Supported versions

This section describes all supported scenarios and options for an upgrade from on-premise SQL Server versions to Azure SQL Database. This information is current as of March 2019.

Details for migrations to Azure SQL Database from the following SQL Server sources are included:

* SQL Server 2005
* SQL Server 2008 and SQL Server 2008 R2
* SQL Server 2012
* SQL Server 2014
* SQL Server 2016
* SQL Server 2017

You can migrate SQL Server running on-premises or on:

* SQL Server on Virtual Machines
* Amazon Web Services (AWS) EC2
* Compute Engine (GCP)
* AWS RDS

The following data migration options are discussed:

* [Azure Database Migration Service (DMS)](https://docs.microsoft.com/azure/dms/)
* [Data Migration Assistant (DMA)](https://docs.microsoft.com/sql/dma/dma-overview?view=sql-server-2017)
* [Transactional replication](https://docs.microsoft.com/sql/relational-databases/replication/administration/enhance-transactional-replication-performance?view=sql-server-2017)
* [Bulk load](https://docs.microsoft.com/sql/t-sql/statements/bulk-insert-transact-sql?view=sql-server-2017)

Data migration options, details, and supported versions are provided in the following table.

<br>
<table width="100%">
<thead>
<tr>
<th width="20%">
<p><strong>Migration option</strong></p>
</th>
<th width="80%">
<p><strong>Purpose</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="20%">
<p>Azure Database Migration Service</p>
</td>
<td width="80%">
<p>Azure DMS supports online (minimal downtime) and offline (one time) migrations at scale to an Azure SQL Database managed instance from SQL Server 2005, SQL Server 2008 and SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016, and SQL Server 2017.</p>
</td>
</tr>
<tr>
<td width="20%">
<p>Data Migration Assistant</p>
</td>
<td width="80%">
<p>Use DMA to detect compatibility issues that can impact database functionality in your target Azure SQL Database managed instance, to recommend performance and reliability improvements, and to move the schema, data, and uncontained objects from your source server to your target server. For information about supported sources and targets, and to download the latest version of DMA, see the <a href="https://aka.ms/get-dma">Microsoft Download Center</a>.</p>
</td>
</tr>
<tr>
<td width="20%">
<p>Transactional replication</p>
</td>
<td width="80%">
<p>Transactional replication to an Azure SQL Database managed instance is supported for migrations from:</p>
<ul>
<li>SQL Server 2012 (SP2 CU8, SP3, or later)</li>
<li>SQL Server 2014 (RTM CU10 or later, or SP1 CU3 or later)</li>
<li>SQL Server 2016</li>
<li>SQL Server 2017</li>
</ul>
</td>
</tr>
<tr>
<td width="20%">
<p>Bulk load</p>
</td>
<td width="80%">
<p>Use bulk load to an Azure SQL Database managed instance for data stored in SQL Server 2005, SQL Server 2008 and SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016, and SQL Server&nbsp;2017.</p>
</td>
</tr>
</tbody>
</table>

### Overview of prerequisites

Before beginning your migration project, it is important to address the associated prerequisites for leveraging Azure Database Migration Service (DMS) for migrations. When upgrading from SQL Server on-premises or on SQL Server on Virtual Machines to Azure SQL Database, there are prerequisites associated with:

* Downloading and installing the [Data Migration Assistant (DMA)](https://www.microsoft.com/en-us/download/details.aspx?id=53595).
* Creating an instance of Azure DMS (detail in [Overview of prerequisites for using the Azure Database Migration Service](https://docs.microsoft.com/azure/dms/pre-reqs)).
* Using Azure DMS to perform online migrations (detail in [Migrate SQL Server to a single database or pooled database in Azure SQL Database online using DMS](https://docs.microsoft.com/azure/dms/tutorial-sql-server-azure-sql-online#prerequisites)).
* Using Azure DMS to perform offline migrations (detail in [Migrate SQL Server to a single database or pooled database in Azure SQL Database offline using DMS](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-azure-sql#prerequisites)).

### Migration assets from real-world engagements

For additional assistance with completing this migration scenario, please see the following resources, which were developed in support of a real-world migrations at scale.

<br>
<table width="100%">
<thead>
<tr>
<th width="20%">
<p><strong>Title/link</strong></p>
</th>
<th width="80%">
<p><strong>Description</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="20%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/Data%20Workload%20Assessment%20Model%20and%20Tool">Data Workload Assessment Model and Tool</a></p>
</td>
<td width="80%">
<p>This tool provides suggested &ldquo;best fit&rdquo; target platforms, cloud readiness, and application/database remediation level for a given workload. It offers simple, one-click calculation and report generation that greatly helps to accelerate large estate assessments by providing and automated and uniform target platform decision process.</p>
</td>
</tr>
<tr>
<td width="20%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/Bulk%20Database%20Creation%20with%20PowerShell">Bulk Database Creation with PowerShell</a></p>
</td>
<td width="80%">
<p>Three scripts that create a resource group (create_rg.ps1), SQL Server to host Azure SQL Databases (create_sqlserver.ps1), and Azure SQL Databases (create_sqldb.ps1). The scripts include loop capabilities, so you can iterate and create as many databases and SQL Servers as necessary.</p>
</td>
</tr>
<tr>
<td width="20%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/Bulk%20Schema%20Deployment%20with%20MSSQL-Scripter%20&amp;%20PowerShell">Bulk Schema Deployment with MSSQL-Scripter &amp; PowerShell</a></p>
</td>
<td width="80%">
<p>This asset creates a resource group, one or multiple SQL Servers to host one or multiple Azure SQL Databases, exports every schema from an on-premises SQL Server (or multiple SQL Servers (2005+) (or VM), and imports it to Azure SQL Database.&nbsp;</p>
</td>
</tr>
<tr>
<td width="20%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/IP%20and%20Scripts/MoveLogins">Utility to move On-Premises SQL Server Logins to Azure SQL DB</a></p>
</td>
<td width="80%">
<p>A PowerShell script that creates a T-SQL command script to re-create logins and select database users from an “on premises” SQL Server to an Azure SQL PaaS service. The tool allows the automatic mapping of Windows AD accounts to Azure AD accounts or it can do UPN lookups for each login against the on premises Windows Active Directory. The tool optionally moves SQL Server native logins as well. Custom server and database roles are scripted, as well as role membership and database role and user permissions. Contained databases are yet not supported and only a subset of possible SQL Server permissions are scripted; i.e. permissions grant with grant are not supported (complex permission trees). More details are available in the support document and the script have comments for ease of understanding.</p>
</td>
</tr>
</tbody>
</table>

**Note**: These resources were developed as part of the Data Migration Jumpstart Program (DM Jumpstart), which is sponsored by the Azure Data Group engineering team. The core charter DM Jumpstart is to unblock and accelerate complex modernization and compete data platform migration opportunities to Microsoft’s Azure Data platform. If you think your organization would be interested in participating in the DM Jumpstart program, please contact your account team and ask that they submit a nomination.

### Additional resources

* For detail on alternatives for migrating to Azure, see the white paper [Choosing your database migration path to Azure](https://aka.ms/dbmigratewp).
* [SQL migration using Azure Data Migration Service (DMS)](https://www.microsoft.com/handsonlabs/SelfPacedLabs/?storyGuid=3b671509-c3cd-4495-8e8f-354acfa09587) hands-on lab.
* Be sure to check out the [Azure Total Cost of Ownership (TCO) Calculator](https://aka.ms/azure-tco) to help estimate the cost savings you can realize by migrating your workloads to Azure.
* For a matrix of the Microsoft and third-party services and tools that are available to assist you with various database and data migration scenarios as well as specialty tasks, see the article [Service and tools for data migration](https://docs.microsoft.com/azure/dms/dms-tools-matrix).
* For options related to migrating Azure SQL Database to a managed instance, see the blog post [How to Migrate Azure SQL Database to Azure SQL Managed Instance](https://blogs.msdn.microsoft.com/azuresqldbsupport/2019/01/28/how-to-migrate-azure-sql-database-to-azure-sql-managed-instance/).

**Videos**

* For an overview of the Azure Database Migration Guide and the information it contains, see the video [How to Use the Database Migration Guide](https://azure.microsoft.com/resources/videos/how-to-use-the-azure-database-migration-guide/).
* For a walk through of the phases of the migration process and detail about the specific tools and services recommended to perform assessment and migration, see the video [Overview of the migration journey and the tools/services recommended for performing assessment and migration](https://azure.microsoft.com/resources/videos/overview-of-migration-and-recommended-tools-services/).
* For details about the pre-requirements, including Azure VNet and firewall set up, needed to create a DMS instance, see the video [How to address pre-requisites and create an instance of the Azure Database Migration Service](https://azure.microsoft.com/resources/videos/how-to-address-prerequisites-and-create-a-dms-instance/).
* For information about how to monitor an online migration and perform a migration cutover when the initial load and data sync have completed, see the video [How to monitor an online migration and perform migration cutover](https://azure.microsoft.com/resources/videos/how-to-monitor-online-migration-and-perform-cutover/).

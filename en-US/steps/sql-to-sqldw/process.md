## Migrate from SQL Server to SQL Data Warehouse

The following sections provide an overview of what's involved with migrating an existing database solution to Azure SQL Data Warehouse.

### Profile your workload

Before migrating, you should verify that SQL Data Warehouse is the best solution for your workload. SQL Data Warehouse is a distributed system designed to perform analytics on large data. Migrating to SQL Data Warehouse requires some design changes that are not difficult to understand but that might take some time to implement. If your business requires an enterprise-class data warehouse, the benefits are worth the effort. However, if you don't need the power of SQL Data Warehouse, it is more cost-effective to use [SQL Server]( https://docs.microsoft.com/en-us/sql/sql-server/sql-server-technical-documentation?view=sql-server-2017) or [Azure SQL Database](https://azure.microsoft.com/services/sql-database/).

Consider using SQL Data Warehouse when you:

* Have one or more Terabytes of data
* Plan to run analytics on substantial amounts of data
* Need the ability to scale compute and storage
* Want to save on costs by pausing compute resources when you don't need them.

Rather than SQL Data Warehouse, consider other options for operational (OLTP) workloads that have:

* High frequency reads and writes
* Large numbers of singleton selects
* High volumes of single row inserts
* Row-by-row processing needs
* Incompatible formats (JSON, XML)

### Plan the migration

After you make the decision to migrate an existing solution to SQL Data Warehouse, it is important to plan the migration before you get started.

A primary goal of planning is to ensure that your data, table schemas, and code are compatible with SQL Data Warehouse. There are some compatibility differences between your current system and SQL Data Warehouse that you will need to work around. In addition, migrating large amounts of data to Azure takes time. Careful planning will speed up the process of getting your data to Azure.

Another key goal of planning is to adjust your design to ensure that your solution takes full advantage of the high query performance that SQL Data Warehouse is designed to provide. Designing data warehouses for scale introduces unique design patterns, so traditional approaches aren't always the best. While some design adjustments can be made after migration, making changes earlier in the process will save you time later.

### Perform the migration

Performing a successful migration requires you to migrate your table schemas, code, and data. For more detailed guidance on these topics, see:

* The article [Migrate your schemas](https://docs.microsoft.com/azure/sql-data-warehouse/sql-data-warehouse-migrate-schema).
* The article [Migrate your code](https://docs.microsoft.com/azure/sql-data-warehouse/sql-data-warehouse-migrate-schema).
* The article [Migrate your data](https://docs.microsoft.com/azure/sql-data-warehouse/sql-data-warehouse-migrate-data).

### Migration assets from real-world engagements

For additional assistance with completing this migration scenario, please see the following resources, which were developed in support of a real-world migration project engagement.

<br>
<table width="100%">
<thead>
<tr style="height: 35px;">
<th style="height: 35px;" width="18%">
<p><strong>Title/link</strong></p>
</th>
<th style="height: 35px;" width="59%">
<p><strong>Description</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr style="height: 62px;">
<td style="height: 62px;" width="18%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/Data%20Workload%20Assessment%20Model%20and%20Tool">Data Workload Assessment Model and Tool</a></p>
</td>
<td style="height: 62px;" width="59%">
<p>This tool provides suggested &ldquo;best fit&rdquo; target platforms, cloud readiness, and application/database remediation level for a given workload. It offers simple, one-click calculation and report generation that greatly helps to accelerate large estate assessments by providing and automated and uniform target platform decision process.</p>
</td>
</tr>
<tr style="height: 62.2px;">
<td style="height: 62.2px;" width="18%">
<p><a href="https://azure.microsoft.com/en-us/blog/handling-data-encoding-issues-while-loading-data-to-sql-data-warehouse/">Handling Data Encoding Issues While Loading Data to SQL Data Warehouse</a></p>
</td>
<td style="height: 62.2px;" width="59%">
<p>This blog is intended to provide insight on some of the data encoding issues that you may encounter while using PolyBase to load data to SQL Data Warehouse. This article also provides some options that you can use to overcome such issues and load the data successfully.</p>
</td>
</tr>
<tr style="height: 76px;">
<td style="height: 76px;" width="18%">
<p><a href="https://aka.ms/dmj-wp-tables-sqldw">Getting table sizes in SQL DW</a></p>
</td>
<td style="height: 76px;" width="59%">
<p>One of the key tasks that an architect must perform execute is to get metrics about a new environment post-migration: collecting load times from on-premises to the cloud, collecting PolyBase load times, etc. Of these tasks, one of the most important is to determine the storage size in SQL Data Warehouse compared to the customer's current platform.</p>
</td>
</tr>
<tr style="height: 48px;">
<td style="height: 48px;" width="18%">
<p><a href="https://aka.ms/dmj-wp-netezza-mapping">Netezza to SQL DW Recommended Datatype Mapping</a></p>
</td>
<td style="height: 48px;" width="59%">
<p>This white paper describes recommended data type mapping between Netezza and Azure SQL Data Warehouse.</p>
</td>
</tr>
<tr style="height: 62px;">
<td style="height: 62px;" width="18%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/IP%20and%20Scripts/MoveLogins">Utility to move On-Premises SQL Server Logins to Azure SQL DW</a></p>
</td>
<td style="height: 62px;" width="59%">
<p>A PowerShell script that creates a T-SQL command script to re-create logins and select database users from an “on premises” SQL Server to an Azure SQL PaaS service. The tool allows the automatic mapping of Windows AD accounts to Azure AD accounts or it can do UPN lookups for each login against the on premises Windows Active Directory. The tool optionally moves SQL Server native logins as well. Custom server and database roles are scripted, as well as role membership and database role and user permissions. Contained databases are yet not supported and only a subset of possible SQL Server permissions are scripted; i.e. permissions grant with grant are not supported (complex permission trees). More details are available in the support document and the script have comments for ease of understanding.</p>
</td>
</tr>
</tbody>
</table>

**Note**: These resources were developed as part of the Data Migration Jumpstart Program (DM Jumpstart), which is sponsored by the Azure Data Group engineering team. The core charter DM Jumpstart is to unblock and accelerate complex modernization and compete data platform migration opportunities to Microsoft’s Azure Data platform. If you think your organization would be interested in participating in the DM Jumpstart program, please contact your account team and ask that they submit a nomination.

### Additional resources

* The CAT (Customer Advisory Team) has some great SQL Data Warehouse guidance published as blog postings. Be sure to take a look at their article, [Migrating data to Azure SQL Data Warehouse in practice]( https://blogs.msdn.microsoft.com/sqlcat/2016/08/18/migrating-data-to-azure-sql-data-warehouse-in-practice/), for additional guidance on migration.
* Check out the white paper [Choosing your database migration path to Azure](https://aka.ms/dbmigratewp) for additional information and recommendations.
* For a matrix of the Microsoft and third-party services and tools that are available to assist you with various database and data migration scenarios as well as specialty tasks, see the article [Service and tools for data migration](https://docs.microsoft.com/azure/dms/dms-tools-matrix).

**Videos**

* For an overview of the Azure Database Migration Guide and the information it contains, see the video [How to Use the Database Migration Guide](https://azure.microsoft.com/resources/videos/how-to-use-the-azure-database-migration-guide/).
* For a walk through of the phases of the migration process and detail about the specific tools and services recommended to perform assessment and migration, see the video [Overview of the migration journey and the tools/services recommended for performing assessment and migration](https://azure.microsoft.com/resources/videos/overview-of-migration-and-recommended-tools-services/

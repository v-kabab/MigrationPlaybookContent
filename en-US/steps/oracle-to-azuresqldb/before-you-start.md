## Preparing for database migration

As you prepare for migrating your database to the cloud, verify that your source environment is supported and that you have addressed any prerequisites. This will help to ensure an efficient and successful migration.

## Overview

This scenario describes how to migrate an Oracle instance to Azure SQL Database.

### Migration assets from real-world engagements

For additional assistance with completing this migration scenario, please see the following resources, which were developed in support of a real-world migration project engagement.

<br>
<table width="100%">
<thead>
<tr>
<th width="18%">
<p><strong>Title/link</strong></p>
</th>
<th width="59%">
<p><strong>Description</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="18%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/Data%20Workload%20Assessment%20Model%20and%20Tool">Data Workload Assessment Model and Tool</a></p>
</td>
<td width="59%">
<p>This tool provides suggested &ldquo;best fit&rdquo; target platforms, cloud readiness, and application/database remediation level for a given workload. It offers simple, one-click calculation and report generation that greatly helps to accelerate large estate assessments by providing and automated and uniform target platform decision process.</p>
</td>
</tr>
<tr>
<td width="18%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/Oracle%20Inventory%20Script%20Artifacts">Oracle Inventory Script Artifacts</a></p>
</td>
<td width="59%">
<p>This asset includes a PL/SQL query that hits Oracle system tables and provides a count of objects by schema type, object type, and status. It also provides a rough estimate of &lsquo;Raw Data&rsquo; in each schema and the sizing of tables in each schema, with results stored in a CSV format.</p>
</td>
</tr>
<tr>
<td width="18%">
<p><a href="https://github.com/Microsoft/DataMigrationTeam/tree/master/SSMA%20Assessment%20Tool">SSMA Assessment Tool</a></p>
</td>
<td width="59%">
<p>This set of resource uses a .csv file as entry (sources.csv in the project folders) to produce the xml files that are needed to run SSMA assessment in console mode. The source.csv is provided by the customer based on an inventory of existing Oracle instances. The output files are <strong>AssessmentReportGeneration_source_1.xml</strong>, <strong>ServersConnectionFile.xml</strong>, and <strong>VariableValueFile.xml</strong>.</p>
</td>
</tr>
<tr>
<td width="18%">
<p><a href="https://aka.ms/dmj-wp-ssma-oracle-errors">SSMA for Oracle Common Errors and how to fix them</a></p>
</td>
<td width="59%">
<p>With Oracle, you can assign a non-scalar condition in the WHERE clause. However, SQL Server doesn&rsquo;t support this type of condition. As a result, SQL Server Migration Assistant (SSMA) for Oracle doesn&rsquo;t&nbsp;convert queries with a non-scalar condition in the WHERE clause, instead generating an error&nbsp;O2SS0001. This white paper provides more details on the issue and ways to resolve it.</p>
</td>
</tr>
<tr>
<td width="18%">
<p><a href="https://aka.ms/dmj-wp-ssma-oracle-steps">Steps to Run SSMA for Oracle</a></p>
</td>
<td width="59%">
<p>This document is designed as a Quick Start Guide for migrating the schema and data from Oracle to Azure SQL Database by using SSMA for Oracle v7.6.0.</p>
</td>
</tr>
<tr>
<td width="18%">
<p><a href="https://aka.ms/dmj-wp-attunity">Steps to Run Attunity Replicate for Microsoft Migrations</a></p>
</td>
<td width="59%">
<p>This document is designed as a Quick Start Guide for migrating the schema and data from Oracle to Azure SQL Database by using Attunity Replicate for Microsoft Migrations tool.</p>
</td>
</tr>
<tr>
<td width="18%">
<p><a href="https://aka.ms/dmj-wp-oracle12c-linux">Setting up Oracle 12c Enterprise and Getting It Working by Using the Azure Marketplace Template</a></p>
</td>
<td width="59%">
<p>This white paper provides a step-by-step walkthrough of setting up and implementing Oracle 12c Enterprise by using the Azure Marketplace Template.</p>
</td>
</tr>
</tbody>
</table>

**Note**: These resources were developed as part of the Data Migration Jumpstart Program (DM Jumpstart), which is sponsored by the Azure Data Group engineering team. The core charter DM Jumpstart is to unblock and accelerate complex modernization and compete data platform migration opportunities to Microsoft’s Azure Data platform. If you think your organization would be interested in participating in the DM Jumpstart program, please contact your account team and ask that they submit a nomination.

## Additional resources

- Be sure to check out the [Azure Total Cost of Ownership (TCO) Calculator](https://aka.ms/azure-tco) to help estimate the cost savings you can realize by migrating your workloads to Azure.
- For a matrix of the Microsoft and third-party services and tools that are available to assist you with various database and data migration scenarios as well as specialty tasks, see the article [Service and tools for data migration](https://docs.microsoft.com/azure/dms/dms-tools-matrix).

**Videos**

- For an overview of the Azure Database Migration Guide and the information it contains, see the video [How to Use the Database Migration Guide](https://azure.microsoft.com/resources/videos/how-to-use-the-azure-database-migration-guide/).
- For a walk through of the phases of the migration process and detail about the specific tools and services recommended to perform assessment and migration, see the video [Overview of the migration journey and the tools/services recommended for performing assessment and migration](https://azure.microsoft.com/resources/videos/overview-of-migration-and-recommended-tools-services/).


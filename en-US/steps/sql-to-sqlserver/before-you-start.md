## Preparing for database migration

As you prepare for upgrading your SQL Server database to a later version of SQL Server, consider the versions of SQL Server that are supported and to address any prerequisites. This will help to ensure an efficient and successful migration.

### Supported upgrade technologies

This section describes all supported scenarios and options for an upgrade from and older version of SQL Server to a newer version of SQL Server, current as of March 2019.

Supported source and target versions are shown in the following table.

<br>
<table style="width: 650px;">
<thead>
<tr>
<th style="width: 325px; vertical-align: middle;">
<p><strong>&nbsp;SQL Server source versions</strong></p>
</th>
<th style="width: 325px; vertical-align: middle;">
<p><strong>&nbsp;SQL Server target versions</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="width: 325px; vertical-align: top;">
<ul>
<li>SQL Server 2005</li>
<li>SQL Server 2008, SQL Server 2008 R2</li>
<li>SQL Server 2012</li>
<li>SQL Server 2014</li>
<li>SQL Server 2016</li>
</ul>
</td>
<td style="width: 325px; vertical-align: top;">
<ul>
<li>SQL Server 2014</li>
<li>SQL Server 2016</li>
<li>SQL Server 2017 on Linux</li>
<li>SQL Server 2017 on Windows</li>
</ul>
</td>
</tr>
</tbody>
</table>

The following data migration options are discussed:
*	Backup and restore
*	Transactional replication
*	Always On availability groups
*	Data Migration tool set (Azure Database Migration Service [Azure DMS] and Data Migration Assistant [Data Migration Assistant])
*	Database mirroring
*	Log shipping
*	Bulk load

#### Upgrading from SQL Server 2005
When upgrading from SQL Server 2005, the following migration options are supported.

<br>
<table width="100%">
<thead>
<tr>
<th width="131">
<p><strong>Target version</strong></p>
</th>
<th width="539">
<p><strong>Database migration options</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="131">
<p>SQL Server 2017</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dma">Data Migration Assistant</a> (DMA).</li>
<li>Backup and restore: A backup taken on SQL Server 2005 can be restored to SQL Server 2017.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2005 to SQL Server 2017.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2016</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2005 can be restored to SQL Server 2016.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2005 to SQL Server 2016.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2014</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2005 can be restored to SQL Server 2014.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2005 to SQL Server 2014.</li>
</ul>
</td>
</tr>
</tbody>
</table>

#### Upgrading from SQL Server 2008 or SQL Server 2008 R2
When upgrading from SQL Server 2008 or SQL Server 2008 R2, the following migration options are supported.

<br>
<table width="100%">
<thead>
<tr>
<th width="131">
<p><strong>Target version</strong></p>
</th>
<th width="539">
<p><strong>Database migration options</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="131">
<p>SQL Server 2017</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dma">Data Migration Assistant</a> (DMA).</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2008 or SQL Server 2008 R2 can be restored to SQL Server 2017.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2008 SP3 or later, or SQL Server 2008 R2 SP2 or later, and mirror is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes principal, SQL Server 2008 or SQL Server 2008 R2 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2008 SP3 or later, or SQL Server 2008 R2 SP2 or later, and secondary is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes primary, SQL Server 2008 or SQL Server 2008 R2 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2008 or SQL Server 2008 R2 to SQL Server 2017.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2016</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2008 or SQL Server 2008 R2 can be restored to SQL Server 2016.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2008 SP3 or later, or SQL Server 2008 R2 SP2 or later, and mirror is running SQL Server 2016. If a failover, either automatic or manual, happens such that SQL Server 2016 instance becomes principal, SQL Server 2008 or SQL Server 2008 R2 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2008 SP3 or later, or SQL Server 2008 R2 SP2 or later, and secondary is running SQL Server 2016. If a failover, either automatic or manual, happens such that SQL Server 2016 instance becomes primary, SQL Server 2008 or SQL Server 2008 R2 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2008 or SQL Server 2008 R2 to SQL Server 2016.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2014</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2008 or SQL Server 2008 R2 can be restored to SQL Server 2014.</li>
<li><u>Transactional replication</u>: SQL Server replication from SQL Server 2008/2008R2 to SQL Server is supported. Replication upgrade options are outlined in detail in the blog post&nbsp;<a href="https://blogs.msdn.microsoft.com/sql_server_team/upgrading-a-replication-topology-to-sql-server-2016/">Upgrading a Replication Topology to SQL Server 2016</a>.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2008 SP3 or later, or SQL Server 2008 R2 SP2 or later, and mirror is running SQL Server 2014. If a failover, either automatic or manual, happens such that SQL Server 2014 instance becomes principal, SQL Server 2008 or SQL Server 2008 R2 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2008 SP3 or later, or SQL Server 2008 R2 SP2 or later, and secondary is running SQL Server 2014. If a failover, either automatic or manual, happens such that SQL Server 2014 instance becomes primary, SQL Server 2008 or SQL Server 2008 R2 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2008 or SQL Server 2008 R2 to SQL Server 2014.</li>
</ul>
</td>
</tr>
</tbody>
</table>

#### Upgrading from SQL Server 2012
When upgrading from SQL Server 2012, the following migration options are supported.

<br>
<table width="100%">
<thead>
<tr>
<th width="131">
<p><strong>Target version</strong></p>
</th>
<th width="539">
<p><strong>Database migration options</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="131">
<p>SQL Server 2017</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dma">Data Migration Assistant</a> (DMA).</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2012 can be restored to SQL Server 2017.</li>
<li><u>Transactional replication</u>: SQL Server transactional replication from SQL Server 2012 to SQL Server 2017 is supported.</li>
<li><u>Availability group</u>: Always On availability groups are supported if primary replica is running SQL Server 2012 SP2 or later and secondary replicas are running SQL Server 2017. If a failover, either automatic or manual, happens such that a SQL Server 2017 instance becomes primary, SQL Server 2012 instance becomes secondary and will NOT be able to receive changes from primary.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2012 SP1 or later and mirror is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes principal, SQL Server 2012 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2012 SP1 or later and secondary is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes primary, SQL Server 2012 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2012 to SQL Server 2017.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2016</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2012 can be restored to SQL Server 2016.</li>
<li><u>Transactional replication</u>: SQL Server transactional replication from SQL Server 2012 to SQL Server 2016 is supported.</li>
<li><u>Availability group</u>: Always On availability groups are supported if primary replica is running SQL Server 2012 SP2 or later and secondary replicas are running SQL Server 2016. If a failover, either automatic or manual, happens such that a SQL Server 2016 instance becomes primary, SQL Server 2012 instance becomes secondary and will NOT be able to receive changes from primary.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2012 SP1 or later and mirror is running SQL Server 2016. If a failover, either automatic or manual, happens such that SQL Server 2016 instance becomes principal, SQL Server 2012 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2012 SP1 or later and secondary is running SQL Server 2016. If a failover, either automatic or manual, happens such that SQL Server 2016 instance becomes primary, SQL Server 2012 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2012 to SQL Server 2016.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2014</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2012 can be restored to SQL Server 2014.</li>
<li><u>Transactional replication</u>: SQL Server transactional replication from SQL Server 2012 to SQL Server 2014 is supported.</li>
<li><u>Availability group</u>: Always On availability groups are supported if primary replica is running SQL Server 2012 SP1 or later and secondary replicas are running SQL Server 2014. If a failover, either automatic or manual, happens such that a SQL Server 2014 instance becomes primary, SQL Server 2012 instance becomes secondary and will NOT be able to receive changes from primary.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2012 SP1 or later and mirror is running SQL Server 2014. If a failover, either automatic or manual, happens such that SQL Server 2014 instance becomes principal, SQL Server 2012 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2012 SP1 or later and secondary is running SQL Server 2014. If a failover, either automatic or manual, happens such that SQL Server 2014 instance becomes primary, SQL Server 2012 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2012 to SQL Server 2014.</li>
</ul>
</td>
</tr>
</tbody>
</table>

#### Upgrading from SQL Server 2014
When upgrading from SQL Server 2014, the following migration options are supported.

<br>
<table width="100%">
<thead>
<tr>
<th width="131">
<p><strong>Target version</strong></p>
</th>
<th width="539">
<p><strong>Database migration options</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="131">
<p>SQL Server 2017</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dma">Data Migration Assistant</a> (DMA).</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2014 can be restored to SQL Server 2017.</li>
<li><u>Transactional replication</u>: SQL Server transactional replication from SQL Server 2014 to SQL Server 2017 is supported.</li>
<li><u>Availability group</u>: Always On availability groups are supported if primary replica is running SQL Server 2014 and secondary replicas are running SQL Server 2017. If a failover, either automatic or manual, happens such that a SQL Server 2017 instance becomes primary, SQL Server 2014 instance becomes secondary and will NOT be able to receive changes from primary.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2014 and mirror is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes principal, SQL Server 2014 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2014 and secondary is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes primary, SQL Server 2014 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2014 to SQL Server 2017.</li>
</ul>
</td>
</tr>
<tr>
<td width="131">
<p>SQL Server 2016</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dam">Data Migration Assistant</a>.</li>
<li>Backup and restore: A backup taken on SQL Server 2014 can be restored to SQL Server 2016.</li>
<li>Transactional replication: SQL Server transactional replication from SQL Server 2014 to SQL Server 2016 is supported.</li>
<li><u>Availability group</u>: Always On availability groups are supported if primary replica is running SQL Server 2014 and secondary replicas are running SQL Server 2016. If a failover, either automatic or manual, happens such that a SQL Server 2016 instance becomes primary, SQL Server 2014 instance becomes secondary and will NOT be able to receive changes from primary.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2014 and mirror is running SQL Server 2016. If a failover, either automatic or manual, happens such that SQL Server 2016 instance becomes principal, SQL Server 2014 instance becomes mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2014 and secondary is running SQL Server 2016. If a failover, either automatic or manual, happens such that SQL Server 2016 instance becomes primary, SQL Server 2014 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2014 to SQL Server 2016.</li>
</ul>
</td>
</tr>
</tbody>
</table>

#### Upgrading from SQL Server 2016
When upgrading from SQL Server 2016, the following migration options are supported.

<br>
<table width="100%">
<thead>
<tr>
<th width="131">
<p><strong>Target version</strong></p>
</th>
<th width="539">
<p><strong>Database migration options</strong></p>
</th>
</tr>
</thead>
<tbody>
<tr>
<td width="131">
<p>SQL Server 2017</p>
</td>
<td width="539">
<ul>
<li><u>Migration tools</u>: Migration is supported through <a href="https://aka.ms/dma">Data Migration Assistant</a> (DMA).</li>
<li><u>Backup and restore</u>: A backup taken on SQL Server 2016 can be restored to SQL Server 2017.</li>
<li><u>Transactional replication</u>: SQL Server transactional replication from SQL Server 2016 to SQL Server 2017 is supported.</li>
<li><u>Availability group</u>: Always On availability groups are supported if primary replica is running SQL Server 2016 and secondary replicas are running SQL Server 2017. If a failover, either automatic or manual, happens such that a SQL Server 2017 instance becomes primary, the SQL Server 2016 instance becomes secondary and will NOT be able to receive changes from primary.</li>
<li><u>Database mirroring</u>: Database mirroring is supported if principal is running SQL Server 2016 and mirror is running SQL Server 2017. If a failover, either automatic or manual, happens such that a SQL Server 2017 instance becomes principal, the SQL Server 2016 instance becomes a mirror and will NOT receive changes from principal.</li>
<li><u>Log shipping</u>: Log shipping is supported if primary is running SQL Server 2016 and secondary is running SQL Server 2017. If a failover, either automatic or manual, happens such that SQL Server 2017 instance becomes primary, the SQL Server 2016 instance becomes secondary and will NOT receive changes from primary.</li>
<li><u>Bulk load</u>: Tables can be bulk copied from SQL Server 2016 to SQL Server 2017.</li>
</ul>
</td>
</tr>
</tbody>
</table>

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
<p><a href="https://aka.ms/dmj-wp-mainframe-optimize">Optimization Guide for Mainframe App/Data recompiled to .NET &amp; SQL Server</a></p>
</td>
<td width="59%">
<p>This guide offers optimization advice for executing point-lookups against SQL Server from .NET as efficiently as possible. Customers wishing to migrate from mainframe databases to SQL Server may desire to migrate existing mainframe-optimized design patterns, especially when using 3rd party tools (such as Raincode Compiler) to automatically migrate mainframe code (COBOL/JCL etc) to T-SQL and C# .NET.</p>
</td>
</tr>
</tbody>
</table>

**Note**: These resources were developed as part of the Data Migration Jumpstart Program (DM Jumpstart), which is sponsored by the Azure Data Group engineering team. The core charter DM Jumpstart is to unblock and accelerate complex modernization and compete data platform migration opportunities to Microsoft’s Azure Data platform. If you think your organization would be interested in participating in the DM Jumpstart program, please contact your account team and ask that they submit a nomination.

### Additional resources

- For an overview of the Azure Database Migration Guide and the information it contains, see the video [How to Use the Database Migration Guide](https://azure.microsoft.com/resources/videos/how-to-use-the-azure-database-migration-guide/).
- For a walk through of the phases of the migration process and detail about the specific tools and services recommended to perform assessment and migration, see the video [Overview of the migration journey and the tools/services recommended for performing assessment and migration](https://azure.microsoft.com/resources/videos/overview-of-migration-and-recommended-tools-services/).

### Prerequisites

Before beginning your migration project, it is important to address the associated prerequisites. To prepare for the migration, download and install the:

* Latest version of the [MAP Toolkit](http://go.microsoft.com/fwlink/?LinkID=316883).
* [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595) v3.3 or later.
* Latest version of the [Database Experimentation Assistant](https://www.microsoft.com/en-us/download/details.aspx?id=54090).

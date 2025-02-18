## Migration overview

After you have the necessary prerequisites in place and have completed the tasks associated with the **Pre-migration** stage, you are ready to perform the schema and data migration.

## Migrate schema and data

After you have completed assessing your databases and addressing any discrepancies, the next step is to execute the migration process. Migration involves two steps – publishing the schema and migrating the data. SSMA for Oracle is the correct tool to use for this process.

### Steps

To use SSMA for Oracle to publish the database schema and migrate the data, perform the following steps.

1. **Publish the schema to Azure SQL Database**.

    a. After schema conversion you can save this project locally for an offline schema remediation exercise. You can do so by choosing "Save Project" from the "File" menu. This gives you an opportunity to evaluate the source and target schemas offline and perform remediation before you can publish the schema to Azure SQL Database.

    b. To Publish the schema, select the database from the "Databases" node in the "SQL Azure Metadata Explorer" and choose "Synchronize with Database" from the right-click menu options
  
    ![Image Alt Text Synchronize with Database](https://mpbdevcontent.azureedge.net/Images/scenario-assets/publishschema.png)
  
    c. This action will publish the Oracle schema to the Azure SQL instance.

2. **Migrate data to Azure SQL Database**.

    a.	After publishing the schema to the Azure SQL instance, select the Oracle schema from the "Oracle Metadata Explorer” and choose "Migrate Data" from the right-click menu options or the menu bar on the top.
  
    b.	At this step you will be required to provide connection details for Oracle and Azure SQL in their respective connection dialogs to migrate the data.
  
    ![Image Alt Text Migrate Data](https://mpbdevcontent.azureedge.net/Images/scenario-assets/migratedata.png)
  
    c. After the migration is complete you will be able to view the "Data Migration report".
  
    ![Image Alt Text Data Migration Report](https://mpbdevcontent.azureedge.net/Images/scenario-assets/migrationreport.png)
  
    d. Validate the migration by reviewing the data and schema on the Azure SQL instance by using SQL Server Management Studio (SSMS).

    ![Image Alt Text Validate in SSMA](https://mpbdevcontent.azureedge.net/Images/scenario-assets/migrationcomplete.png)

SSMA is not the only option for migrating data, though. You could also use SQL Server Integration Services (SSIS).

**Note**: For complete step-by-step guidance on publishing the schema and migrating the data, see the following resources:

* The blog posting [SQL Server Migration Assistant: How to assess and migrate data from non-Microsoft data platforms to SQL Server](https://blogs.msdn.microsoft.com/datamigration/2016/11/16/sql-server-migration-assistant-how-to-assess-and-migrate-databases-from-non-microsoft-data-platforms-to-sql-server/)
* The article [Getting Started with SQL Server Integration Services](https://docs.microsoft.com/en-us/sql/integration-services/sql-server-integration-services)
* The white paper [SQL Server Integration Services: SSIS for Azure and Hybrid Data Movement](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/SSIS%20Hybrid%20and%20Azure.docx)

**Note**: If you are interested in participating in a Private preview of online migrations for Oracle to Azure SQL Database (or to Azure SQL Database Managed Instance) using the Azure Database Migration Service, submit a nomination on the Azure Database Migration Service [preview site](https://aka.ms/dms-preview).

## Data sync and Cutover

With minimal-downtime migrations, the source you are migrating continues to change, drifting from the target in terms of data and schema, after the one-time migration occurs. During the **Data sync** phase, you need to ensure that all changes in the source are captured and applied to the target in near real time. After you verify that all changes in source have been applied to the target, you can cutover from the source to the target environment.

The Azure Database Migration Service does not yet support minimal-downtime migrations for this scenario, so the **Data sync** and **Cutover** phases are not currently applicable.

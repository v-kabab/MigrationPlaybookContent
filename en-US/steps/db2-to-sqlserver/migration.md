## Migration overview

After you have the necessary prerequisites in place and have completed the tasks associated with the **Pre-migration** stage, you are ready to perform the schema and data migration.

## Migrate schema and data

After you have completed assessing your databases and addressing any discrepancies, the next step is to execute the migration process. Migration involves two steps – publishing the schema and migrating the data. SSMA for DB2 is the correct tool to use for this process.

### Steps

To use SSMA for DB2 to publish the database schema and migrate the data, perform the following steps.

1. **Publish the schema to SQL Server**.

    a. After schema conversion you can save this project locally for an offline schema remediation exercise. You can do so by choosing "Save Project" from the "File" menu. This gives you an opportunity to evaluate the source and target schemas offline and perform remediation before you can publish the schema to SQL Server.

    b. To Publish the schema, select the database from the "Databases" node in the "SQL Server Metadata Explorer" and choose "Synchronize with Database" from the right-click menu options
  
    ![Synchronize with Database](https://mpbdevcontent.azureedge.net/Images/scenario-assets/publishschema.png)
  
    c. This action will publish the DB2 schema to the SQL Server instance.


2. **Migrate data to SQL Server**.

    a.	After publishing the schema to the SQL Server instance, select the DB2 schema from the "DB2 Metadata Explorer” and choose "Migrate Data" from the right-click menu options or the menu bar on the top.
  
    b.	At this step you will be required to provide connection details for DB2 and SQL Server in their respective connection dialogs to migrate the data.
  
    ![Migrate Data](https://mpbdevcontent.azureedge.net/Images/scenario-assets/migratedata.png)
  
    c. After the migration is complete you will be able to view the "Data Migration report".
  
    ![Data Migration Report](https://mpbdevcontent.azureedge.net/Images/scenario-assets/migrationreport.png)
  
    d. Validate the migration by reviewing the data and schema on the SQL Server instance by using SQL Server Management Studio (SSMS).

    ![Validate in SSMA](https://mpbdevcontent.azureedge.net/Images/scenario-assets/migrationcomplete.png)

## Data sync and Cutover

With minimal-downtime migrations, the source you are migrating continues to change, drifting from the target in terms of data and schema, after the one-time migration occurs. During the **Data sync** phase, you need to ensure that all changes in the source are captured and applied to the target in near real time. After you verify that all changes in source have been applied to the target, you can cutover from the source to the target environment.

The Azure Database Migration Service does not yet support minimal-downtime migrations for this scenario, so the **Data sync** and **Cutover** phases are not currently applicable.

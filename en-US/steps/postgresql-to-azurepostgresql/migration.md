## Migration overview

After you have the necessary prerequisites in place and have completed the tasks associated with the **Pre-migration** stage, you are ready to perform the schema and data migration.

## Migrate schema and data

There are two ways to migrate a PostgreSQL database to Azure Database for PostgreSQL.

- **For relatively large databases that can’t afford downtime during migration**, see the detailed, step-by-step instructionns in the article [Migrate PostgreSQL to Azure Database for PostgreSQL online using DMS](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql).

- **For relatively small (<150GB for example) databases that allow for downtime during migration**, you can use the pg_dump and pg_restore commands.

### Dump and restore
You can use [pg_dump](https://www.postgresql.org/docs/9.6/static/app-pgdump.html) to extract a PostgreSQL database into a dump file and [pg_restore](https://www.postgresql.org/docs/9.6/static/app-pgrestore.html) to restore the PostgreSQL database from an archive file created by pg_dump. For additional detail, see the article [Dump and restore](https://docs.microsoft.com/en-us/azure/postgresql/howto-migrate-using-dump-and-restore) in the Azure Database for PostgreSQL documentation.

To optimize your backup and restore commands and minimize the time required to perform he migration from PostGreSQL to Azure Database for PostgreSQL, consider the following guidance.

**Note**: By using these optimizations, one of our customers, for example, restored a 10 Gb database to the Azure Database for PostgreSQL service (General Purpose pricing tier) in under 50 minutes.

**Important**: Be sure to test and validate these commands on a validation system before you use them on a production system.

### For the backup
Perform the backup using the **-Fc** switch so that you can perform the restore in parallel to speed up the process.

For example:
    pg_dump -h MySourceServerName -U MySourceUserName -Fc -d MySourceDatabaseName > Z:\Data\Backups\MyDatabaseBackup.dump

**Note**: The detailed syntax for the pg_dump command is available in [PostgreSQL documentation](https://www.postgresql.org/docs/9.6/static/app-pgdump.html).

### For the restore
Copy the backup files to an Azure blob/store and perform the restore from there, which should be a lot faster than performing the restore across the Internet. While this should occur by default, be sure to open the dump file and verify that the create index statements are after the insert of the data. If it is not the case, move the create index statements so that they appear after the insert of the data.

Perform the restore using the **-Fc** and **-j #** switches to parallelize the restore. In this case, # represents the number of cores on the target server. You can also test running the command with # set to twice the number of cores of the target server to see if performance is further enhanced.

For example:
    pg_restore -h MyTargetServer.postgres.database.azure.com -U MyAzurePostgreSQLUserName -Fc -j 32 -d MyTargetDatabase Z:\Data\Backups\MyDatabaseBackup.dump

You can also edit the dump file to include the **set synchronous_commit = off;** statement at the beginning and the **set synchronous_commit = on;** statement at the end of the file. If you do not include the statement to turn on synchronous commit at the end of the file and before the apps change the data, a subsequent loss of data may result.

**Note**: The detailed syntax for the pg_restore command is available in [PostgreSQL documentation](https://www.postgresql.org/docs/9.6/static/app-pgrestore.html).

## Data sync and Cutover

With minimal-downtime migrations, the source you are migrating continues to change, drifting from the target in terms of data and schema, after the one-time migration occurs. During the **Data sync** phase, you need to ensure that all changes in the source are captured and applied to the target in near real time. After you verify that all changes in source have been applied to the target, you can cutover from the source to the target environment.

For details on Data Sync and Cutover for this scenario, see the instructions in the [Cutover migration task](https://docs.microsoft.com/azure/dms/tutorial-postgresql-azure-postgresql-online#cutover-migration-task) section of the article Migrate PostgreSQL to Azure Database for PostgreSQL online using DMS.

## Migration overview

After you have the necessary prerequisites in place and have completed the tasks associated with the Pre-migration phase, you are ready to proceed with the migration. 

### Migrate MongoDB data

You can use the Azure Database Migration Service to perform an offline (one-time) migration of databases from an on-premises or cloud instance of MongoDB to Azure Cosmos DB's API for MongoDB.

#### Overview of migration steps

An overview of the steps associated with using Azure DMS to migrate MongoDB data to Azure Cosmos DB follows.

1. Register the Microsoft.DataMigration resource provider.
2. Create an instance.
3. Create a migration project.
4. Specify source details.
5. Specify target details.
6. Map to target databases.
7. Run the migration.
8. Monitor the migration.
9. Verify data in Cosmos DB.

**Important**: For detail on the specific steps associated with:
* Online migrations, see the information in [Migrate MongoDB to Azure Cosmos DB's API for MongoDB online using DMS](https://docs.microsoft.com/en-us/azure/dms/tutorial-mongodb-cosmos-db-online#register-the-microsoftdatamigration-resource-provider).
* Offline migrations, see the information in [Migrate MongoDB to Azure Cosmos DB's API for MongoDB offline using DMS](https://docs.microsoft.com/en-us/azure/dms/tutorial-mongodb-cosmos-db#register-the-microsoftdatamigration-resource-provider).

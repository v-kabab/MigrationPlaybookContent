## Migrating from Azure Table Storage

There are two options available for migrating from Azure Table Storage to Azure Cosmos DB Table API. 

**Option #1: Move data using AZCopy** 

One option is to use the [AzCopy utility](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy?toc=%2fazure%2fstorage%2fblobs%2ftoc.json) to transfer data from
Azure Table Storage to Azure Cosmos Database. 

**Option #2: Azure Cosmos DB Data Migration Tool**

The other option is the Azure Cosmos DB [Data Migration tool](http://www.microsoft.com/en-us/download/details.aspx?id=46436), which is an open source solution that imports data to Azure Cosmos DB from a variety of sources, including: MongoDB, JSON files, SQL Server, etc. 
Follow the instructions in the article [Azure Cosmos DB: Data migration tool](https://docs.microsoft.com/en-us/azure/cosmos-db/import-data) on how to download and use the tool.

Note: If you are migrating from a data source that is not listed here to Azure Cosmos DB, please send an email to [*AskCosmosDB@microsoft.com*](mailto:AskCosmosDB@microsoft.com) and the product team will help you with migration.

### Additional resources

- For an overview of the Azure Database Migration Guide and the information it contains, see the video [How to Use the Database Migration Guide](https://azure.microsoft.com/resources/videos/how-to-use-the-azure-database-migration-guide/).
- For a walk through of the phases of the migration process and detail about the specific tools and services recommended to perform assessment and migration, see the video [Overview of the migration journey and the tools/services recommended for performing assessment and migration](https://azure.microsoft.com/resources/videos/overview-of-migration-and-recommended-tools-services/).

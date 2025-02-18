## Post-migration overview

After you have successfully completed the Migration phase, you need to go through a series of post-migration tasks to ensure that everything is functioning as smoothly and efficiently as possible. 
 
### Remediate applications

After the data is migrated to the target environment, all the applications that formerly consumed the source need to start consuming the target. Accomplishing this will require changing the MongoDB connection string. 

**Steps include:** 

1. In an Internet browser, sign in to the [Azure portal](https://portal.azure.com/). 

2. On the Azure Cosmos DB blade, select the API for MongoDB account.  

3. On the left pane of the account blade, select **Quick start**.  

4. Choose your platform (.NET, Node.js, MongoDB Shell, Java, Python). If you don't see your driver or tool listed, don't worry--we continuously document more connection code snippets. Please comment below on what you'd like to see. To learn how to craft your own connection, read [Get the account's connection string information](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account). 

5. Copy and paste the code snippet into your MongoDB app.

    ![Cosmos DB quick start](https://mpbdevcontent.azureedge.net/Images/scenario-assets/mongo-quick-start.png)

### Optimize  

The post migration phase is crucial for optimizing performance and costs. After migrating to Cosmos DB, customers can tune several different options. 

**Reduce Request Units for Collections** 

Customers should reduce provisioned throughput capacity to the number of Request Units (RU’s) that is necessary for their workloads. 

When you estimate the number of request units to provision, it's important to consider the following variables: 

- **Item size**. As size increases, the number of request units consumed to read or write the data also increases. 
- **Item property count**. Assuming default indexing of all properties, the units consumed to write a document, node, or entity increase as the property count increases. 
- **Query patterns**. The complexity of a query affects how many request units are consumed for an operation. The number of query results, the number of predicates, the nature of the predicates, the size of the source data, and projections all affect the cost of query operations. 

**Tune Consistency Model** 

Select the best consistency level to ensure well-reasoned trade-offs between consistency, availability, and latency. Consistency models like Strong require additional RU’s during reads. 

For more information about tuning the consistency model, see the article [Consistency levels in Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/cosmos-db/consistency-levels).

**Optimize Indexing Policy** 

Cosmos DB indexes all fields by default. It does not expect or require any schema or creation of secondary indices.  

However, there are trade-offs between storage, write, and query performance which can be optimized by [tuning the indexing policy.](https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-indexing) For example, customers with a write heavy workload should ensure they only index necessary properties or change index types to require less data. Customers can also adjust indexing precision to tune the trade-off between index storage overhead and query performance. 

Customers can modify the indexing modes to better manage the amount of RU’s used in indexing data. Customers have the following options: 

- **Indexing Mode: Consistent**. Indices for new writes will have the same consistency as the collection.
- **Indexing Mode: Lazy**. Indices for new writes will only have eventual consistency 

**Distribute Data Globally** 

Customers can associate an unlimited number of regions with their Azure Cosmos DB accounts. They can also enable multi-master to have multiple write regions. When not using multi-master, customers can assign failover priorities for their globally replicated regions. More information about turnkey global distribution is available in [Manage an Azure Cosmos account](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally-turnkey).

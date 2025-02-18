## Post-migration overview

After you have successfully completed the **Migration** stage, you need to go through a series of post-migration tasks to ensure that everything is functioning as smoothly and efficiently as possible.

## Remediate applications

After the data is migrated to the target environment, all the applications that formerly consumed the source need to start consuming the target. Accomplishing this will in some cases require changes to the applications.

## Perform tests

After the data is migrated to target, perform tests against the databases to verify that the applications perform well against the after the migration.
Use the Database Experimentation Assistant (DEA) to assist with evaluating the target SQL Server.

**Note**: For assistance with developing and running post-migration validation tests, also consider the Data Quality Solution available from [QuerySurge](http://www.querysurge.com/company/partners/microsoft). 

### Steps for the Perform tests phase

To use DEA for database migration testing, perform the following steps.

1. **Download the [DEA tool](https://www.microsoft.com/en-us/download/details.aspx?id=54090)**, and then install it.

2. **Run a trace capture**

    a. On the left navigation tree, select the camera icon the go to **All Captures**.
    
    ![New trace capture](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deanewcapture.png)
    
    b. To start a new capture, select **New Capture**.
    
    c. To configure the capture, speficy the trace name, duration, SQL Server instance name, database name, and the share location for storing the trace file on the computer running SQL Server.
    
    ![Provide trace capture inputs](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deacaptureinputs.png)
    
    d. Select **Start** to begin trace capture.

3. **Run a trace replay**
    
    a. On the left navigation tree, select the play icon the go to **All Replays**.
    
    ![New trace replay](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deanewreplay.png)
    
    b. To start a new replay, select **New Replay**.
    
    c. To configure the replay, specify the replay name, controller machine name, path to source trace file on controller, SQL Server instance name, and the pathfor storing the target trace file on the computer running SQL Server.
    
    d. Select **Start** to begin replay of your capture.
    
 4. **Create a new Analysis Report**
 
    a. On the left navigation tree, select the checklist icon to go to **Analysis Reports**. 
    
    ![New Analysis Report](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deanewanalysis.png)
    
    b. Connect to the SQL Server on which you will store your report databases.
    
    You will see the list of all reports in the server.
    
    c. Select **New Report**.
    
    d. To configure the report, specify the report name, and specify paths to the traces fon the source and target SQL Server instances.
    
    ![Provide report analysis inputs](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deaanalysisinput.png)
    
 5. **Review an analysis report**
 
    a. On the first page of the report, the version and build information for the target servers on which the experiment was run displays.
    
    Threshold allows you to adjust the sensitivity or tolerance of your A/B Test analysis. 
    
    Note: By default, threshold is set to 5%; any performance improvement that is >= 5% is categorized as ‘Improved’. The drop-down selector allows you to evaluate the report using different performance thresholds.
       
    ![Analysis Threshold](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deathreshold.jpg)
    
    b. Select the individual slices of the pie chart to view drill-down metrics on performance.
    
    ![Drill down report](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deachart.png)
    
    On the drill-down page for a performance change category, you will see a list of queries in that category. 
    
    ![Drill down report](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deaerrorqueries.png)
    
    c. Select an individual query to get performance summary statistics, error information, and query plan information.
    
    ![Summary Statistics](https://mpbdevcontent.azureedge.net/Images/scenario-assets/deasummarystats.png)

## Optimize

The post-migration phase is crucial for reconciling any data accuracy issues and verifying completeness, as well as addressing performance issues with the workload.

**Note**: For additional detail about these issues and specific steps to mitigate them, see the following resource:
* The [Post-migration Validation and Optimization Guide](https://docs.microsoft.com/en-us/sql/relational-databases/post-migration-validation-and-optimization-guide).

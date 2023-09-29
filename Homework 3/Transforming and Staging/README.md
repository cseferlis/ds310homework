# Homework 3 - Transforming and Staging

**Class,**

> **NOTE** - Homework3 is based on the homework2 (Extract And Load) assignment. You will be using the same `resource group` and `data-factory` you created for previous assignment. If you did not complete that assignment please reach out to TA Office Hours to start with this assignment.

Building off of Homework 2 where you extracted and loaded a data file into your storage account. Using the [reference document](https://static.nhtsa.gov/odi/ffdd/cmpl/Import_Instructions_Excel_All.pdf) where all datatypes and fields are listed, for Homework 3, you will need to use your existing Data Factory, and add a new activity for loading the data from the .txt file into a SQL Server Database Table you create.

You will need to use Azure Data Factory to:

1. Convert the datatype from text to date for the "DateA" column (Transform)
2. Then import the data into a "<initials>Complaints" database into the SQL Server you will be creating using the following instructions:
    > **NOTE** - If you have used the _`bash fromTemplate.sh`_ script for current homework to create your sql server, you can skip these steps for creating the server and database and start from **step 3**. You will still need to create the table and load the data into the table.

    Next, create an Azure SQL Server with Sample database included:

    Read the instructions fully first: [https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal](https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal) 
    
    - Use the Resource Group you just created for Homework 2
    - Use `<initials>DS310db` for the database name for step 5 (`<initials>` will be random if you used the script)
    - For Step 6
      - Use EastUS2 for Region
      - Use `<first initial><last name>` for the user account (make sure you keep track of your password) (LoginId will be `ds310admin` if you used the script and Password will be `ds310password013!`)
      - Use `<initials>ds310server` for the server name (Has to be all lower case) (Server name will start with `db<random-string>` if you used the script)
    - Select "Development" for Workload Environment
    - Select "Configure database" next to Compute and Storage
      - Use the Standard Tier (S0) with 10 DTU and 250 GB storage for Service Tier
      - The cost should be listed as $14.72/mo - if this doesn't match, you missed something
    - Select "Locally Redundant Storage" for backup storage redundancy option prior to the networking step
    - Select "Yes" for both options under firewall rules in step 13 (instructions are no, then yes, we want yes for both)
    - Do not opt for the free trial in step 16
    - After you create the database, it may take 5-10 minutes to complete deployment
    - Continue with instructions through running a query

3. You will need to use the Reference (`Complaints Reference File`) file below for setting up the new table attributes (columns) with the appropriate datatypes. For best results, I typically use NVARCHAR as my datatype to be able to handle Unicode and any strange characters that might show up in the data.

4. After your database is up and running, I want you to run the following query, output the results to a file and save the file as a PDF for submission.

    ```sql
    SELECT *
    FROM cbsComplaints
    WHERE CONVERT(Date, DATEA) = CONVERT(Date, GETDATE() - 1)
    ```

Here are a few reference documents that will help:

- [Getting started with Azure Data Factory](https://learn.microsoft.com/en-us/azure/data-factory/quickstart-create-data-factory)
- [Creating a Storage Account](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-create?tabs=azure-portal)
- [Creating a Database in Azure SQL Server Using your Existing SQL Server](https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal)
- [Creating a Table in an Azure SQL Database](https://www.edureka.co/community/62364/how-to-create-table-in-azure-sql-database)
- [Information page for Complaints data](https://www.nhtsa.gov/nhtsa-datasets-and-apis#complaints)
- [Complaints Data File](https://static.nhtsa.gov/odi/ffdd/cmpl/FLAT_CMPL.zip)
- [Complaints Reference File](https://static.nhtsa.gov/odi/ffdd/cmpl/Import_Instructions_Excel_All.pdf)
- [Copy Tool](https://docs.microsoft.com/en-us/azure/data-factory/copy-activity-overview)
- [Data Flow](https://docs.microsoft.com/en-us/azure/data-factory/concepts-data-flow-overview)

## Think Loud On Below Points 🤔
- How to use `Complaints Reference File` to create a table in Azure SQL Database?
- How to use `Copy Tool` to load data from Azure Storage to Azure SQL Database?
- What if you have a row with a `missing value` in the middle of the file?
- What if the `header column` name is different from the column name in the table?
- What is the `current format` of the file? What is the `delemiter`? How `many columns` are there?
- How to `map` columns in the file to columns in the table? How to change the data type of a column(s)?

## Using Template

```azurecli-interactive
az deployment group create --resource-group <resource-group-name> --template-file <path-to-template.json> --parameters @<path-to-parameters.json>
```
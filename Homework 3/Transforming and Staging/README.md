# Homework 3 - Transforming and Staging

**Class,**

I'll continue to work to get ahead of schedule on Homework, just remember the course changes as it is so new, thus leading to creating some of these activities on the fly.

With that, I'm introducing Homework 3 - Transforming and Staging

Building off of Homework 2 where you extracted and loaded a data file into your storage account. Using the reference document for Homework 3 where all datatypes and fields are listed, you will need to use your existing Data Factory, and add a new activity for loading the data from the .txt file into a SQL Server Database Table you create.

You will need to use Azure Data Factory to:

- Convert the datatype from text to date for the "DateA" column (Transform)
- Then import the data into a "<initials>Complaints" database into the SQL Server you will create using the following instructions:

  Next, create an Azure SQL Server with Sample database included:
  
  Read the instructions fully first: [https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal](https://learn.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?view=azuresql&tabs=azure-portal)
  
  - Use the Resource Group you just created for Homework 2
  - Use `<initials>DS310db` for the database name for step 5
  - For Step 6
    - Use EastUS2 for Region
    - Use `<first initial><last name>` for the user account (make sure you keep track of your password)
    - Use `<initials>ds310server` for the server name (Has to be all lower case)
  - Select "Development" for Workload Environment
  - Select "Configure database" next to Compute and Storage
    - Use the Standard Tier (S0) with 10 DTU and 250 GB storage for Service Tier
    - The cost should be listed as $14.72/mo - if this doesn't match, you missed something
  - Select "Locally Redundant Storage" for backup storage redundancy option prior to the networking step
  - Select "Yes" for both options under firewall rules in step 13 (instructions are no, then yes, we want yes for both)
  - Do not opt for the free trial in step 16
  - After you create the database, it may take 5-10 minutes to complete deployment
  - Continue with instructions through running a query

You will need to use the Reference file below for setting up the new table attributes (columns) with the appropriate datatypes. For best results, I typically use NVARCHAR as my datatype to be able to handle Unicode and any strange characters that might show up in the data.

After your database is up and running, I want you to run the following query, output the results to a file and save the file as a PDF for submission.

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


Feel free to adjust the Markdown code according to your needs or formatting preferences.

## Using Template

```azurecli-interactive
az deployment group create --resource-group <resource-group-name> --template-file <path-to-template.json> --parameters @<path-to-parameters.json>
```
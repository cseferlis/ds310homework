# Homework 7: Synapse SQL Script, External Table Creation, and Data Visualization

In Homework 7, we are going to connect to the PARQUET file created in homework 6 and mount the file as an external table in our Azure Synapse Serverless Pool. This will require setting permissions to your Azure Storage account from your Azure Synapse Workspace, and ensuring that your PARQUET file is formatted properly. From there you will run a simple query in the Workspace with a visual of the results. 

## Objective
Create an external table in Azure Synapse, utilize Synapse SQL scripts to read `.parquet` files, and visualize data. 

## Tasks

### ACL Permissions and Synapse Administration:

1. In Azure, set the Access Control List (ACL) permissions for your container where your `.parquet` file is stored within your storage account to include read, write, and execute permissions for the email address used for the assignment. This resource will help you in setting these permissions: https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-acl-azure-portal

2. In Azure Synapse Studio, go to ‘Manage’, then ‘Access Control’ and assign yourself ‘Synapse Administrator’ permissions.

### External Table Creation:

1. In Azure Synapse Studio, navigate to the ‘Data’ hub and locate the option to create an external table.

2. Use the [Azure Synapse Analytics documentation](https://learn.microsoft.com/en-us/azure/synapse-analytics/sql/develop-tables-external-tables?tabs=hadoop) as a reference for the specific steps.

3. Connect the external table to the NHTSA data in the `.parquet` file.

4. Ensure that the external table schema matches the schema of the `.parquet` file.

### Read Required Parquet Files:

1. Use the SQL script editor in Synapse Studio to write and execute queries against the external table.

2. Make sure your query correctly addresses the data within the `.parquet` files.

### Data Analysis:

1. Focus on extracting data related to Ford F-150 crashes from 1990 to 2010.

2. Your SQL query should filter the data based on the model (Ford F-150) and the year range. You will need to use the where clause for both, including the BETWEEN clause in your query. https://learn.microsoft.com/en-us/sql/t-sql/language-elements/between-transact-sql?view=sql-server-ver16. *note* if your datatype for the year column is not a number this will cause you problems.

### Create a Plot:

1. Use the query results to create a visual representation of the data.

2. This can be a bar chart or line graph showing the number of crashes per year.

### Submission:

1. Your submission should include a screenshot of the SQL query and the resultant plot from the Synapse Studio.

2. Ensure your email address is visible in the screenshot for authentication purposes.

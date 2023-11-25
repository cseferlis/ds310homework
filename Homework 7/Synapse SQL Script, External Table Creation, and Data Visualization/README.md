# Homework 8: Synapse SQL Script, External Table Creation, and Data Visualization

## Objective
Create an external table in Azure Synapse, utilize Synapse SQL scripts to read `.parquet` files, and visualize data.

## Tasks

### ACL Permissions and Synapse Administration:

1. In Azure, set the Access Control List (ACL) permissions for your storage account to include read, write, and execute permissions for the email address used for the assignment.

2. In Azure Synapse Studio, go to ‘Manage’, then ‘Access Control’ and assign yourself ‘Synapse Administrator’ permissions.

### External Table Creation:

1. In Azure Synapse Studio, navigate to the ‘Data’ hub and locate the option to create an external table.

2. Use the [Azure Synapse Analytics documentation](https://docs.microsoft.com/en-us/azure/synapse-analytics/sql/create-external-table) as a reference for the specific steps.

3. Connect the external table to the NHTSA data in the `.parquet` file.

4. Ensure that the external table schema matches the schema of the `.parquet` file.

### Read Required Parquet Files:

1. Use the SQL script editor in Synapse Studio to write and execute queries against the external table.

2. Make sure your query correctly addresses the data within the `.parquet` files.

### Data Analysis:

1. Focus on extracting data related to Ford F-150 crashes from 1990 to 2010.

2. Your SQL query should filter the data based on the model (Ford F-150) and the year range.

### Create a Plot:

1. Use the query results to create a visual representation of the data.

2. This can be a bar chart or line graph showing the number of crashes per year.

### Submission:

1. Your submission should include a screenshot of the SQL query and the resultant plot from the Synapse Studio.

2. Ensure your email address is visible in the screenshot for authentication purposes.
# Homework 6: Azure Synapse Workspace and Parquet Files Creation

## Objective

The main objective of this assignment is to create a Synapse Workspace and partition `.parquet` files by manufacturer name.

## Tasks

### Upgrade your storage account

To connect your Synapse to storage account, you need to upgrade it to ADLS Gen 2. To do so, enable Hierarchical namespace in your storage account (Found in overview, under Data Lake Storage heading)

### Convert NHTSA TXT File to Parquet Format

You are required to perform the following steps using Azure Data Factory Data Flows:

1. **Set up a Data Flow:**
   - Use the NHTSA TXT file as the source for this data flow.

2. **Configure the Sink:**
   - Ensure the output is in `.parquet` format.

3. **Partition the Parquet Files:**
   - The parquet files should be partitioned by Manufacturer name.
   - Some manufacturer names end with a dot (.), this is not allowed in your storage accounts, use filters to filter them out using filter operator in data flow.
   - [Complaints Reference File](https://static.nhtsa.gov/odi/ffdd/cmpl/Import_Instructions_Excel_All.pdf)

### Create Your Synapse Workspace

Follow the steps below, referring to the Azure tutorial where necessary:

1. **Set up the Synapse Workspace:**
   - Tutorial [https://learn.microsoft.com/en-us/azure/synapse-analytics/get-started-create-workspace](Quickstart: Get started - create a Synapse workspace - Azure Synapse Analytics | Microsoft Learn)
   - Do not use the sample data provided in the tutorial.
   - In the Data section of the Synapse workspace, add your storage account as a linked service if it is not already added.
   - Ensure to set up the primary storage account correctly (It should be ADLS Gen 2).

2. **Use the Created Parquet File:**
   - Make sure that the `.parquet` files you created from the NHTSA data is accessible from Synapse workspace.

## Submission

Your submission should include the following:

1. **Screenshot of Your Synapse Workspace:**
   - Ensure that the screenshot clearly shows your Synapse workspace.

2. **Directory or Storage Container View:**
   - Provide a view showing the partitioned `.parquet` files.
   - The partition names based on the manufacturer name should be visible.


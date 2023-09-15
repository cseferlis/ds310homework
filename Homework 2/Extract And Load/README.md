# Homework 2 - Extract & Load

**Let the games begin!**

This homework will require some actual thinking and planning, so do not ignore it or wait until the last minute. If you really want a career in tech, this should be fun for you... (waaaaaayyyyy better than American Lit or Sociology!)

For this assignment, you will be grabbing the National Highway Travel Safety Administration "Complaints" data from the NHTSA.gov website.

You will need to use Azure Data Factory to:

- Grab (Extract) the file from the link below
- Copy it to a newly created Azure Storage (blob type) account (Load) using the tool, not manually
- Unzip the file to a txt file using the tool, not manually

Here are a few reference documents that will help. I recommend following some of the tutorials provided by Microsoft for learning how the tool works and its intent. One Hint: you are grabbing the file from an HTTPS data source:

- [Getting started with Azure Data Factory](https://learn.microsoft.com/en-us/azure/data-factory/quickstart-create-data-factory)
- [Information page for Complaints data](https://www.nhtsa.gov/nhtsa-datasets-and-apis#complaints)

**Complaints Data File:** [https://static.nhtsa.gov/odi/ffdd/cmpl/FLAT_CMPL.zip](https://static.nhtsa.gov/odi/ffdd/cmpl/FLAT_CMPL.zip)

**Complaints Reference File:** [https://static.nhtsa.gov/odi/ffdd/cmpl/Import_Instructions_Excel_All.pdf](https://static.nhtsa.gov/odi/ffdd/cmpl/Import_Instructions_Excel_All.pdf)

## Using Template

```azurecli-interactive
az deployment group create --resource-group <resource-group-name> --template-file <path-to-template.json> --parameters @<path-to-parameters.json>
```

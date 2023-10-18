# Homework 4 - NoSQL

**Class,**

> **NOTE** - Homework4 is based on the homework2 and homework3 assignment. You will be using the same `resource group` and `data-factory` you created for previous assignment. If you did not complete that assignment please reach out to TA Office Hours to start with this assignment. Create a new pipeline you will use for HW4.

As we begin our transition to NoSQL and other types of databases, we're going to start working with Microsoft's Multi-Master, Multi-Modal database, CosmosDB. This is an incredibly flexible DBMS as it can handle SQL, Graph, Document and other database types with sub 10ms replication to nodes all around the world. In fact, the database is so fast that Microsoft uses it to power the Xbox Gaming network and more. 

Read more about CosmosDB and its capabilities here: https://learn.microsoft.com/en-us/azure/cosmos-db/introduction

Building off of Homework 2 and 3 where you extracted and loaded a data file into your storage account. For Homework 4, we will use a different kind of database (NoSQL) to load and manipulate complex data with nested attributes.

For this assignment, you will be grabbing the Kaggle TMDB dataset for 5000 movies (https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata/). For the purpose of this assignment, we will use a cleaned version of that data that is hosted on: [https://data.koley.in/tmdb_5000_movies.json](https://data.koley.in/tmdb_5000_movies.json).

You will need to use Azure to:

- Using Azure data factory, grab the file from the link [https://data.koley.in/tmdb_5000_movies.json](https://data.koley.in/tmdb_5000_movies.json)
- Create a Azure CosmosDB database using the following instructions:
  - To deploy the CosmosDB, use the following tutorial: https://learn.microsoft.com/en-us/azure/cosmos-db/nosql/quickstart-portal Note, do not clean up the resources in the last step, as we want the database to stick around.
  - IN ORDER TO CONTROL COSTS, Alternatively, run the template from this repo using:
      ```sh
      bash formtemplate.sh
      ```
      ```
      az deployment group create --resource-group <resource-group-name> --template-file <path-to-template.json> --parameters @<path-to-parameters.json>
      ```
- Create a container with Database id as "ds310" in your CosmosDB and Container id called "movies". Set Database Throughput as Manual and set it 400 RU/s. For paritionId, use the value "status". 
- Then import the data into the "movies" container.
- Finally, you will do some sample querying using SQL for querying the data in your container using this tutorial: https://learn.microsoft.com/en-us/azure/cosmos-db/nosql/tutorial-query 

- After your database is up and running, I want you to run the following query.

    ```sql
      select c.title from movies as c 
      JOIN p IN c.keywords 
      WHERE p.name = "artificial intelligence"
    ```
  This should give a result of 26 movie titles all of which were originally tagged with "artificial intelligence". 

  If you get this, then everything you have done so far is correct.

- Now modify the above query to find movies which were produced by **"Dentsu"** production company, capture a screenshot of the output of both queries INCLUDING YOUR ACCOUNT IN THE TOP RIGHT of the window.


As questions arise, remember to post questions here in Piazza and work together to find the solutions. 


## Think Loud On Below Points 🤔
- Since our data is a JSON file, use the appropriate dataset format in the Data Factory.
- How to use `Copy Tool` to load data from the online link to the CosmosDB.
- How to use given query to similarly map the production_companies in the data?

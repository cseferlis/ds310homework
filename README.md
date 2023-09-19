# DS 310 Data Mechanics

### Course Description
This course is focused on developing students’ capacity to design and implement the data flows and the associated workflows meant to inform online and offline decision-making within large systems. In supervised group projects, students explore the data science lifecycle, including question formulation, data collection and cleaning (data wrangling), exploratory data analysis and visualization, and decision-making. The course applies tools and methods for data collection, retrieval, integration, and interpretation, using relational (SQL), non-relational (NoSQL), and Big Data paradigms to assemble analysis, optimization, and decision-making algorithms to track and scale data. Topics covered include consolidation, synchronization, and summarization of multiple data streams; data maintenance, and availability; optimization, and analytics that can operate on large amounts of static or streaming data; and online and offline interactive visualization platforms for presenting and examining data. Projects and assignments in this course will leverage problems in real-world settings, especially those related to CDS Impact Labs and co-Labs focusing on equity, sustainability, health, and civic tech.


### Course Objectives
At the end of the course, successful students will have gained skills and hands-on experience in the following methods and technology: 

- Design and implementation of data processing pipelines 
- Complex data modeling 
- Architectural considerations for various data requirements 
- Relational query optimization 
- Dataflow programming abstractions 
- Data stream processing concepts 
- System support for distributed workloads 

Further, students will be exposed to recent developments in distributed data processing systems such as Hadoop, Apache Spark, Databricks, and more through paper assignments and presentations. The collaborative semester-long project will prepare them for the practical aspects of their future careers and expose them to project management tools and software engineering best practices.

### Homework Instructions
1. In a web browser, sign into the [Azure portal](https://portal.azure.com) at `https://portal.azure.com`.
2. Use the **[\>_]** button to the right of the search bar at the top of the page to create a new Cloud Shell in the Azure portal, selecting a ***PowerShell*** environment and creating storage if prompted. Select the subscription "Azure for Students" if prompted. The cloud shell provides a command line interface in a pane at the bottom of the Azure portal, as shown here:

    ![Azure portal with a cloud shell pane](./images/cloud-shell.png)

    > **Note**: You can use either ***Bash*** or ***PowerShell*** environment, use the the drop-down menu at the top left of the cloud shell pane to change it.

3. Note that you can resize the cloud shell by dragging the separator bar at the top of the pane, or by using the **&#8212;**, **&#9723;**, and **X** icons at the top right of the pane to minimize, maximize, and close the pane. For more information about using the Azure Cloud Shell, see the [Azure Cloud Shell documentation](https://docs.microsoft.com/azure/cloud-shell/overview).

4. In the PowerShell pane, enter the following commands to clone this repo:

```[git]
git clone https://github.com/cseferlis/ds310homework.git
```

5. After the repo has been cloned, enter the following commands to change to the folder for the exercise and run the below command

```[bash]
cd ds310homework
```

6. Next go to the `homework` directory you want to work on and run the below command. Run the bash script inside the homework folder using the following command, this will generate the template and parameter files for you.

```[bash]
bash ./formTemplate.sh
```

7. Make sure you mention the right resource group name and the right template and parameter files.

```[azure]
az deployment group create --resource-group <resource-group-name> --template-file <path-to-template.json> --parameters @<path-to-parameters.json>
```

Example:

```[azure]
az deployment group create --resource-group ds310homework --template-file ./homework1/azuredeploy.json --parameters @./homework1/azuredeploy.parameters.json
```

The above command will use a template to create the resources and you should be good to go with the assignment. If you have any questions please reach out.
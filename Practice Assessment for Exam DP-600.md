# Practice Assessment for Exam DP-600: Implementing Analytics Solutions Using Microsoft Fabric

Υλικό επανάληψης βασισμένο στο παρεχόμενο αρχείο. Οι απαντήσεις και οι επεξηγήσεις βρίσκονται σε αναπτυσσόμενες ενότητες, ώστε να μπορείς να δοκιμάζεσαι πριν τις εμφανίσεις.

## Περιεχόμενα

- [Question 1](#question-1)
- [Question 2](#question-2)
- [Question 3](#question-3)
- [Question 4](#question-4)
- [Question 5](#question-5)
- [Question 6](#question-6)
- [Question 7](#question-7)
- [Question 8](#question-8)
- [Question 9](#question-9)
- [Question 10](#question-10)
- [Question 11](#question-11)
- [Question 12](#question-12)
- [Question 13](#question-13)
- [Question 14](#question-14)
- [Question 15](#question-15)
- [Question 16](#question-16)
- [Question 17](#question-17)
- [Question 18](#question-18)
- [Question 19](#question-19)
- [Question 20](#question-20)
- [Question 21](#question-21)
- [Question 22](#question-22)
- [Question 23](#question-23)
- [Question 24](#question-24)
- [Question 25](#question-25)
- [Question 26](#question-26)
- [Question 27](#question-27)
- [Question 28](#question-28)
- [Question 29](#question-29)
- [Question 30](#question-30)
- [Question 31](#question-31)
- [Question 32](#question-32)
- [Question 33](#question-33)
- [Question 34](#question-34)
- [Question 35](#question-35)
- [Question 36](#question-36)
- [Question 37](#question-37)
- [Question 38](#question-38)
- [Question 39](#question-39)
- [Question 40](#question-40)
- [Question 41](#question-41)
- [Question 42](#question-42)
- [Question 43](#question-43)
- [Question 44](#question-44)
- [Question 45](#question-45)
- [Question 46](#question-46)
- [Question 47](#question-47)
- [Question 48](#question-48)
- [Question 49](#question-49)
- [Question 50](#question-50)

## Question 1

You have a Fabric workspace that contains a lakehouse named Lakehouse1.

A user named User1 plans to use Lakehouse explorer to read Lakehouse1 data.

You need to assign a workspace role to User1. The solution must follow the principle of least privilege.

Which workspace role should you assign to User1?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Σωστή απάντηση

Contributor

### Σημειώσεις

Για ανάγνωση δεδομένων μέσω του Lakehouse explorer απαιτείται ρόλος Admin, Member ή Contributor. Ακολουθώντας την αρχή των ελάχιστων απαραίτητων δικαιωμάτων, επίλεξε **Contributor**. Ο ρόλος Viewer δεν παρέχει πρόσβαση ανάγνωσης μέσω του Lakehouse explorer.

Roles in workspaces in Microsoft Fabric - Microsoft Fabric | Microsoft Learn

Implement a Lakehouse with Microsoft Fabric - Training | Microsoft Learn

</details>

## Question 2

Your company uses Microsoft Fabric for data analytics. You must protect sensitive data from unauthorized access in the data warehouse.

You need to manage access to specific objects in the warehouse.

What action should you take to achieve this?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Use TSQL to grant granular permissions.

### Σωστή απάντηση

Use TSQL to grant granular permissions.

### Επεξήγηση και πρόσθετη μελέτη

Using T-SQL to grant permissions on specific objects is the correct method to ensure only authorized users can interact with certain warehouse objects. Row-level security applies per table and is not granular enough. Dynamic data masking obfuscates data, but isn't considered access control. Item-level permissions prevent certain access within the warehouse, but not granular to the objects.
Configure SQL granular permissions using T-SQL

</details>

## Question 3

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a lakehouse, a data pipeline, a notebook, and several Microsoft Power BI reports.

A user named User1 plans to use SQL to access the lakehouse to analyze data. User1 must have the following access:

User1 must have read-only access to the lakehouse.
User1 must NOT be able to access the rest of the items in Workspace1.
User1 must NOT be able to use Spark to query the underlying files in the lakehouse.
You need to configure access for User1.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Share the lakehouse with User1 directly and select Read all SQL E ndpoint data.

### Σωστή απάντηση

Share the lakehouse with User1 directly and select Read all SQL E ndpoint data.

### Επεξήγηση και πρόσθετη μελέτη

Since the user only needs access to the lakehouse and not the other items in the workspace, you should share the lakehouse directly and select Read all SQL Endpoint data. The user should not be added as a member of the workspace. All members of the workspace, even viewers, will be able to open all Power BI reports in the workspace. The SQL analytics endpoint itself cannot be shared directly; the Share options only show for the lakehouse.

Lakehouse sharing and permission management - Microsoft Fabric | Microsoft Learn

</details>

## Question 4

Your company is using Microsoft Fabric to manage its data warehousing needs. The data includes sensitive customer information that must be protected according to regulatory requirements.

You need to protect sensitive data from unauthorized access while allowing authorized users to perform their tasks efficiently.

Each correct answer presents part of the solution. Which three actions should you take?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Apply sensitivity labels.

### Σωστή απάντηση

Apply sensitivity labels.

### Επεξήγηση και πρόσθετη μελέτη

Implement object-level security.

This answer is correct.
Use Microsoft Entra ID groups for user permissions.

This answer is correct.
Applying sensitivity labels, implementing object-level security, and using Microsoft Entra ID groups are effective strategies to protect sensitive data while allowing authorized users to perform their tasks efficiently. These measures ensure compliance with regulatory requirements and streamline permission management. Revoking all user permissions temporarily would disrupt legitimate access, while granting all users the Viewer role could prevent users from performing necessary tasks due to insufficient permissions.

Explore end-to-end analytics with Microsoft Fabric - Training | Microsoft Learn
Implement column-level security - Training | Microsoft Learn

</details>

## Question 5

You are designing a Microsoft Power BI semantic model that contains a measure named CompanyCosts.

You need to restrict access to CompanyCosts and ensure that only a user named User1 can view the measure in reports.

What should you implement?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

object-level security (OLS)

### Σωστή απάντηση

object-level security (OLS)

### Επεξήγηση και πρόσθετη μελέτη

OLS enables restricting access to semantic model objects, such as tables, columns, and calculations based on these columns. RLS (both static and dynamic) restricts access to specific attributes in the semantic model, such as location, category, etc.

Restrict access to Power BI model objects - Training | Microsoft Learn

</details>

## Question 6

Your organization uses Microsoft Fabric for data analytics solutions, including sensitive financial information that must be protected to comply with regulatory standards.

You need to restrict user access based on their role and protect certain sensitive data within the data warehouse.

Each correct answer presents part of the solution. Which three actions should you take?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Apply sensitivity labels.

### Σωστή απάντηση

Apply sensitivity labels.

### Επεξήγηση και πρόσθετη μελέτη

Implement row-level security.

This answer is correct.
Use dynamic data masking.

This answer is correct.
Applying sensitivity labels is essential for classifying and protecting sensitive data, ensuring compliance with organizational policies and regulatory standards. Implementing row-level security enhances data privacy by allowing users to access only the data they are authorized to view, thus maintaining control over sensitive information. Using dynamic data masking further protects sensitive data by preventing unauthorized viewing, while still allowing necessary analysis. Endorsing the warehouse will indicate that it's trustworthy, but doesn't protect the data. Granting authorized users the Viewer role might seem like a safe option but does not ensure that only authorized users can access sensitive data.

Explore end-to-end analytics with Microsoft Fabric - Training | Microsoft Learn
Secure a Microsoft Fabric data warehouse - Training | Microsoft Learn

</details>

## Question 7

Your organization uses Microsoft Fabric for data analytics. The team must protect sensitive data in a Fabric data warehouse from unauthorized access.

You need to limit data access based on different user roles and ensure to follow the principle of least privilege.

Which two actions should you take to achieve this solution?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Implement column-level security.

### Σωστή απάντηση

Implement column-level security.

### Επεξήγηση και πρόσθετη μελέτη

Implement row-level security.

This answer is correct.
To effectively limit data visibility based on user roles, implementing both row-level and column-level security is essential. Row-level security ensures that users can only access specific rows they are authorized to view, while column-level security restricts access to sensitive columns, thereby protecting critical information. Setting up item-level permissions provides more specific access control than workspace roles but lacks the necessary granularity for row and column-level restrictions. Assigning workspace roles does not address the need for role-based access control at the row or column level. Dynamic data masking, although useful for obscuring sensitive data, does not fulfill the requirement of restricting access based on user roles.

Explore end-to-end analytics with Microsoft Fabric - Training | Microsoft Learn
Secure a Microsoft Fabric data warehouse - Training | Microsoft Learn

</details>

## Question 8

You have a semantic model that loads data from an Azure SQL database and is synced via Fabric deployment pipelines to three workspaces named Development, Test, and Production.

You need to reduce the size of the query requests sent to the Azure SQL database when full semantic model refreshes occur in the Development or Test workspaces.

What should you do for the deployment pipeline?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Add a parameter to filter the data.

### Σωστή απάντηση

Add a parameter to filter the data.

### Επεξήγηση και πρόσθετη μελέτη

Adding a parameter to filter the data allows you to configure the parameter in dev and test to not load all the data. Configuring row level security changes the access and impacts the consuming users ability to view the data, it does not change the load. Connecting a workspace to ADLS to Gen 2 is around logging not loading data from Azure SQL. Incremental refresh changes the loading however the stem states full model refresh so we need all the data.

Create deployment rules for Fabric's Application lifecycle management (ALM) - Microsoft Fabric | Microsoft Learn

Manage the analytics development lifecycle - Training | Microsoft Learn

</details>

## Question 9

You have a Fabric workspace named Sales-Prod that is assigned to a Fabric capacity. The workspace contains a semantic model named SalesModel that is used by production Microsoft Power BI reports.

Users of an external tool cannot deploy metadata changes to SalesModel.

What should you configure?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Set the XMLA endpoint to Read Write on the capacity that hosts the workspace.

### Σωστή απάντηση

Set the XMLA endpoint to Read Write on the capacity that hosts the workspace.

### Επεξήγηση και πρόσθετη μελέτη

**Objective:**

1.2 Maintain the analytics development lifecycle

**What This Item Tests:**

Deploy and manage semantic models by using the XMLA endpoint

**Additional Reading:**

Troubleshoot XMLA endpoint connectivity

**Rationale:**

Setting the XMLA endpoint to Read Write enables external tools to deploy metadata changes to semantic models in a Fabric capacity; Downloading and republishing a PBIX file is not required for metadata deployment and disrupts the development lifecycle; Tenant settings for creating Fabric items are unrelated to XMLA access; Granting Admin permissions alone does not enable write operations without the XMLA endpoint set to Read Write.

</details>

## Question 10

You have a Fabric workspace named Workspace1 that contains a semantic model and a report.

You plan to connect Workspace1 to a Git repository named Repo1 and enable version control. Repo1 will be used to manage and maintain the contents of Workspace1.

You need to ensure that other users can collaborate on the semantic model and the report. The solution must minimize development effort.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

From Workspace1, create a branch and a new workspace.

### Σωστή απάντηση

From Workspace1, create a branch and a new workspace.

### Επεξήγηση και πρόσθετη μελέτη

You should create a branch and a new workspace from Workspace1 because Fabric’s Git integration supports collaborative development by allowing users to work in isolated branches that are mapped to their own workspaces. This approach enables multiple users to modify the semantic model and report independently while using Repo1 for version control, all with minimal development effort and configuration. Committing alone does not establish collaborative workflows, Power BI Desktop projects are not required for workspace-level version control in Fabric, and Fabric does not support connecting workspaces directly to local folders.

Implement version control and Git integration

</details>

## Question 11

You use Microsoft Fabric to manage an organization's data analytics solutions and need to set up a deployment pipeline.

The deployment pipeline must maintain item dependencies and support efficient data refresh processes.

Each correct answer presents part of the solution. Which three actions should you take?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Σωστή απάντηση

1. **Configure autobinding** to maintain item connections across pipeline stages.
2. **Enable incremental refresh** to process data efficiently.
3. **Use deployment rules for connections** so semantic models use the correct data-source connections at each stage.

### Σημειώσεις

These three actions maintain dependencies and support efficient refreshes. Creating a new workspace for each stage is not one of the required actions in this question.

Implement deployment pipelines - Training | Microsoft Learn
The deployment pipelines process - Training | Microsoft Learn

</details>

## Question 12

You have a Fabric deployment pipeline that has the following stages:

Development
Test
Production
The Development workspace contains a lakehouse named SalesLH. SalesLH contains an internal OneLake shortcut that points to a table in another lakehouse in the same workspace.

You need to deploy SalesLH to Test by using the deployment pipeline.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Σωστή απάντηση

Create the tables, folders, and files referenced by the shortcut in the target workspace before the deployment.

### Σημειώσεις

**Objective:**

1.2 Maintain the analytics development lifecycle

**What This Item Tests:**

Create and configure deployment pipelines

**Additional Reading:**

Lakehouse git integration and deployment pipelines
IDEAS journey to a modern data platform with Microsoft Fabric - from petabytes to insights
Fabric governance and security baselines
**Rationale:**

Create the referenced tables, folders, and files in the target workspace before deploying. An internal OneLake shortcut must be able to resolve to an existing target object in that workspace.

</details>

## Question 13

You have a Fabric workspace that contains a semantic model and five reports that use the model.

You plan to share the semantic model with another workspace and use the model in five additional reports in the new workspace.

You need to analyze the downstream dependencies of the semantic model. The solution must minimize administrative effort.

From the workspace, you open the semantic model.

What should you do next?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Select Impact analysis.

### Σωστή απάντηση

Select Impact analysis.

### Επεξήγηση και πρόσθετη μελέτη

You should select Impact analysis because it automatically identifies and summarizes all downstream dependencies of the semantic model, including reports and usage across workspaces, which is essential before sharing the model and reusing it in additional reports. Impact analysis provides a clear view of affected items and dependency scope with minimal administrative effort, whereas Lineage offers a more manual, visual relationship view without consolidated impact insights, Security is focused on permissions, and View related does not provide a comprehensive dependency or impact assessment.

Impact analysis

</details>

## Question 14

You have a Fabric workspace that contains a lakehouse named Lakehouse1.

You need to create a data pipeline and ingest data into Lakehouse1 by using the Copy data activity.

Which properties on the General tab are mandatory for the activity?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Name only

### Σωστή απάντηση

Name only

### Επεξήγηση και πρόσθετη μελέτη

For the Copy Data Activity, only the name must be defined on the General tab. All the other properties are optional.

Lakehouse tutorial - Ingest data into the lakehouse - Microsoft Fabric | Microsoft Learn

</details>

## Question 15

You have a Fabric tenant that contains a lakehouse named Lakehouse1.

You have a large 1 TB dataset in an external data source.

You need to recommend a method to ingest the dataset into Lakehouse1. The solution must provide the highest throughput. The solution must be suitable for developers who prefer the low-code/no-code option.

What should you recommend?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Use the Copy data activity of a pipeline to copy the data.

### Σωστή απάντηση

Use the Copy data activity of a pipeline to copy the data.

### Επεξήγηση και πρόσθετη μελέτη

Dataflow Gen2 is a low code / no code option to ingest data but for straight bulk copy of data is not as efficient for large data size as the copy data activity.
Using Lakehouse explorer allows for low code no code but is not good for high throughput and also assumes the data is in files in the first part but the external source has not been defined.
Notebooks are efficient however these are not a low code/no code option.

Options to get data into the Lakehouse – Microsoft Fabric | Microsoft Learn

Ingest data with Microsoft Fabric - Training | Microsoft Learn

</details>

## Question 16

You have a Fabric workspace that contains an eventhouse named Eventhouse1.

Eventhouse1 contains a KQL database named Database1 that stores real-time data.

You plan to use the Real-Time hub in Fabric to explore and use streaming data.

You need to ensure that other Fabric items can query the streaming data in Database1.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Connect Database1 to OneLake.

### Σωστή απάντηση

Connect Database1 to OneLake.

### Επεξήγηση και πρόσθετη μελέτη

You should connect Database1 to OneLake because this exposes the KQL database in Eventhouse1 as a shared, queryable data source across Microsoft Fabric. By making the database available in OneLake, other Fabric items such as data warehouses, Power BI, and pipelines can query the streaming data using supported interfaces, enabling cross-item analytics with minimal configuration. Creating pipelines or eventstreams focuses on data movement and ingestion rather than data accessibility, and alerts only monitor conditions without enabling other Fabric items to query the data.

Eventhouse OneLake Availability

</details>

## Question 17

You have a Fabric tenant that contains a lakehouse named Lakehouse1.

A notebook named Notebook1 is used to ingest data from an external data source named Externaldata1 into Lakehouse1. A notebook named Notebook2 is used to transform the data in the lakehouse.

You create a pipeline named Pipeline1 to first run Notebook1 to ingest data then on success Notebook2 to transform.

You need to configure a schedule that runs the process daily at 7:00AM.

On which object should you configure the schedule?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Pipeline1

### Σωστή απάντηση

Pipeline1

### Επεξήγηση και πρόσθετη μελέτη

Scheduling on the external datasource does not affect the load. Lakehouse1 doesn't have scheduling.
Notebook1 has scheduling but it is a per notebook configuration and will not ensure both notebooks run one after the other. Pipeline scheduling allows scheduling and running both.

Data pipeline runs - Microsoft Fabric | Microsoft Learn

Use Data Factory pipelines in Microsoft Fabric - Training | Microsoft Learn

</details>

## Question 18

You have a Fabric tenant that contains a lakehouse named Lakehouse1.

You have forecast data stored in Azure Data Lake Storage Gen2.

You plan to ingest the forecast data into Lakehouse1. The data is already formatted, and you do NOT need to apply any further data transformations. The solution must minimize development effort and costs.

Which method should you recommend to efficiently ingest the data?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Use the Copy activity in a pipeline.

### Σωστή απάντηση

Use the Copy activity in a pipeline.

### Επεξήγηση και πρόσθετη μελέτη

The Copy data activity should be used when you must copy data directly between a supported source and a destination without applying any transformations. Dataflow Gen2 or Spark notebooks should be used when you must apply data transformations. Downloading data to your local computer and uploading it is inefficient and will incur unnecessary egress charges.

Use the Copy Data activity - Training | Microsoft Learn

</details>

## Question 19

You have a Fabric tenant that contains a warehouse named Warehouse1.

You have a large 1 TB dataset in an external data source.

You need to recommend a method to ingest the dataset into Warehouse1. The solution must provide the highest throughput and support a low-code/no-code development model.

What should you recommend?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Copy data activity

### Σωστή απάντηση

Copy data activity

### Επεξήγηση και πρόσθετη μελέτη

The Copy data activity provides the highest throughput data ingestion and is considered low-code/no-code. Dataflow Gen2 is a great tool for transformations; however, for large data ingestions without any transformations, the Copy data activity performs best. Shortcuts do not move data. Spark notebooks are considered code-first.

https://learn.microsoft.com/en-us/fabric/data-warehouse/ingest-dataIngesting data into the warehouse - Microsoft Fabric | Microsoft Learn

Ingest data with Microsoft Fabric - Training | Microsoft Learn

</details>

## Question 20

You have a Fabric workspace that contains a complex semantic model for a Microsoft Power BI report.

You need to optimize the semantic model for analytical queries and use denormalization to reduce the model complexity and the number of joins between tables.

Which tables should you denormalize?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Snowflaked dimension tables

### Σωστή απάντηση

Snowflaked dimension tables

### Επεξήγηση και πρόσθετη μελέτη

A Snowflake dimension is a set of normalized tables for a single business entity. Implementing a proper star schema usually requires denormalizing the set of tables to create a single table that contains all the necessary attributes.

Understand star schema and the importance for Power BI - Power BI | Microsoft Learn

</details>

## Question 21

You are designing a semantic model for a Microsoft Power BI report. You have a table named Employee that contains the following columns: EmployeeID, EmployeeName, and EmployeePosition. You have a table named Contract that contains the following columns: EmployeeID and ContractType.

You plan to denormalize both tables and include the ContractType attribute.

You need to ensure that all the rows in the Employee table are preserved and include any matching rows from the Contract table.

Which type of join should you specify in the Power Query Merge queries transformation?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Left outer

### Σωστή απάντηση

Left outer

### Επεξήγηση και πρόσθετη μελέτη

A left outer join keeps all the rows from the left table (Employee) and brings any matching rows from the right table (Contract). A Left Anti Join will keep only rows from the left table and exclude any matching rows from the right table. An inner join brings only matching rows from both the left and right tables, while a cross join returns the Cartesian product of the rows in both tables.

Left outer join - Power Query | Microsoft Learn

</details>

## Question 22

You have a Fabric lakehouse that contains a Fabric notebook. The notebook contains a PySpark DataFrame with order data from a source system. The DataFrame contains a column named InvoiceDate.

You need to add a column named InvoiceYear that will hold only the Year value of the InvoiceDate.

Which PySpark method should you use?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

withColumn

### Σωστή απάντηση

withColumn

### Επεξήγηση και πρόσθετη μελέτη

The method to add new columns to a DataFrame is withColumn.

Lakehouse tutorial - Prepare and transform data in the lakehouse - Microsoft Fabric | Microsoft Learn

</details>

## Question 23

You have a Fabric warehouse that contains two tables named FactSales and dimGeography. The dimGeography table has a primary key column named GeographyKey. The FactSales table has a foreign key column named GeographyKey.

You create a Dataflow Gen2 query and add the tables as queries.

You plan to use the Diagram view to visually transform the data.

You need to join the two queries so that you retain all the rows in FactSales even if there are no matching rows for them in dimGeography.

What should you do after you select FactSales?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Use Merge queries as new transformation with join kind set to Left outer and FactSales as the left table and dimGeography as the right table.

### Σωστή απάντηση

Use Merge queries as new transformation with join kind set to Left outer and FactSales as the left table and dimGeography as the right table.

### Επεξήγηση και πρόσθετη μελέτη

Using the Diagram view, you can join two existing queries by using the Merge Queries as new transformation. A left join keeps all the rows from the left table even when there is no match for them in the right table. The Append queries as new transformation adds the queries to each other like a Union operation.

Create your first Microsoft Fabric Dataflow Gen2 - Microsoft Fabric | Microsoft Learn

</details>

## Question 24

You have a complex Microsoft Power BI report that retrieves data from a Microsoft SQL Server database.

You plan to use Power Query Editor to apply a series of transformations to shape the data.

You need to make sure to use transformations that ensure that query folding is still in place.

Which transformation prevents query folding?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Adding index columns

### Σωστή απάντηση

Adding index columns

### Επεξήγηση και πρόσθετη μελέτη

Unlike Pivot/Unpivot, as well as Keep rows transformations, adding the index column transformation in Power Query will always prevent the query from folding.

Query folding - Power Query | Microsoft Learn

</details>

## Question 25

You have a Parquet file named Customers.parquet uploaded to the Files section of a Fabric lakehouse.

You plan to use Data Wrangler to view basic summary statistics for the data before you load it to a Delta table.

You open a notebook in the lakehouse.

You need to load the data to a pandas DataFrame.

Which PySpark code should you run to complete the task?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

import pandas as pd

df = pd.read_parquet("/lakehouse/default/Files/Customers.parquet")

### Σωστή απάντηση

import pandas as pd

df = pd.read_parquet("/lakehouse/default/Files/Customers.parquet")

### Επεξήγηση και πρόσθετη μελέτη

To load data to a pandas DataFrame, you must first import the pandas library by running import pandas as pd. Pandas DataFrames use the File API Path vs. the File relative path that Spark uses. The File API Path has the format of lakehouse/default/Files/Customers.parquet.

Accelerate data prep with Data Wrangler - Microsoft Fabric | Microsoft Learn

</details>

## Question 26

You have a Fabric workspace that contains a Microsoft Power BI report named Sales.

You plan to use Dataflow Gen2 to add an additional column to the report. The new column must be based on the unit price of a product. Any product that has a unit price that is greater than $1,000 must be labeled as High, while any product that has a unit price that is less than $1,000 must be labeled as Regular.

What should you select on the Add column tab in Power Query Editor?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Conditional column

### Σωστή απάντηση

Conditional column

### Επεξήγηση και πρόσθετη μελέτη

The Conditional column option enables adding new columns whose values will be based on one or more conditions applied to the existing table columns.

Add a conditional column - Power Query | Microsoft Learn

</details>

## Question 27

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a lakehouse. The lakehouse contains a table named Customers and a Fabric notebook.

You plan to use the notebook to profile the data.

In the notebook, you set up the following DataFrame that references the Customers table.

df = Spark.sql(“Select * from Customers”)

You need to profile the data in the DataFrame. The solution must minimize administrative effort.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Display the DataFrame by running display(df), and then viewing the Inspect flyout tab.

### Σωστή απάντηση

Display the DataFrame by running display(df), and then viewing the Inspect flyout tab.

### Επεξήγηση και πρόσθετη μελέτη

While you can embed a Power BI report in a notebook and analyze the data by using the QuickVisualize method, this does not generate the statistics required for profiling. The Chart option is a powerful tool to visualize data, but it does not provide statistics. The Inspect button provides summarized data distribution and statistics for each column.

Notebook visualization - Microsoft Fabric | Microsoft Learn

</details>

## Question 28

You use Microsoft Power BI Desktop to connect to data stored in a CSV file.

You need to use Power Query Editor to identify the percentage of valid records in a column before loading the data to a report.

Which Power Query option should you use?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Column quality

### Σωστή απάντηση

Column quality

### Επεξήγηση και πρόσθετη μελέτη

A percentage of valid records in the column is displayed when you enable Column quality. Column distribution provides an overview of the value frequency and distribution in a column. Column profile provides statistical data about values in a column.

Profile data in Power BI - Training | Microsoft Learn

</details>

## Question 29

You have a Fabric lakehouse named Lakehouse1.

You use a notebook in Lakehouse1 to explore customer data.

You need to identify the rows of a DataFrame named df_customers in which any of the columns (axis 1 of the DataFrame) are NULL.

Which statement should you run?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

df_customers[df_customers.isnull().any(axis=1)]

### Σωστή απάντηση

df_customers[df_customers.isnull().any(axis=1)]

### Επεξήγηση και πρόσθετη μελέτη

The isnull() method identifies which individual values are NULL. To see these individual values in context, you should filter the DataFrame to include only rows in which any of the columns (axis 1 of the DataFrame) are NULL.

Exercise - Explore data with NumPy and Pandas - Training | Microsoft Learn

</details>

## Question 30

You have a Fabric data warehouse that contains two tables named dbo.FactSales and dbo.DimCustomer. The tables contain the following columns:

dbo.FactSales:
OrderID
CustomerKey
SalesAmount
dbo.DimCustomer:
CustomerKey
Region
Stakeholders require a reusable dataset that returns one row per region with:

TotalSales = sum of SalesAmount
OrderCount = count of OrderID
You create the query in the visual query editor.

You need the result to be referenced like a table in future queries by all workspace users, without requiring the users to write SQL.

What should you do in the visual query editor?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Save the query as a view.

### Σωστή απάντηση

Save the query as a view.

### Επεξήγηση και πρόσθετη μελέτη

**Objective:**

2.3 Query and analyze data

**What This Item Tests:**

Select, filter, and aggregate data by using the Visual Query Editor

**Additional Reading:**

Query and transform data
Explore data in your mirrored database using Microsoft Fabric

Query using the SQL query editor

**Rationale:**

Saving the query as a view creates a reusable database object that other users can reference like a table in future queries without needing to write or maintain SQL themselves. Saving the query as a table materializes the result and requires a managing refresh or reprocessing rather than dynamically reflecting the source data. Saving SQL in My queries stores the script for only the current user and does not create a shared dataset object. Data preview only displays results in the editor and cannot be referenced in other queries.

</details>

## Question 31

You have a table named Sales that contains the following columns:

Order_ID
Customer_ID
Product_ID
Quantity
Sales_Date
You need to write a SQL statement to find the total number of products sold for each Product_ID in January 2024.

What should you run?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

SELECT Product_ID, SUM(Quantity)

FROM Sales

WHERE MONTH(Sales_Date) = 1 AND YEAR(Sales_Date) = 2024

GROUP BY Product_ID

### Σωστή απάντηση

SELECT Product_ID, SUM(Quantity)

FROM Sales

WHERE MONTH(Sales_Date) = 1 AND YEAR(Sales_Date) = 2024

GROUP BY Product_ID

### Επεξήγηση και πρόσθετη μελέτη

The following SQL statement is the only one that correctly filters to sales for January 2024 for each product, with a total sum of the sales amount.

SELECT Product_ID, SUM(Quantity)

FROM Sales

WHERE MONTH(Sales_Date) = 1 AND YEAR(Sales_Date) = 2024

GROUP BY Product_ID

WHERE (Transact-SQL) - SQL Server | Microsoft Learn

</details>

## Question 32

You have a Fabric lakehouse named SalesLH that contains a table named SalesOrderDetail. SalesOrderDetail contains the following columns:

SalesOrderID (int)
LineTotal (decimal)
The SQL analytics endpoint is used to run read-only T-SQL queries.

You need to write a query that meets the following requirements:

Returns one row per SalesOrderID
Calculates SUM(LineTotal) as a subtotal
Returns only groups where the subtotal is greater than 100000.00
Which T-SQL clause should you use to filter the aggregated results?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

HAVING

### Σωστή απάντηση

HAVING

### Επεξήγηση και πρόσθετη μελέτη

**Objective:**

2.3 Query and analyze data

**What This Item Tests:**

Select, filter, and aggregate data by using SQL

**Additional Reading:**

SELECT - HAVING clause (Transact-SQL)

Query and analyze lakehouse data

**Rationale:**

The HAVING clause filters results after aggregation, making it the correct clause to apply conditions to grouped results such as SUM(LineTotal). The WHERE clause filters rows before aggregation and, therefore, cannot reference aggregate results. ORDER BY only sorts query results and does not filter them. DISTINCT removes duplicate rows but does not filter aggregated groups.

</details>

## Question 33

You have a Fabric warehouse that contains two tables named dbo.FactSales and dbo.DimCustomer. The tables contain the following columns:

dbo.FactSales:
OrderID
CustomerKey
SalesAmount
dbo.DimCustomer:
CustomerKey
Region
In the visual query editor, you drag both tables onto a canvas and create an inner join on CustomerKey by using Merge queries as new.

You need to generate T-SQL for the query by selecting View query. The T-SQL must include the join and aggregations defined in the visual query editor.

What should you do before selecting View query?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Enable load for the merged query result.

### Σωστή απάντηση

Enable load for the merged query result.

### Επεξήγηση και πρόσθετη μελέτη

**Objective:**

2.3 Query and analyze data

**What This Item Tests:**

Select, filter, and aggregate data by using the Visual Query Editor

**Additional Reading:**

Query using the visual query editor
Query and transform data
Explore the visual query editor

**Rationale:**

Enabling load for the merged query result ensures that the query is materialized in the visual query pipeline so the View query option can generate the corresponding T-SQL, including the join and aggregation steps defined in the editor. Adding an ORDER BY clause does not affect whether the generated SQL includes the configured joins and aggregations. Opening a separate SQL query window does not convert the visual query steps into T-SQL. Saving the query as a view occurs after query generation and is not required to view the SQL produced by the visual query editor.

</details>

## Question 34

Your organization uses Microsoft Fabric to manage its data analytics solutions. You have a Microsoft KQL database connected to multiple data sources, including a Microsoft Azure Data Explorer cluster and a Microsoft OneLake data hub.

You need to analyze recent storm event data using Kusto Query Language (KQL).

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Use a KQL Queryset.

### Σωστή απάντηση

Use a KQL Queryset.

### Επεξήγηση και πρόσθετη μελέτη

To generate a report on recent storm events using KQL, writing and running a KQL query in the KQL Queryset is the appropriate approach. This method directly utilizes the KQL capabilities of the KQL database, allowing for efficient data retrieval. Using a KQL activity in a data pipeline is not the most direct method for this task. Using a KQL query in Power BI involves visualization rather than direct querying for report generation. Using the SQL analytics endpoint is incorrect because it involves SQL, not KQL, which is necessary for this scenario.

Work with Microsoft Fabric lakehouses - Training | Microsoft Learn
Understand data warehouses in Fabric - Training | Microsoft Learn

</details>

## Question 35

Your company wants to analyze sales data in a Microsoft Fabric data warehouse. You decide to use the visual query editor for this task.

You need to identify top customers by sales volume by combining data from 'Sales' and 'Customer' tables.

Which three actions should you take to achieve this goal? Each correct answer contributes to the solution.

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Add 'Sales' and 'Customer' tables to canvas.

### Σωστή απάντηση

Add 'Sales' and 'Customer' tables to canvas.

### Επεξήγηση και πρόσθετη μελέτη

Identify common key column in both tables.

This answer is correct.
Merge tables using 'Merge queries as new'.

This answer is correct.
To effectively combine data from 'Sales' and 'Customer' tables, add 'Sales' table to canvas to initiate the query process. Identify a common key column in both tables to ensure accurate data merging, allowing for correct table joining. Use 'Merge queries as new' to join tables based on this common key, facilitating comprehensive data analysis. Using 'Append queries' instead of 'Merge queries' is ineffective for merging data based on a common key, as it only adds rows. Similarly, using 'Save as view' before merging is unnecessary, as this action is typically performed after the query is complete.

Explore the visual query editor - Training | Microsoft Learn
Explore Dataflows Gen2 in Microsoft Fabric - Training | Microsoft Learn

</details>

## Question 36

You use Microsoft Fabric for data warehousing with data in FactSales and DimProduct tables.

You need to generate a monthly report summarizing sales by product category using the visual query editor.

Each correct answer presents part of the solution. Which two actions should you take?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Add FactSales and DimProduct tables.

### Σωστή απάντηση

Add FactSales and DimProduct tables.

### Επεξήγηση και πρόσθετη μελέτη

Merge FactSales and DimProduct on ProductKey.

This answer is correct.
To create a report showing total sales for each product category by month, you must first drag and drop the FactSales and DimProduct tables onto the canvas to set up the query environment. Then, use the Merge queries as new operator to join these tables on ProductKey, which is essential for aggregating sales data by product category. Sorting or filtering for specific sales amounts are not necessary steps for this task. Selecting ProductCategory and summing SalesAmount after merging tables seems complete but misses enabling load for DimProduct.

Explore the visual query editor - Training | Microsoft Learn
Explore Dataflows Gen2 in Microsoft Fabric - Training | Microsoft Learn

</details>

## Question 37

You are developing a Microsoft Power BI semantic model.

Two tables in the data model are not connected in a physical relationship.

You need to establish a virtual relationship between the tables.

Which DAX function should you use?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

TREATAS()

### Σωστή απάντηση

TREATAS()

### Επεξήγηση και πρόσθετη μελέτη

TREATAS() applies the result of a table expression as filters to columns from an unrelated table. USERELATIONSHIP() activates different physical relationships between tables during a query execution. CROSSFILTER() defines the cross filtering direction of a physical relationship. PATH() returns a string of all the members in the column hierarchy.

TREATAS function - DAX | Microsoft Learn

</details>

## Question 38

You have a Fabric workspace and a Microsoft Power BI semantic model that contains the following tables:

Sales (ProductKey,CustomerKey,DateKey,SalesAmont)
Product (ProductKey,ProductName,ProductCategory)
Date (DateKey,Date,Month,Year)
Customer (CustomerKey,CustmomerName,CustomerCity)
The Product table has a 1-to-many relationship with the Sales table based on ProductKey.

The Customer table has a 1-to-many relationship with the Sales table based on CustomerKey.

The Date table has a 1-to-many relationship with the Sales table based on DateKey.

You need to create a Power BI report so that end users can use a one column chart to analyze SalesAmount by ProductCategory or Year or CustomerCity. The solution must minimize development effort.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Set up a Fields parameter with ProductCategory, Year, and CustomerCity. Use the Fields parameter in the visual.

### Σωστή απάντηση

Set up a Fields parameter with ProductCategory, Year, and CustomerCity. Use the Fields parameter in the visual.

### Επεξήγηση και πρόσθετη μελέτη

While you can use bookmarks to navigate between report pages or change the visibility of visuals, using the Fields parameter is a much easier and more efficient way of allowing an end-user to change the fields on a visual. Developing a custom visual with built-in buttons to switch the items on the axis, involves extra development effort.

Use parameters to visualize variables - Power BI | Microsoft Learn

</details>

## Question 39

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 is assigned to an F64 Fabric capacity and contains a warehouse.

You are working on a custom Microsoft Power BI semantic model that sources data from the warehouse tables. You apply optimization best practices to reduce the model size. You estimate that once the model is published to the Power BI service and fully loaded, it will approach 50 GB.

Which option should you configure to enable the semantic model to refresh in the Power BI service?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Large semantic model storage format

### Σωστή απάντηση

Large semantic model storage format

### Επεξήγηση και πρόσθετη μελέτη

The large semantic model storage format can be enabled from the Power BI service from the semantic model settings. It will allow data to grow beyond the 10-GB limit for Power BI premium capacities or Fabric capacities of F64 or higher. The other options do not change the default limit of 10 GB after compression.

Design scalable semantic models

</details>

## Question 40

You are designing a Microsoft Power BI semantic model that will contain 50 different measures, such as Sales Amount, Order Quantity, and Refund Amount.

For each measure, you need to create the same set of time intelligence calculations such as month-to-date, year-to-date, and year-over-year change.

The solution must minimize administrative effort.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Create a calculation group.

### Σωστή απάντηση

Create a calculation group.

### Επεξήγηση και πρόσθετη μελέτη

Calculation groups are an efficient way to reduce the number of measures in the semantic model by grouping common measure expressions. The main benefit of using calculation groups is to reduce the overall number of measures that must be created and maintained.

Design scalable semantic models

</details>

## Question 41

You are developing a large Microsoft Power BI semantic model that will contain a fact table. The table will contain 400 million rows.

You plan to leverage user-defined aggregations to speed up the performance of the most frequently run queries.

You need to confirm that the queries are mapped to aggregated data in the tables.

Which two tools should you use? Each correct answer presents part of the solution.

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

DAX Studio

### Σωστή απάντηση

DAX Studio

### Επεξήγηση και πρόσθετη μελέτη

SQL Profiler

This answer is correct.
SQL Server Profiler and DAX Studio can detect whether queries were returned from the in-memory cache storage engine or pushed by DirectQuery to the data source.

User-defined aggregations - Power BI | Microsoft Learn

</details>

## Question 42

You use Tabular Editor 2 to perform advanced data processing of the largest tables in a Microsoft Power BI semantic model.

You need to load data to a table without rebuilding hierarchies and relationships and without recalculating calculated columns and measures.

Which process mode should you use?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Process Data

### Σωστή απάντηση

Process Data

### Επεξήγηση και πρόσθετη μελέτη

Process Data loads data to a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures. With Process Default, hierarchies, calculated columns, and relationships are built or rebuilt (recalculated). Process Defrag defragments the auxiliary table indexes, while Process Recalc recalculates hierarchies, relationships, and calculated columns on a database level.

Process Database, Table, or Partition (Analysis Services) | Microsoft Learn

</details>

## Question 43

You are designing a dimension table named dimCustomer that will be used to analyze historical sales data by customer zip code. The table will be joined to a table named FactSales on a column named CustomerKey to report historical sales data by customer zip code.

The sales data must be reported based on the zip codes of customers at the time of the sale, not their most recent zip code.

You need to design dimCustomer to contain a fixed number of columns.

Which type of dimension should you choose for dimCustomer?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

type 2 slowly changing dimension (SCD)

### Σωστή απάντηση

type 2 slowly changing dimension (SCD)

### Επεξήγηση και πρόσθετη μελέτη

Type 0 SCD attributes never change and will not fit the requirement. Type 1 SCD overwrites the changes and historical analysis of data based on the zip code at the time of the sales will be impossible. Type 2 SCD will keep track of historical data by adding new records with new keys whenever an attribute changes. Type 3 SCD adds new columns to a table for attribute changes.

Explore data load strategies - Training | Microsoft Learn

</details>

## Question 44

You have a Fabric lakehouse.

You are building a semantic model for a sales dataset.

Report users require that visuals always reflect the latest data in the lakehouse.

You need to configure the semantic model.

Which storage mode should you use?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Direct Lake

### Σωστή απάντηση

Direct Lake

### Επεξήγηση και πρόσθετη μελέτη

**Objective:**

3.1 Design and build semantic models

**What This Item Tests:**

Choose a storage mode

**Additional Reading:**

Choose the best storage mode
Table storage mode in Power BI semantic models
Design scalable semantic models
**Rationale:**

Direct Lake enables a semantic model to query Delta tables stored in OneLake directly, without importing data into the model and without relying on scheduled refresh. Queries read the latest data from the lakehouse while maintaining high performance because the engine reads the Delta files directly. Import storage mode loads data into the semantic model and requires a refresh to reflect the changes. DirectQuery sends queries to the underlying data source at runtime but is typically used for relational sources rather than directly scanning Delta tables in OneLake. Composite models combine storage modes but are not required when the goal is to query lakehouse Delta tables directly without importing data.

</details>

## Question 45

You have an Azure SQL database.

You have a Microsoft Power BI report connected to a semantic model that uses a DirectQuery connection to the database.

You need to reduce the number of queries sent to the database when a user is interacting with the report by using filters and/or slicers.

What should you do?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Add apply buttons to all the basic filters.

### Σωστή απάντηση

Add apply buttons to all the basic filters.

### Επεξήγηση και πρόσθετη μελέτη

Adding apply buttons will pause all requests to the Azure SQL database until you finalize your filter and/or slicer selections. Then a single request can be sent once the apply button is selected. The other options will not change the number of unique query requests sent to the database.

Create Apply all and Clear all slicers buttons in reports - Power BI | Microsoft Learn

DirectQuery optimization scenarios with the Optimize ribbon in Power BI Desktop - Power BI | Microsoft Learn

</details>

## Question 46

You have a Microsoft Power BI semantic model assigned to you for ownership and maintenance.

You need to perform an audit on the model to identify and resolve potential performance or design issues.

Which Tabular Editor tool should you use?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Best Practices Analyzer

### Σωστή απάντηση

Best Practices Analyzer

### Επεξήγηση και πρόσθετη μελέτη

Only Best Practices Analyzer lets you specify a ruleset to review the model and multiple options for quick fixes by using C# scripts.

External tools in Power BI Desktop - Power BI | Microsoft Learn

Best Practice Analyzer | Tabular Editor Documentation

</details>

## Question 47

You have a semantic model that contains a Calendar Dimension table and a Sales fact table. The tables have a 1-to-many relationship.

From DAX studio, you discover a DAX measure that is performing slowly against the model.

You plan to modify a filter in the measure to improve performance.

Which measure provides the best performance for the model?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

CALCULATE( [Sales],

Calendar[Year] = 2023

)

### Σωστή απάντηση

CALCULATE( [Sales],

Calendar[Year] = 2023

)

### Επεξήγηση και πρόσθετη μελέτη

Filtering on the Calendar Dimension table will almost always perform faster than filtering directly on any fact table, as that requires more processing by both the DAX formula and the storage engine.

Avoid using FILTER as a filter argument in DAX - DAX | Microsoft Learn

</details>

## Question 48

You have a Fabric semantic model in Import storage mode. The model contains a table named Sales. Sales contains three years of data and a column named TransactionDate (datetime).

Refreshing the table takes more than three hours.

You need to ensure that scheduled refresh processes only new and updated rows.

What should you do in Microsoft Power BI Desktop?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

In Power Query, configure incremental refresh for the table.

### Σωστή απάντηση

In Power Query, configure incremental refresh for the table.

### Επεξήγηση και πρόσθετη μελέτη

**Objective:**

3.2 Optimize enterprise-scale semantic models

**What This Item Tests:**

Implement incremental refresh for semantic models

**Additional Reading:**

Data refresh in Power BI
**Rationale:**

Incremental refresh requires defining the RangeStart and RangeEnd parameters, applying them as a filter on the date column in Power Query, and configuring an incremental refresh policy for the table. This enables refresh operations to process only new and changed partitions. Enabling large semantic model storage format increases model capacity but does not change the refresh behavior. Creating partitions manually does not enable service-managed incremental refresh. Converting the model to DirectQuery removes the import refresh scenario rather than optimizing it.

</details>

## Question 49

You have a Fabric warehouse named Warehouse1.

You discover a SQL query that performs poorly, and you notice that table statistics are out of date.

You need to manually update the statistics to improve query performance for the table.

Which column statistics should you update?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

columns used in GROUP BY clauses

### Σωστή απάντηση

columns used in GROUP BY clauses

### Επεξήγηση και πρόσθετη μελέτη

When manually creating/updating statistics for optimizing query performance, you should focus on columns used in JOIN, ORDER BY, and GROUP BY clauses.

Statistics - Microsoft Fabric | Microsoft Learn

</details>

## Question 50

You have a Fabric workspace that contains a lakehouse named Lakehouse1. Lakehouse1 contains a table named FactSales that is ingested by using a Dataflow Gen2 query.

There are several applied steps and transformations applied to FactSales during the ingestion process.

You notice that due to the number of Power Query transformations, there are occasional timeout issues for the dataflow.

You need to recommend a solution to prevent the timeout issues.

You have already confirmed that the query cannot be further optimized and that changing the refresh time does not improve the timeout issues.

Which additional action should you recommend?

<details>
<summary>Εμφάνιση απάντησης και επεξήγησης</summary>

### Η απάντησή σου στο αρχικό assessment

**Αποτέλεσμα:** Σωστή

Create a second dataflow that ingests the FactSales table with no additional transformations, and then connect the original dataflow to transform the FactSales data by using this second dataflow.

### Σωστή απάντηση

Create a second dataflow that ingests the FactSales table with no additional transformations, and then connect the original dataflow to transform the FactSales data by using this second dataflow.

### Επεξήγηση και πρόσθετη μελέτη

It is considered best practice to create a staging first dataflow that ingests the raw data first, and then a second dataflow to transform the data, commonly applied when there are performance or timeout issues for a query.

Best practices for designing and developing complex dataflows - Power Query | Microsoft Learn

</details>

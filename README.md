## 1) What Is a Data Warehouse?

A data warehouse is a type of data management system that centralizes and consolidates large amounts of data from multiple sources.Data warehouses are solely intended to perform queries and analysis and often contain large amounts of historical data.
A well-designed data warehouse will perform queries very quickly, deliver high data throughput, and provide enough flexibility for end users to “slice and dice”

According to this definition, data warehouses are

 - Subject-oriented. They can analyze data about a particular subject or functional area (such as sales).

- Integrated. Data warehouses create consistency among different data types from disparate sources.

- Nonvolatile. Once data is in a data warehouse, it’s stable and doesn’t change.

- Time - variant. Data warehouse analysis looks at change over time.

## 2) What is a Cloud Data Warehouse?
A cloud data warehouse uses the cloud to ingest and store data from disparate data sources.

The original data warehouses were built with on-premises servers. In many cases, they can offer improved governance, security, data sovereignty, and better latency. However, on-premises data warehouses are not as elastic and they require complex forecasting to determine how to scale the data warehouse for future needs. Managing these data warehouses can also be very complex.

On the other hand, some of the advantages of cloud data warehouses include:

Elastic, scale-out support for large or variable compute or storage requirements
Ease of use
Ease of management
Cost savings

## 3) What is Data Lake?
A Data Lake is a storage repository that can store a large amount of structured, semi-structured, and unstructured data. It is a place to store every type of data in its native format. When organizations need low-cost storage for unformatted, unstructured data from multiple sources that they intend to use for some purpose in the future, a data lake might be the right choice

## 4) Data Lake vs Datawarehous
  
  - ### 1 Data Storage 
  A data lake contains all an organization's data in a raw, unstructured form, and can store the data indefinitely — for immediate or future use.
 
 A data warehouse contains structured data  that has been cleaned and processed, ready for strategic analysis based on predefined business needs.

- ### 2. Users	
Data from a data lake — with its large volume of unstructured data — is typically used by data scientists and engineers who prefer to study data in its raw form to gain new, unique business insights.

Data from a data warehouse is typically accessed by managers and business-end users looking to gain insights from business KPIs, as the data has already been structured to provide answers to pre-determined questions for analysis.

- ### 3. Analysis	
Data lake used for Predictive analytics, machine learning, data visualization, BI, big data analytics.

Datawarehouse used for Data visualization, BI, data analytics.

- ### 4. Schema	
Data Lake - Schema is defined after the data is stored in a data lake , making the process of capturing and storing the data faster.

In a data warehouse, the schema is defined before the data is stored. This lengthens the time it takes to process the data, but once complete, the data is at the ready for consistent, confident use across the organization.

- ### 5. Processing	
ELT (Extract, Load, Transform). In this process, the data is extracted from its source for storage in the data lake, and structured only when needed.

ETL (Extract, Transform, Load). In this process, data is extracted from its source(s), scrubbed, then structured so it's ready for business-end analysis.

- ### 6. Cost	
Storage costs are fairly inexpensive in a data lake vs data warehouse. Data lakes are also less time-consuming to manage, which reduces operational costs.

Data warehouses cost more than data lakes, and also require more time to manage, resulting in additional operational costs.

## 5) Database vs Datawarehouse

- Database is a collection of related data that represents some elements of the real world whereas Data warehouse is an information system that stores historical and commutative data from single or multiple sources.
- Database is designed to record data whereas the Data warehouse is designed to analyze data.
- Database is application-oriented-collection of data whereas Data Warehouse is the subject-oriented collection of data.
- Database uses Online Transactional Processing (OLTP) whereas Data warehouse uses Online Analytical Processing (OLAP).
- Database tables and joins are complicated because they are normalized whereas Data Warehouse tables and joins are easy because they are denormalized.
- Data stored in the Database is up to date.	Current and Historical Data is stored in Data Warehouse. May not be up to date.
- Flat Relational Approach method is used for data storage in the database.	Data Ware House uses dimensional and normalized approach for the data structure. Example: Star and snowflake schema.

## 6) What is OLTP?
An OLTP system captures and maintains transaction data in a database. Examples include banking and credit card activity or retail checkout scanning.

In OLTP, the emphasis is on fast processing, because OLTP databases are read, written, and updated frequently. If a transaction fails, built-in system logic ensures data integrity.

## 7) What is OLAP?
OLAP applies complex queries to large amounts of historical data, aggregated from OLTP databases and other sources, for analytics, and business intelligence projects.

Online analytical processing (OLAP) is a system for performing multi-dimensional analysis at high speeds on large volumes of data.

In OLAP, the emphasis is on response time to these complex queries. Examples include year-over-year financial performance or marketing lead generation trends. 

|OLTP                          |   OLAP  |
|------------------------------|---------|
|Operational data; OLTPs are the original source of the data.|  Consolidation data; OLAP data comes from the various OLTP Databases       | 
| Purpose of data: To control and run fundamental business tasks | Purpose of data :To help with planning, problem solving, and decision support|
| Inserts and Updates : Short and fast inserts and updates initiated by end users |Periodic long-running batch jobs refresh the data|
|Queries : Relatively standardized and simple queries Returning relatively few records | Often complex queries involving aggregations|
|Processing Speed : Typically very fast |Depends on the amount of data involved; batch data refreshes and complex queries may take many hours; query speed can be improved by creating indexes|
|Database Design : Highly normalized with many tables|Typically de-normalized with fewer tables; use of star and/or snowflake schemas|
|Backup religiously; operational data is critical to run the business, data loss is likely to entail significant monetary loss and legal liability|Instead of regular backups, some environments may consider simply reloading the OLTP data as a recovery method|
|Space Requirements : Can be relatively small if historical data is archived| Larger due to the existence of aggregation structures and history data; requires more indexes than OLTP
## 8) Types of Facts

- Additive:

Additive facts are facts that can be summed up through all of the dimensions in the fact table. A sales fact is a good example for additive fact.
|   f1   |
|------|
|date|
|Store|
|Product|
|Sales_Amount|

The purpose of this table is to record the sales amount for each product in each store on a daily basis. Sales_Amount is the fact. In this case, Sales_Amount is an additive fact, because you can sum up this fact along any of the three dimensions present in the fact table -- date, store, and product. 

For example, the sum of Sales_Amount for all 7 days in a week represents the total sales amount for that week.

- Semi-Additive:

Semi-additive facts are facts that can be summed up for some of the dimensions in the fact table, but not the others.
Eg: Daily balances fact can be summed up through the customers dimension but not through the time dimension.

- Non-Additive:

Non-additive facts are facts that cannot be summed up for any of the dimensions present in the fact table.
Eg: Facts which have percentages, ratios calculated.

- Factless Fact Table:

In the real world, it is possible to have a fact table that contains no measures or facts. These tables are called "Factless Fact tables".

Eg: A fact table which has only product key and date key is a factless fact. There are no measures in this table. But still you can get the number products sold over a period of time.

## 9) Types of Fact tables

### Transaction Fact Table 
- Grain set to a single transaction. Lowest level of details.
- Mostly additive facts
### Periodic Sanpshot Fact Table
- This type of fact table describes the state of things in a particular instance of time, and usually includes more semi-additive and non-additive facts
- A periodic fact table or periodic fact entity stores one row for a group of transactions that happen over a period of time. Month end batch etc.

![image](https://user-images.githubusercontent.com/67767423/150616261-aeee0d06-2bd3-40c6-948d-7ebf3b6aa068.png)

### Accumulated Fact Table
- An accumulating fact table or accumulating fact entity stores one row for the entire lifetime of an event.
- It contains Multiple date dimensions , such as order fulﬁllment or claim processing, that have a deﬁned start point, standard intermediate steps, and deﬁned end point.
- As pipeline progress occurs, the accumulating fact table row is revisited and updated like Claim paid date will be updated once claim is settled. 

Initial stage, Paid date would be not available but updated once claim was paid

![image](https://user-images.githubusercontent.com/67767423/150617567-2fcbceaf-cbd7-44d4-9f45-0c6b96d4b7f9.png)

![image](https://user-images.githubusercontent.com/67767423/150617658-913dec10-dfc7-423a-9d75-a32e80f06cec.png)

## 10) Types of Dimension Tables

- Conformed Dimension
A conformed dimension is the dimension that is shared across multiple data mart or subject area. Company may use the same dimension table across different projects without making any changes to the dimension tables.

Conformed dimension example would be Customer dimension, i.e. both marketing and sales department can use Customer dimension for their reporting purpose.

- Degenerate Dimension  
A degenerate dimension is a dimension key in the fact table that does not have its own dimension table. This is because useful dimensional data is sometimes stored in a fact table to reduce duplication, especially when you have a very large fact table and also avoids expensive join between tables. Example Order Number

- Junk Dimension

In data warehouse design, frequently we run into a situation where there are yes/no indicator fields in the source system. A junk dimension combines several low-cardinality flags and attributes into a single dimension table rather than modeling them as separate dimensions. If the cardinality of each attribute is relatively low, and there are only a few attributes, then the easiest way to create the dimension is to cross-join the source system lookup tables. This creates all possible combinations of attributes, even if they might never exist in the real world.

## 11) Slowly changing Dimensions -

Slowly changing dimensions or SCD are dimensions that changes slowly over time, rather than regular basis.  In data warehouse environment, there may be a requirement to keep track of the change in dimension values and are used to report historical data at any given point of time.

### Type 1: 
- The new record replaces the original record. No trace of the old record exists.

When no historical reporting needed then use this approach

In our example, recall we originally have the following table:

| Customer Key | 	Name	| State
| ------------ |-------|------
|1001	| Christina	| Illinois

After Christina moved from Illinois to California, the new information replaces the new record, and we have the following table:

| Customer Key	| Name	| State
|--------------|-------|----
|1001	| Christina	| California

### Type 2 : 

In Type 2 Slowly Changing Dimension, a new record is added to the table to represent the new information. Therefore, both the original and the new record will be present. The new record gets its own primary key.

| Customer Key | 	Name	| State|version no
| ------------ |-------|------|-----
|1001	| Christina	| Illinois|1
|1005|Christina	| California|2

But we can't understand which record out of these two is current or active record. So version number column is added and we can use max version into reporting.

 Some SCD type 2 implementations use effective from and to date with flag indicating latest record. Version = 1 and Eff End Date = NULL indicates current or latest tuple versions. In some implementation, data modeller uses future date (9999-12-31) as effective to date.
 
| Customer Key | 	Name	| State|Eff Start Date|Eff End Date|version
| ------------ |-------|------|-----|----------|--------
|1001	| Christina	| Illinois|01-JAN-2021|31-DEC-2021|0
|1005|Christina	| California|01-JAN-2022|NULL|1

Advantages:

- This allows us to accurately keep all historical information.

Disadvantages:

- This will cause the size of the table to grow fast. In cases where the number of rows for the table is very high to start with, storage and performance can become a concern.

- This necessarily complicates the ETL process.

### Type 3 :

Adds new attribute to store changed value, preserve partial history.

|Customer Key |	Name	| Original State	| Current State	| Effective Date
|-------------|-----|-----------------|---------------|------------
|1001	|Christina	|Illinois	|California	|15-JAN-2003

Advantages:

- This does not increase the size of the table, since new information is updated.

- This allows us to keep some part of history.

Disadvantages:

- Type 3 will not be able to keep all history where an attribute is changed more than once. For example, if Christina later moves to Texas on December 15, 2003, the California information will be lost.

### 12) Surrogate Key vs Natural Key :

- Natural key

A natural key is a column or set of columns that already exist in the table (e.g. they are attributes of the entity within the data model) and uniquely identify a record in the table.  Since these columns are attributes of the entity they obviously have business meaning.

- Natural Key Pros

1)  Key values have business meaning and can be used as a search key when querying the table

2) Column(s) and primary key index already exist so no disk extra space is required for the extra column/index that would be used by a surrogate key column

3) Fewer table joins since join columns have meaning.  For example, this can reduce disk IO by not having to perform extra reads on a lookup table

- Natural Key Cons

1) disadvantage of natural keys is that because they have business meaning they are effectively coupled to your business: you may need to rework your key when your business requirements change. For example, if your users decide to make CustomerNumber alphanumeric instead of numeric then in addition to updating the schema for the Customer table (which is unavoidable) you would have to change every single table where CustomerNumber is used as a foreign key.

2) Can't enter record until key value is known.  It's sometimes beneficial for an application to load a placeholder record in one table then load other tables and then come back and update the main table.

- Surrogate Key

A surrogate key is a system generated (could be GUID, sequence, etc.) value with no business meaning that is used to uniquely identify a record in a table. It goes sequential.

- Surrogate Key Pros

 1) No business logic in key so no changes based on business requirements.  
 2) Better performance since key value is smaller.  Less disk IO is required on when accessing single column indexes. Faster query performance.

- Surrogate Key Cons

1) Extra column(s)/index for surrogate key will require extra disk space

2) Requires more table joins to child tables since data has no meaning on its own.

3) Key value has no relation to data so technically design breaks 3NF
4) Surrogate keys are typically not useful when searching for datasince they have no meaning

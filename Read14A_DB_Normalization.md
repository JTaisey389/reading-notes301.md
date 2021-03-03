# Code 301 Reading Notes

## Read 14 Database Normalization

### Introduction to Database Normalization
- Database Normalization is a process used to organize databases into tables and columns. The main idea with this is a table should be a specific topic and only supporting topics included. We use a spreadsheet to contain the the information as an example, we can contain data about salespeople and customers.

- What this can do:
1. Identify salespeople in your organization
2. List all customers your company calls upon to sell a product
3. Identify which salespeople call on specific customers

- By limiting a table to one purpose you reduce the number of duplicate data contained within your database. This eliminates a few issues from database modifications

- There are three normal forms most databases use. As a table satisfies each successive normalization form, there is less chance to modification anomalies and more focused toward a sole purpose or topic. 

- There are three reasons to normalize a database. 
1. Minimize duplicate data,
2. Avoid data modification issues
3. Simplify Queries

- Here is an example: 

<img src="https://www.essentialsql.com/wp-content/uploads/2014/06/FirstNormalFormUnormalized-1.png">

- The first thing to note is the table server many purposes.
1. Identify the organizations salespeople
2. Listing the sales offices and phone numbers
3. Associate a salesperson with a sales office
4. Showing each salesperson customer

### Data Duplication and Modification Anomalies
- Take note that each SalePerson that is listed has a SalesOffice and and OfficeNumber. There are duplicate saleseperson data which presents two problems.

1. It increases storage and decreases performance
2. It becomes more difficult to maintain data changes

### Insert Anomaly
- There are facts that we cannot record until we know information for the entire row. With out example we cannot record a new sales office until we know the sales person. 

### Update Anomaly
- In this case the same information  persists in several rows. For example if the office number changes, there are other updates that need to be made. If the rows do not update inconsistencies begin to appear.

### Deletion Anomaly
- Deleting rows causes a removal of more than one set of facts. For example if John retires then deleting that row causes us to lose information about the New York office. 

- Example: 
<img src="https://www.essentialsql.com/wp-content/uploads/2014/06/Intro-Deletion-Anomaly-e1425554658757.png">

### Search and Sort Issues
- The final reason to consider is making it easier to search and sort the data. In the table if you want to search for a specific customer such as Ford, you have to construct a query like this.

- Example:

`SELECT SalesOffice`
`FROM SalesStaff`
`WHERE Customer1 = ‘Ford’ OR`
      `Customer2 = ‘Ford’ OR`
      `Customer3 = ‘Ford’`

### Definition of Database Normalization
- There are three common forms of database normalization: 1st, 2nd, and 3rd normal form. They can be abbreviated as 1NF, 2NF, and 3NF. 

1. First Normal Form: The information is stored in a relational table with each column containing atomic values.
2. Second Normal Form: The table is in first normal form and all the columns depend on the table's primary key.
3. Third Normal Form: The table is in second normal form and all of its columns are not transitively dependent on the primary key. 


### Table of Contents

### Link to Code 102
- [Code 102 Reading Notes](https://jtaisey389.github.io/reading-notes/)

### Link to Code 201
- [Reading Notes 201](https://jtaisey389.github.io/reading-notes201.md/)

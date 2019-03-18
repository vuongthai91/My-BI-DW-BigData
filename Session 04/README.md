# Business Intelligence and Data Warehouse Course

## Session 4

The topic of this session is **Data Modelling** (in the context of data warehousing). This repository includes the content discussed in class:

  - Concepts
  - Exercises
  - FAQ
  - References

## Main concepts

  - **Star Schema**: A single large central fact table (that represents business process to analyze) and one table for each dimension (that represents business perspective of analysis).
  - **Snowflake Schema**: Variant of star schema model. It consist in a single, large and central fact table and one or more tables for each dimension. Dimension tables are normalized splitting dimension table data into additional tables.
  - **Fact Constellation**: Multiple fact tables share multiple dimension tables. This group of tables is viewed as collection of stars hence.
  - **Data Vault**: novel approach for data modelling. It be understood as a hybrid approach encompassing the best of breed between 3NF and Star Schemas. It is based on hubs (business concepts), links (relations between hubs) and satellites (attributes for links and hubs). 
 
## How to use this content

  - Fork this repository or download the content
  - Required Software:
	  - MySQL
	  - MySQL Workbench
  - All schemas have been created with MySQL Workbench.

## What you can learn in the videos

  - [MySQL Workbench - Introduction](https://vimeo.com/280760052)

## FAQ

### Can we use an iterative/incremental development for the dw?

Yes. We can use user story as work unit to begin building and evolving the DW/BI system. For example, let's assume you have the following user story:
 
> **As** a Marketing Analyst
> **I need** the ability to see the marketing budget per year
> **In order to identify** the evolution of marketing budget

From this user story we can identify one dimension (date) and one fact table (budget). Let's assume now a new user story:

> **As** a Marketing Analyst
> **I need** the ability to see the marketing budget per campaign
> **In order to identify** the distribution of marketing budget per campaign

From this second story it is clear that we need to add a new dimension to our model (campaign).

Most of the times, we refer iterative/incremental development as [**Agile Data Modeling**](http://agiledata.org/essays/agileDataModeling.html).

### How do we track incremental changes?

To keep track of incremental changes in the structure of the dimensional model, it is suitable to use a database change management tool. Some of the best known Open Source tools are [Flyway](https://flywaydb.org/), [Liquibase](http://www.liquibase.org/) or [DBDeploy](http://dbdeploy.com/).

### Which options do I have for a data warehouse database?

There are many options:

 - Relational databases: [MySQL](https://mysql.com), [PostgreSQL](https://www.postgresql.org), [MSSQL](https://www.microsoft.com/en-us/sql-server) or [Oracle](www.oracle.com) among many others.
 - Columnar databases: [Clickhouse](https://clickhouse.yandex) among many others.
 - Analytic data warehouses: such as [Exasol](https://www.exasol.com), [Teradata](https://www.teradata.com), [Vertica](https://www.vertica.com) among many others.
 - Hadoop-based solutions: [Amazon Redshift](https://aws.amazon.com/redshift/), [Google BigQuery](https://cloud.google.com/bigquery/) or [Snowflake](https://snowflake.net) among many others.
 - Appliances: [Yellowbrick](https://yellowbrick.com), [IBM's Netezza](https://www.ibm.com/analytics/netezza) or [Teradata](https://www.teradata.com) among many others.

Choosing one or another depends on many factors such as data size, purpose, knowledge, budget, etc.

### What can I do if I forget my MySQL password?

If you forget your MySQL password or don't know how to change MySQL root password, follow these steps.

#### Windows

Use the installer (that you can find in control panel > uninstall programs) to restore your MySQL installation. If this process is not working then follow these steps.

1) Run Command Prompt (Type cmd into the search menu in Windows 8/10) and run it as Administrator and execute the following commands to stop and remove MySQL service.

```
Net stop MySQL
SC delete MySQL
```

The service should now be gone.

2) Go to Control Panel > Programs > Programs and Features, select MySQL Server and click Uninstall.

3) Open Windows Explorer and go to Organize > Folder and search options, Select the “View” tab and under “Hidden files and Folders” choose “Show hidden files and folders”. Now explore the following locations and delete following folders.

> Note: You will need enable “Hidden items” in file manager in order to get to the program data files.

C:\Program Files\MySQL
C:\Program Files (x86)\MySQL
C:\ProgramData\MySQL

And if exists, delete it too:

C:\Users\[User-Name]\AppData\Roaming\MySQL

Its also probably worth scanning and fixing the registry for anything that’s been left behind using a program to repair your registry and clear out any old files. The registry entries are:

HKEY_CURRENT_USER\Software\MySQL AB
HKEY_LOCAL_MACHINE\SOFTWARE\MySQL AB

If multiple users sign on to your machine, you will also have to look under each user:

HKEY_USERS\*\Software\MySQL AB 

#### Mac

**Option 1**

Open System Preferences > Initializa Database, then

 - Enter new password
 - Choose "Use Legacy Password Encription"

**Option 2**

If option 1 is not working, open terminal and follow these steps

 - Stop MySQL:

``` 
sudo /usr/local/mysql/support-files/mysql.server stop
``` 

  - Restart mysql with the option "skip grants tables":

``` 
sudo /usr/local/mysql/bin/mysqld_safe --skip-grant-tables
``` 

  - Update the "root" user password:

``` 
UPDATE USER SET AUTHENTICATION_STRING=password('NewPassword') WHERE user='root'
``` 

 - Flush privileges

``` 
FLUSH PRIVILEGES
``` 

**Option 3**

If option 2 is not working, in this link you will find the steps (for every OS): http://dev.mysql.com/doc/refman/5.7/en/resetting-permissions.html. 

**Option 4**

Last but not least. If the previous options are not working, you can uninstall MySQL and completely remove it from your Mac:

  - Open a terminal window
  - Write the following instructions (one by one):

```  
sudo rm /usr/local/mysql
sudo rm -rf /usr/local/mysql*
sudo rm -rf /Library/StartupItems/MySQLCOM
sudo rm -rf /Library/PreferencePanes/My*
sudo rm -rf ~/Library/PreferencePanes/My*
sudo rm -rf /Library/Receipts/mysql*
sudo rm -rf /Library/Receipts/MySQL*
sudo rm -rf /private/var/db/receipts/*mysql*
sudo rm -rf /var/db/receipts/com.mysql.*
sudo rm /Library/LaunchDaemons/com.oracle.oss.mysql.mysqld.plist
``` 

After this, you need to install again MySQL and keep the auto-generated password. Then:

 - Start the database (from the system preferences).
 - Open MySQL Workbench and create a connection. 
 - It will ask for the generated password. After that a new window will appear to propose a new password. Choose one easy to remember. After this you will be able to enter to the server with your new password.

### I have to manage other databases and not only MySQL, what can I do?

You can use other programs for managing and modelling multiple databases such [HeidiSQL](https://www.heidisql.com) or [Toad](https://www.toadworld.com).

## References

  - https://www.vertabelo.com/blog/technical-articles/data-vault-series-agile-modeling-not-an-option-anymore
  - https://www.vertabelo.com/blog/technical-articles/data-vault-series-data-vault-2-0-modeling-basics
  - https://www.vertabelo.com/blog/technical-articles/data-vault-series-the-business-data-vault
  - https://www.vertabelo.com/blog/technical-articles/data-vault-series-building-an-information-mart-with-your-data-vault
  - Modeling Data Lake Metadata with a Data Vault. [arXiv:1807.04035](https://arxiv.org/abs/1807.04035)
  - Building an Effective Data Warehousing for Financial Sector. [arXiv:1709.05874](https://arxiv.org/abs/1709.05874)
  - Benchmarking data warehouses. [arXiv:1701.00399](https://arxiv.org/abs/1701.00399)
  - Design and implementation of the Customer Experience Data Mart in the Telecommunication Industry: Application Order-To-Payment end to end process. [arXiv:1401.0534](https://arxiv.org/abs/1401.0534)

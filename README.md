# Business Intelligence and Data Warehouse Course

This repository contains all necessary inputs to run the course hands-on labs. 

## Repository contents (by session)

  - Additional articles and documents
  - MySQL Workbench Schemas
  - ETL processes
  - Datasets
  - Tableau files
  - Videos

## Software Installation

  - **Data Warehouse**: MySQL (database) and MySQL Workbench (database modeling and SQL development)
  - **ETL**: Pentaho Data Integration (PDI)
  - **Business Intelligence/Data Visualization**: Tableau Desktop
  - **Self-Service of Data Lakes**: Dremio

### Steps

**Install Java**

  - Download Java JDK v8 from: http://www.oracle.com/technetwork/java/javase/downloads/index-jsp-138363.html (in our case: Java SE 8u202).
  - Install and follow the instructions
  - [Optional] Instead of using Oracle Java JDK, you can use
    - [OpenJDK](https://openjdk.java.net/). Only use one JDK version.
    - [Amazon Correto](https://aws.amazon.com/tw/corretto/). In particular [version 8](https://docs.aws.amazon.com/corretto/latest/corretto-8-ug/downloads-list.html). Consider the right installer for your OS. This is a long-term support production-ready distribution of the Open Java Development Kit (OpenJDK) supported by Amazon. 

**Install MySQL**

  - Download the right version of MySQL and MySQL Workbench for your OS (in our case: MySQL Community Server 8.0.15 and MySQL Workbench 8.0.15). Download the program(s): 
    - [Mac] In this case: MySQL (http://dev.mysql.com/downloads/mysql/) and MySQL Workbench (http://dev.mysql.com/downloads/workbench/). You must download the DMG file.
    - [Windows] In this case download the MSI installer (bigger size, 64bits) from http://dev.mysql.com/downloads/mysql/ . This installer includes MySQL Workbench. Choose custom installation and only install the server and the workbench. Workbench in windows may require [Microsoft .NET Framework 4.5](https://www.microsoft.com/en-us/download/details.aspx?id=30653) and [Visual C++ Redistributable for Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145), but if you choose custom installation as stated in the previous step it won't be required. 
    - These versions will work in MAC OSX and Windows (latest OS versions). In case you have a previous OS version then it may be required to use an older version from [here](https://downloads.mysql.com/archives/installer/).
  - Install all the programs and follow the instructions:
    - [Windows] During the installation process you will configure the password for root user (choose IEMBD2018 or a password that you will remember). Consider a custom installation and choose just the MySQL Server and MySQL Workbench as components to be installed. If you forget the password you will be able to change it using the workbench.
    - [Mac] During the installation process you will configure the password for root user (choose iembd2018 or a password that you will remember). If you forget the password you will be able to change it from system preferences.
    - PDI and Tableau only support **legacy password encription**, not the new strong encription available in MySQL 8. Select this option until the strong encription is supported.

> Note: for Microsoft Windows it is just one installer for MAC, two files.

Remember to start the server to be able to use the database. Open MySQL Workbench and create a new connection using the right user and password and the standard parameters for configuration.

**Install PDI**

We will use the community version of Pentaho Data Integration (a.k.a PDI). It can be downloaded from this [link](https://sourceforge.net/projects/pentaho/files/Pentaho%208.2/client-tools/) (in our case: pdi-ce-8.2.0.0-324.zip).

  - Download the file and unzip.
    - [Mac] Move the data-integration folder into Applications folder
    - [Windows] Move the data-integration folder into C:/ folder
  - Open PDI
    - [Windows] Double-click spoon.bat inside data-integration folder
    - [Mac] Open the terminal and execute:
    
```
cd /Applications/data-integration/
./spoon.sh
```    
  - [Optional] Activate data-integration.app as a double-click app using the terminal:
  
``` 
sudo xattr -dr com.apple.quarantine /Applications/data-integration/Data\ Integration.app
```  

  - Configuring a JDBC Connection to MySQL 8.x Using PDI:
    - Download the MySQL 8.x JDBC driver (platform independent, zip) to the computer running Pentaho from: https://dev.mysql.com/downloads/connector/j/
    - Unzip the file mysql-connector-java-8.0.15.zip
    - Copy mysql-connector-java-8.0.15.jar to the Pentaho lib folder. [Windows]: C:\data-integration\lib. [Mac OS]: …/Applications/data-integration/lib
    - Configure a Generic Database connection in Pentaho: (1) Connection URL: **jdbc:mysql://localhost:3306/<database_name>** (at the beggining the only database we have is sys) (2) Driver Class Name: **com.mysql.cj.jdbc.Driver** (3) use the previous user and password
    - In case the server time zone value 'AEST' (or other) is unrecognized or represents more than one time zone, then consider: jdbc:mysql://localhost:3306/<database_name>?useLegacyDatetimeCode=false&serverTimezone=UTC
  - [Not required, only if you use MySQL 5.x] Install MySQL 5.x plugin for PDI:
    - Open PDI
    - Go the tools menu > Marketplace > MySQL Plugin and install
    - Restart PDI

**Install Tableau Desktop**

We can access student licenses due to the Academic Partnership. Tableau has versions for Mac and Windows. Follow these instructions:

  - Download the latest version of Tableau Desktop [here](https://www.tableau.com/academic).
  - Copy Tableau Desktop License from campus.
  - Install the software following the instructions in the screen.
  - Update your license in the application: Help menu -> Manage Product Keys
  - Download the driver for MySQL from [here](https://www.tableau.com/support/drivers)

**Install Dremio**

We will use the community version of Dremio Server. It can be downloaded from this [link](https://www.dremio.com/download/). Dremio server requires Java to work. Then:

  - Install Dremio using the installer.
  - Start Dremio:
      - [Windows]: Start from the Start Menu.
      - [Mac]: Launch Dremio from Applications. Start Dremio from the Start Menu.
  - You can now navigate to the Dremio UI at http://localhost:9047.
  - Download and install Dremio ODBC for your OS from https://docs.dremio.com/drivers/

**(Optional) Atom**

In case you need a multipurpose text editor, I recommend [Atom](https://atom.io).

## FAQ

### Is there a Pentaho Release Product Version Matrix?

Yes! You can find it [here](https://wiki.pentaho.com/display/PEOpen/Pentaho+Release+Product+Version+Matrix+8.x).

### Any recommendation for MySQL SQL syntax?

Yes, check [MySQL™ Notes for Professionals book](http://books.goalkicker.com/MySQLBook/) and [MySQL Documentation](https://dev.mysql.com/doc/).

### How can I have this repository?

Fork it using [github](https://www.github.com) and [github desktop](https://www.desktop.github.com). Are you interested in how Github works? Start [here](https://guides.github.com/activities/hello-world/). Steps:

  - [Sign up](https://github.com/join) for a free GitHub account
  - Then follow this guide to [fork your own copy](https://guides.github.com/activities/forking/) of the course repository
  - [Clone a copy of your forked repository](https://help.github.com/articles/cloning-a-repository/)

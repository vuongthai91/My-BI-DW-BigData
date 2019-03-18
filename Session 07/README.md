# Business Intelligence and Data Warehouse Course

## Session 7

The topic of this session is **Data Integration** (in particular, ETL). This repository includes the content discussed in class.

  - articles
  - Datasets
  - Videos

## Main Concepts

  - What is data integration
  - What is ETL
  - ETL subsystems

## How to use this content

  - Watch the videos
  - Download the folder
  - If you want to reproduce download the dataset (customer_data.csv) and install the programs
  - Required Software:
    - JDK v8
    - Pentaho Data Integration (latest version)
  
## What you can learn in the videos

  - [PDI - Our First ETL](https://vimeo.com/234685308)

## FAQ

### Why is PDI not working?

Many reasons:

 - Your computer has JRE not JDK.
 - Your computer has JDK v9/10/11 not v8.
 - Your computer has several java virtual machines (7, 8, 9, 10 and/or 11).
 - PDI is not in the right folder.
 - PDI has not been extracted from the zip file. Or the extraction process is corrupted (this is quite common in [Windows]).
 
### How to solve the problem

[Windows] Unzip PDI one more time.

Move PDI to the right location:

  - [Mac]: In the applications folder
  - [Windows]: In C:/

We must uninstall all JRE, JDK from our system and install the right JDK version.

[Windows]

  - Go to control panel > Uninstall programs. Delete all JRE and JDK not required. You have more information [here](https://java.com/en/download/help/uninstall_java.xml)
  - Download Java SE Development Kit 8u202 from [Oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
  - Install JAVA following the steps of the installer.
  - Set Environment Variables:
    - Open Control Panel. Open User Accounts applet. On the left-hand side of that applet you will see a link that says Change my environment variables. Click that link, and it will take you to the same “Environment Variables” dialog for your user's environment variables.
    - Set the PENTAHO_JAVA_HOME  environment variable. If you do not set these variables, Pentaho will not start correctly. If you are using a JRE, set the JRE_HOME home environment variable as well.
    - Set the path of the PENTAHO_JAVA_HOME variable to the path of your Java installation, like in the following example: SET PENTAHO_JAVA_HOME=C:\Program Files\Java\jdk8
   - Open PDI and verify the variables have been properly set.

[Mac]

  - Uninstall Java. Open the terminal and execute:

``` 
sudo rm -fr /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin
sudo rm -fr /Library/PreferencePanes/JavaControlPanel.prefpane
sudo rm -fr ~/Library/Application\ Support/Java
sudo rm -fr ~/Library/Application\ Support/Oracle/Java
cd /Library/Java/JavaVirtualMachines
sudo rm -rf jdk*
``` 

  - Download Java SE Development Kit 8u202 from [Oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
  - Install JAVA following the steps of the installer.

[Windows] If PDI is able to find java but it is still refusing to open, then open CMD prompt inside the data integration folder and execute the following instruction:

``` 
java -jar launcher\launcher.jar -lib ..\libswt\win64
``` 

### What can I do to increase the memory limit for PDI?

Follow the instructions in this [article](https://help.pentaho.com/Documentation/8.2/Setup/Configuration/Design_Tools_and_Utilities/Memory_Limit) to increase the memory limit in spoon.bat or spoon.sh.

### Are there other open source data integration options?

Yes, many and the amount is growing. Some of them:

 - [Apache Camel](https://camel.apache.org): an open source Java integration framework that enables integration of different applications using multiple protocols and technologies. It is a rule-based routing and mediation engine.
 - [Apache Kafka](https://kafka.apache.org): an open source platform written in Scala and Java. It provides a unified, high-throughput, low-latency platform for managing real-time data.
 - [Heka](http://hekad.readthedocs.io): an open source software system for high performance data gathering, analysis, monitoring and reporting. Its main component is a daemon program known as ‘hekad’ that enables the functionality of gathering, converting, evaluating, processing and delivering data.
 - [Logstash](https://www.elastic.co/products/logstash): an open source data processing pipeline that ingests data from multiple sources simultaneously, transforming the source data and store events into ElasticSearch by default. Logstash is part of an ELK stack.
 - [Pentaho Data Integration](https://sourceforge.net/projects/pentaho/files/): an open source java ETL tool that supports multiple data integration steps. 
 - [Talend Open Studio](https://www.talend.com/products/talend-open-studio/): products provide tools to integrate, cleanse, mask and profile data. Talend has a GUI that enables managing a large number of source systems using standard connectors.
 - [Singer](https://www.singer.io): is an open-source standard for writing scripts that move data.
 - [Luigi from Spotify](https://github.com/spotify/luigi): a Python module that helps you build complex pipelines of batch jobs.
 - [embulk](http://www.embulk.org/docs/): a open-source bulk data loader that helps data transfer between various databases, storages, file formats, and cloud services.
 
And many more proprietary options: [Informatica](https://www.informatica.com), [Fivetran](https://fivetran.com), [Improvado](http://improvado.io), [Flydata](https://www.flydata.com), [Alooma](https://www.alooma.com), [Blendo](https://www.blendo.co) [Segment](https://segment.com), [etleap](https://etleap.com), [CloverETL](http://www.cloveretl.com), [Data Duck ETL](http://dataducketl.com), [Celigo Integrator](https://www.celigo.com/ipaas-integration-platform/) or [Matillion](https://www.matillion.com), [ICEDQ](https://icedq.com), [Melt](http://www.jumpmind.com/products/metl/overview) among many others. 

### I don't want to use a GUI for ETL. Any options?

Yes. Check the following links: [1](https://github.com/pawl/awesome-etl) and [2](https://github.com/pditommaso/awesome-pipeline).

## References

  - [Hitachi Ventara Pentaho - Documentation](https://help.pentaho.com/Documentation/)
  - [Hitachi Ventara Pentaho - Documentation PDI](https://help.pentaho.com/Documentation/8.2/Products/Data_Integration)
  - [Pentaho Github](https://github.com/pentaho)
  - [PDI - Transformation Steps](https://help.pentaho.com/Documentation/8.0/Products/Data_Integration/Transformation_Step_Reference)
  - [PDI - Job Steps](https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Job_Entry_Reference)
  - [PDI - Market Place](https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Marketplace)
  - [Hitachi Ventara Pentaho - Community](https://community.hds.com/community/products-and-solutions/pentaho/)
  - [Hitachi Ventara Pentaho - Wiki](https://wiki.pentaho.com)
  - [Hitachi Ventara Pentaho - Wiki - PDI](https://wiki.pentaho.com/display/EAI/Latest+Pentaho+Data+Integration+(aka+Kettle)+Documentation)
  - [Examples from Learning Pentaho Data Integration 8 CE Third Edition](https://github.com/PacktPublishing/Learning-Pentaho-Data-Integration-8-CE-Third-Edition)

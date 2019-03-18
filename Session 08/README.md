# Business Intelligence and Data Warehouse Course

## Session 8

The topic of this session is **Data Integration** (in particular, ETL). This repository includes the content discussed in class.

  - ETL processes
  - Videos
  - Data Sets

## Main Concepts

  - ETL subsystems
  - ETL design and implementation

## How to use this content

  - Download the folders
  - Required Software:
	  - MySQL
	  - Pentaho Data Integration
	  - Java JDK
  - All ETL processes have been created with Pentaho Data Integration.
  - Transformation TR8-P1 and TRA8-P2 require MySQL.
  
## FAQ

### Does PDI support user input?

Yes. It supports arguments, parameters and variables. You can read about it [here](https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Data_Integration_Perspective/Run_Modifiers).

### How can we create an ETL environment independent?

Using variable in the path such as

``` 
${Internal.Entry.Current.Directory}
``` 

PDI supports other variables. Check this [link](https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Data_Integration_Perspective/Run_Modifiers/Variables) to discover all of them.

### How can we schedule an ETL process using PDI?

You can use [carte server](https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Carte_Clusters) (one of the components of PDI) and [cron](https://en.wikipedia.org/wiki/Cron) or an external tool such as [Azkaban](https://azkaban.github.io/) that combines both tools.

### How can I discover all the steps supported by PDI?

Check the following links:

- https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Transformation_Step_Reference
- https://help.pentaho.com/Documentation/8.2/Products/Data_Integration/Job_Entry_Reference

### Key criteria for selecting ETL tools

When selecting an ETL tool, it is recommended to consider, at least, the following criteria: 

 - Infrastructure
 - Functionality
 - Performance
 - Native connectivity
 - Usability
 - Platforms supported
 - Debugging facilities
 - Data Quality & profiling
 - Reusability
 - Scalability
 - Batch vs Real-time
 - Future prospects

# Lab 14: Essbase Feature Functionalities

## Introduction

This lab walks you through the major features of Essbase-19c and their functionalities across the platform along with Overview of the Essbase-19c Web-UI on a whole.

## Objectives

*	Understand the Essbase 19c Plugins. [ Smartview and Cube designer ]
*	Learn how to use the major aspects of plugins effectively.
*	Learn the Essbase 19c Web-UI overview.
*	Learn how to build rules/calculations and run corresponding jobs.
*	Learn the MIGRATION process between Cloud environments.
*	Understand the Essbase REST API functionality.

## Required Artifacts

*	The following lab requires an Oracle Public Cloud account - Essbase 19c Instance with Service Administrator role .
*	Windows Operating System is preferred for proper working of Essbase Plugins
*	The estimated time to complete this lab is 30 minutes. 

`NOTE: Whenever there is a “Name” being assigned to any Resource / Application / Cube or to any database in this lab please follow the naming convention as “Sample_<FIRST_NAME>” to avoid duplication.`

## Part 1 - Creating a Sample App in Essbase19c

1.	Login to the Essbase 19c UI using the corresponding Essbase endpoints. i.e. https://ip/essbase/jet

2.	Now in the Applications tab click on “Import” option from the UI as shown below.

3.	 From the pop-up window that’s displayed click on the “Catalog” as below.

4.	Now as mentioned in the path below , please select “Sample_Basic.xlsx” file. [ from Catalog -> All Files -> Gallery Templates ]

5.	Let us give the name of the Application as “DynamicCorp” and Cube i.e. Database name as “Sales” as below and then click OK.

6.	Now we can see an application is deployed and its status. 

This concludes the creation of sample app from the “Catalog” in the Essabase 19c UI.

## Part 2 - Analyzing Essbase data using Smart View Plugin

In this lab, we will be doing the following - 

*	Connecting to Data Sources
*	Describe Smart View user interface
*	Create ad hoc grids

**Section 1 - Connecting to Data Sources**
After installing Oracle Smart View for Office, you can create connections to Essbase in cloud. Connections require information about the server and port. Your cloud service administrator should provide you with the information you need to create the connection. Use the quick connection method to create a private connection to 
the cloud service.

To create a private connection using the quick connection method:

1. In Excel, select the Smart View ribbon, and then click Panel.

2. On the Smart View Panel, click the arrow on the Switch to button, and then select Private Connections from the list.

3. In the text box that opens, enter the URL for the data source to which you want to connect. The URL syntax: `https://ip/essbase/smartview`

4. Click Go, or press Enter. (You will receive alert for certificate error. This is expected behavior as for the purpose of this tutorial we are using Essbase 19c deployment with demo certificate. Once in post deployment / production instance we replace demo certificate with paid SSL certificate we will not get this alert. For instance, click yes on alert to continue with lab exercise.)

5. On the login window, enter your login credentials. After successful login, you can now begin working with data in Oracle Analytics Cloud - Essbase. 

6. Expand ‘EssbaseCluster’, navigate to ‘DynamicCorp’ application. Double click on ‘Sales’ database.

You will be presented with option to create Ad hoc grid. Click on Ad hoc analysis.

**Section 2 - Describe Smart View user interface**

**Smart View Ribbon**
The Smart View ribbon option enables you to set Smart View options and perform commands that are common for all data source providers.

**Essbase Ribbon**
The Essbase ribbon contains commands that enable you to view, navigate, and analyze Essbase data.

**POV Toolbar**
Dimensions that are not displayed in columns or rows of a data grid are displayed on POV toolbar, which identifies a slice of the database for a grid. For default ad hoc grids, all database dimensions are displayed on the POV toolbar at the dimension level

**Smart View Panel** 
You use Smart View panel to connect to your smart view data sources and manage connections.

**Section 3 - Create ad hoc grids**
1. Bring up Excel. Click Smart View – Panel – Private Connections. Enter the provided Smart View URL. Supply the credentials.
2. In the Connection Manager panel to your right, click ‘DynamicCorp’ – ‘Sales’. Click Connect. Click Ad hoc Analysis. 
3. After connecting to an Essbase server and opening a worksheet, you can initiate ad hoc reports against databases on the connected server. A report initiated at the database level on an empty worksheet returns data from the top levels of each database dimension.
4. Double click or zoom in to Measures and Year. You will now see the measures broken down by Quarters.
5. Go to Year. Click on Zoom In – All levels. You will now see the numbers broken down to leaf level Months. ‘Zoom in’ drills down to display details. To zoom in on a member, perform one of the following actions:

        a. Select the member and then, on the Essbase ribbon, click Zoom In.
        b. Double-click the member.

6. Double Click (or Click Zoom in): Measures – Profit – Margins – Sales. Go to Sales. Click Keep Only. Now you are analyzing only Sales numbers and you have removed the rest from your sheet. 
7. In the Smart View ribbon click Undo. Undo reverses the last change you made to the data. 
8. In the Smart View ribbon click ‘Redo’. It will take you back to the sheet prior to the ‘Undo’. 
9. Pivot to POV: 

        a. Click on ‘POV’ in ‘Essbase’ ribbon. 
        b. Click on down arrow next to Market. Select New York. 
        c. You can now select New York in the POV toolbar, click Refresh to see the figures refreshed in the sheet for New York. 

10. Member Selection: 

        a. Drag Scenario from POV tool bar to the sheet. 
        b. Click on Scenario
        c. Click on Member Selection in the Essbase ribbon. Select Actual.
        
11. Free Form processing: 

        a. You can free form type a member combination on a sheet. Click Refresh. The sheet will be updated to show the results of the query in your free form sheet. 
        b. Start with creating smart view analysis report.
        c. Create report by zooming into Year & Measures dimension.

12. You can directly enter Sales account member in place of Profit to visualize sales data across year without needing to perform member selection.

13. Click on Profit cell and replace with Sales, hit refresh.


## Part 3 - Install the Smart View Cube Designer Extension
## Part 4 - About the Cube Designer Ribbon
## Part 5 - Creating a Cube from Tabular Data in Cube Designer 
## Part 6 - Updating Cubes Incrementally in Cube Designer
## Part 7 - Overview of the WEB-UI
## Part 8 - Data Load to Cube
## Part 9 - Calculating Essbase Cube
## Part 10 - Migration Utilities
## Part 11 - REST APIs

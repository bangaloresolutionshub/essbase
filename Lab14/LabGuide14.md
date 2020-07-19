# Lab 14: Essbase Feature Functionalities

## Introduction

This lab walks you through the major features of Essbase-19c and their functionalities across the platform along with Overview of the Essbase 19c Web UI on the whole.

## Objectives

*	Understand the Essbase 19c Plugins. (Smartview and Cube designer)
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
*       Audit Trail

### Section 1 - Connecting to Data Sources 

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

### Section 2 - Describe Smart View user interface

**Smart View Ribbon**
The Smart View ribbon option enables you to set Smart View options and perform commands that are common for all data source providers.

**Essbase Ribbon**
The Essbase ribbon contains commands that enable you to view, navigate, and analyze Essbase data.

**POV Toolbar**
Dimensions that are not displayed in columns or rows of a data grid are displayed on POV toolbar, which identifies a slice of the database for a grid. For default ad hoc grids, all database dimensions are displayed on the POV toolbar at the dimension level

**Smart View Panel** 
You use Smart View panel to connect to your smart view data sources and manage connections.

### Section 3 - Create ad hoc grids
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

### Secrtion 4 - Audit Trail

**Step 1 - Enable Audit trail:**

Data is updated in Essbase by Submitting data, adding/changing LRO (Linked Reporting Objects) and Data load. Essbase has the capability to let certain users go back and view the Audit Trail of the changes that were made to the data. 

Users who have one of the following roles on the application can view the processed audit records for the cubes in that application: Application Manager, Database manager, Database Update role. Only those records where the user name requesting the audit trail matches the user name registered in the audit records, will be returned. 

1. The Service Administrator and Power User have the permissions to enable Audit Trail in the Essbase Application. 
2. Log in to Essbase UI. Click on Application DynamicCorp. Click on hamburger icon. Click on inspect.
3. Click on configuration.
4. Click on Add + to your right.
5. Click + to select ‘AUDITTRAIL’ property.  Enter ‘DATA’ in value field. Click ‘Apply and Restart’ to restart application. 

**Step 2 - Submit Data and Audit Trail**

1. Log in to Smart View and connect to application DynamicCorp/Sales. Click on Connect. Click on Ad hoc Analysis. 
2. Click on Year. Click on Zoom In – All levels. 
3. Change data for Jan. Click ‘Smart View’ – ‘Submit Data’
4. Click ‘More’ under ‘Ad hoc Analysis’. Click on ‘Audit Trail’.
5. Notice an Audit Trail table that contains records of changes made to the cube. The record contains Timestamp, New Value, Data cell POV where change was made. 

Below the table, notice a detailed description of the change in the Audit record. 

**Step 3 - Linked Reporting Objects and Audit Trail**

1.	Click on cell cell B3. Click ‘Essbase’ – ‘Linked Objects’. Click drop down next to ‘Attach’. Click ‘Cell Note’. Add a cell note "Figures are too high".
2.	Click on cell B7. Click ‘Essbase’ – ‘Linked Objects’. Click drop down next to ‘Attach’. Click ‘File’. Browse and attach a file. Enter a file description. 
3.	Click on cell B11. ‘Essbase’ – ‘Linked Objects’. Click drop down next to ‘Attach’. Click ‘URL’. Enter URL http://cnn.com and enter "Breaking news!". Make a few more such updates. 
4.	Click ‘Audit Trail’ menu. You will see the table populated with all the changes you made. Each record in the audit trail represents one of two changes - change to data (New Value) or change to LRO (LRO)

**Step 4 - Audit Trail Table**

1.	There are three icons at the bottom of the audit table: "Export logs to sheet", "Refresh audit log list", "Adhoc for selected POV. The columns in the Audit trail table can be sorted by clicking the arrow at the heading. 
2.	Audit records can be exported to an excel file by clicking on icon at the bottom of Audit table called "Export logs to sheet". 
3.	When you click on an audit record, you can see the description of the audit record change in the description section at the bottom of the table.
4.	Then, if you want to do further analysis on the POV for this record, select the icon at the bottom of the Audit table titled "Adhoc for selected POV", it will land you on a sheet called "Audit_adhoc", with the POV and refreshed data value. This is the starting point and it is a live sheet where you can start doing analysis and rest of Smart View operations.  
5.	This is a shared sheet for landing from Audit record. When you click on subsequent audit records, and click on Adhoc for selected POV, it will land you in this same sheet.

## Part 3 - Install the Smart View Cube Designer Extension

Before you perform this procedure, you must complete the steps in Create Data Source Connections to Essbase. 

### Step 1 - Installing Cube Designer from Smart View

1. On the ‘Smart View’ ribbon, select ‘Options’, and then ‘Extensions’. 
2. Click the ‘Check for updates’ link. Smart View checks for all extensions that your administrator has made available to you. 
3. Locate the extension named Oracle ‘Cube Designer’ and click ‘Install’ to start the installer. 
4. Follow the prompts to install the extension.

### Step 2 - Installing Cube Designer from Essbase

1. In Essbase19c UI , click ‘Console’.
2. On the ‘Desktop Tools’ tab, to the right of Cube Designer Extension, click ‘Download’. 
3. In the ‘CubeDesignerInstaller.svext’ dialog box, select ‘Save File’ and click ‘OK’. Save the file to a local directory.
4. Close all Microsoft Office applications and make sure Microsoft Office applications are not running in the background.
5. Double click the ‘CubeDesignerInstaller.svext’ file we downloaded to local directory.
6. Restart Microsoft Office applications.

### Step 3 - Update the Smart View Cube Designer Extension

If an extension is available for you to update, you can update it from Smart View Excel, on the Extensions tab of the Options dialog box. To check for Cube Designer Smart View extension updates and install them: 

1. From the ‘Smart View’ ribbon, select ‘Options’ and then ‘Extensions’.

2. Click the ‘Check for Updates, New Installs, and Uninstalls’ link to check for updates.

You are prompted to log in after you click on existing Essbase server URL’s.

If an update is available, the ‘Update Available’ icon is displayed in the Cube Designer row. 

*Note:*
This process uses a server locations list, which was created by previous Smart View connections . If there are connection definitions that are no longer valid, you receive errors when the process tries to connect to those servers. See (Delete Smart View Connection URLs)[https://docs.oracle.com/en/cloud/paas/analytics-cloud/essug/delete-smart-view-connection-urls.html]. 

3.	Click Remove to uninstall the extension.
4.	Close Excel.
5.	Restart Excel.
6.	From the ‘Smart View’ ribbon, select ‘Options’ and then ‘Extensions’.
7.	Click ‘Check for Updates, New Installs, and Uninstalls’. Once again, when you select the Essbase URL, you are prompted to log in.
8.	In the Cube Designer row, click Install.
9.	Close Excel.
10.	Open Excel.
11.	Ensure that the Cube Designer ribbon is displayed in Excel. 

## Part 4 - About the Cube Designer Ribbon

Cube Designer helps you to design, create and modify application workbooks to meet their strict layout and syntax requirements. You can also use options on the Cube Designer ribbon to perform a number of cube management tasks, such as loading data, editing formulas and viewing jobs.

### Cube Designer Ribbon Options

**Connections:** Opens the ‘Connections’ dialog box, in which you choose the cloud service URL. 

**Essbase/Catalog:** Opens the Essbase Files dialog box, which contains a selection of prebuilt application workbooks, from which you can build sample applications and cubes. 

Also, a catalog toolbar is available in this dialog box from which you can perform many file operations within the catalog, such as upload, download, cut, copy, paste, delete, rename, and create a new folder.

**Local:** Provides a drop-down menu with options to open or save an application workbook locally, or to export a cube to an application workbook. 

**Designer Panel:** Opens the Designer Panel, a series of panels in which you can design and edit application workbooks. 

**Formula Editor:** Opens the Formula Editor, which provides an interface in which to develop member formulas, with assistance for developing correct syntax. 

**Hierarchy Viewer:** Opens the Dimension Hierarchy dialog box, in which you can view the hierarchy for the selected dimension worksheet in an application workbook, and perform tasks, such as renaming members and changing storage settings. See Work with Dimension Worksheets in Cube Designer. 

**Build Cube:** Opens the ‘Build Cube’ dialog box, where you can build a cube from the active application workbook. In this dialog box, cube designer automatically detects existing data and calculation worksheets, and then pre-selects options to load the data and run the worksheets. 

**Load Data:** Opens the Load Data dialog box, which contains options to clear all data and to load data. 

**Calculate:** Opens the Calculate Data dialog box, in which you can select an application, a cube, and a calculation script to execute. 

**Analyze:** Provides a drop-down menu with options to create a Smart View ad hoc grid, or connect application workbook query worksheets (Query.query_name worksheets) to Smart View. 

**View Jobs:** Opens the Job Viewer dialog box, in which you can monitor the status of jobs, such as data loads, calculations, imports, and exports. 

**Transform Data:** Opens the Transform Data dialog box, which lets you build a cube from tabular data. 

**Options:** Provides options to specify the default working folder and to activate the cube designer log. 

**Admin Tasks:** Opens a menu from which you can delete an application, delete a cube, or view logs. Selecting one of these options opens the ‘Delete Application’ or ‘Delete Cube’ dialog box, or allows you to view server or application logs. 

**Server name:** Shows the currently defined connection location. When you click ‘Server name’ and log in (if prompted to do so), the server name and the client and server versions are displayed.

## Part 5 - Creating a Cube from Tabular Data in Cube Designer 
## Part 6 - Updating Cubes Incrementally in Cube Designer
## Part 7 - Overview of the WEB-UI
## Part 8 - Data Load to Cube
## Part 9 - Calculating Essbase Cube
## Part 10 - Migration Utilities
## Part 11 - REST APIs

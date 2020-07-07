** Install the Smart View Cube Designer Extension

Before you perform this procedure, you must complete the steps in Create Data Source Connections to Essbase. 

*** Installing Cube Designer from Smart View

1.	On the ‘Smart View’ ribbon, select ‘Options’, and then ‘Extensions’. 
1.png

2.	Click the ‘Check for updates’ link. 
Smart View checks for all extensions that your administrator has made available to you. 
         2.png
3.	Locate the extension named Oracle ‘Cube Designer’ and click ‘Install’ to start the installer. 

4.	Follow the prompts to install the extension.


*** Installing Cube Designer from Essbase
1.	In Essbase19c UI , click ‘Console’.

2.	On the ‘Desktop Tools’ tab, to the right of Cube Designer Extension, click ‘Download’ . 

  3.png
  
3.	In the ‘CubeDesignerInstaller.svext’ dialog box, select ‘Save File’ and click ‘OK’. 

Save the file to a local directory.

4.png

4.	Close all Microsoft Office applications and make sure Microsoft Office applications are not running in the background.

5.	Double click the ‘CubeDesignerInstaller.svext’ file we downloaded to local directory.

6.	Restart Microsoft Office applications.

*** Update the Smart View Cube Designer Extension

If an extension is available for you to update, you can update it from Smart View Excel, on the Extensions tab of the Options dialog box. 
To check for Cube Designer Smart View extension updates and install them: 

1.	From the ‘Smart View’ ribbon, select ‘Options’ and then ‘Extensions’.

1.png

2.	Click the ‘Check for Updates, New Installs, and Uninstalls’ link to check for updates.

2.png

You are prompted to log in after you click on existing Essbase server URL’s.
If an update is available, the ‘Update Available’ icon is displayed in the Cube Designer row. 
Note:
This process uses a server locations list, which was created by previous Smart View connections . If there are connection definitions that are no longer valid, you receive errors when the process tries to connect to those servers. See Delete Smart View Connection URLs. 

5.png

3.	Click Remove to uninstall the extension.

4.	Close Excel.

5.	Restart Excel.

6.	From the ‘Smart View’ ribbon, select ‘Options’ and then ‘Extensions’.

7.	Click ‘Check for Updates, New Installs, and Uninstalls’.
Once again, when you select the Essbase URL, you are prompted to log in.

8.	In the Cube Designer row, click Install.

9.	Close Excel.

10.	Open Excel.

11.	Ensure that the Cube Designer ribbon is displayed in Excel. 

6.png

** About the Cube Designer Ribbon

Cube Designer helps you to design, create and modify application workbooks to meet their strict layout and syntax requirements. You can also use options on the Cube Designer ribbon to perform a number of cube management tasks, such as loading data, editing formulas and viewing jobs.

6.png

*** Cube Designer Ribbon Options

*	Connections: Opens the ‘Connections’ dialog box, in which you choose the cloud service URL. 
*	Essbase/Catalog : Opens the Essbase Files dialog box, which contains a selection of prebuilt application workbooks, from which you can build sample applications and cubes. 
Also, a catalog toolbar is available in this dialog box from which you can perform many file operations within the catalog, such as upload, download, cut, copy, paste, delete, rename, and create a new folder.
*	Local: Provides a drop-down menu with options to open or save an application workbook locally, or to export a cube to an application workbook. 
*	Designer Panel: Opens the Designer Panel, a series of panels in which you can design and edit application workbooks. 
*	Formula Editor: Opens the Formula Editor, which provides an interface in which to develop member formulas, with assistance for developing correct syntax. 
*	Hierarchy Viewer: Opens the Dimension Hierarchy dialog box, in which you can view the hierarchy for the selected dimension worksheet in an application workbook, and perform tasks, such as renaming members and changing storage settings. See Work with Dimension Worksheets in Cube Designer. 
*	Build Cube: Opens the ‘Build Cube’ dialog box, where you can build a cube from the active application workbook. In this dialog box, cube designer automatically detects existing data and calculation worksheets, and then pre-selects options to load the data and run the worksheets. 
*	Load Data: Opens the Load Data dialog box, which contains options to clear all data and to load data. 
*	Calculate: Opens the Calculate Data dialog box, in which you can select an application, a cube, and a calculation script to execute. 
*	Analyze: Provides a drop-down menu with options to create a Smart View ad hoc grid, or connect application workbook query worksheets (Query.query_name worksheets) to Smart View. 
*	View Jobs: Opens the Job Viewer dialog box, in which you can monitor the status of jobs, such as data loads, calculations, imports, and exports. 
*	Transform Data: Opens the Transform Data dialog box, which lets you build a cube from tabular data. 
*	Options: Provides options to specify the default working folder and to activate the cube designer log. 
*	Admin Tasks: Opens a menu from which you can delete an application, delete a cube, or view logs. Selecting one of these options opens the ‘Delete Application’ or ‘Delete Cube’ dialog box, or allows you to view server or application logs. 
*	Server name: Shows the currently defined connection location. When you click ‘Server name’ and log in (if prompted to do so), the server name and the client and server versions are displayed. 

** Creating a Cube from Tabular Data in Cube Designer 

This workflow uses two sample tabular data Excel files to demonstrate the concepts of intrinsic and forced-designation headers. See About Using Tabular Data to Create Cubes. 

1.	In Excel, on the ‘Cube Designer’ ribbon, click ‘Catalog’.
2.	On the Cloud Files dialog box, under Catalog, go to ‘gallery/Technical/Table Format’ as shown below, then select a sample tabular data file:
o	Unstr_Hints.xlsx: Intrinsic headers 
7.png
3.	Double click on the above directed file.
4.	On the ‘Cube Designer’ ribbon, select ‘Transform Data’  .
5.	On the ‘Transform Data’ dialog box, enter an application and cube name, if you want to change the default names that are prepopulated. 
8.png
The application name is based on the source file name without the extension and the cube name is based on the worksheet name.
o	Unstr_Hints.xlsx: Application name is Unstr_Hints and the cube name is SpendHistory.
6.	Press ‘Preview Data’. The workbook is sent to Essbase19c for analysis and the relationships are returned for viewing. 
7.	When you are ready to create the cube, click ‘Run’.
8.	  (Optional) When asked if you want to see the cube job status, click ‘Yes’.
10.png
The newly created application and cube are listed on the Applications home page in the cloud service and are available in Cube Designer. Now that the cube has been created from the tabular data, you can export the cube to an application workbook. 
9.	On the ‘Cube Designer’ ribbon, select ‘Private / Local’  , then select ‘Export Cube to Application Workbook’.
11.png
10.	On the ‘Export Cube to Application Workbook’ dialog box, select the application and cube, and then select ‘Run’ 
12.png

To create a cube in the cloud service, see Creating a Cube from Tabular Data. 

With this, we saw how a normal flat file excel sheet is converted into an Essbase Application and a Cube. We could get the DBX[Design by Example] file in a matter of seconds with the dynamic capabilities of Essbase powered by Cube Designer plugin.

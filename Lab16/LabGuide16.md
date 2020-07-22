
# Lab 13: Scenario Management

Using scenario management, scenario participants can perform what-if analysis to model data in their own private work areas. These scenarios can optionally be subject to an approval workflow which includes a scenario owner and one or more approvers. In the workflow, scenario owners merge scenario data with the final cube data only after it is approved.

## Topics: 

•	Scenario Management Overview
•	Creating a cube with Sandboxes	
•	Creating a Scenario	
•	Lightweight Sandboxes		
•	Changing Sandbox Data	
•	Scenario Workflow
 
## Overview – Understand Scenario

The exercises contained within this lesson will allow the user to get acquainted with different aspects of Scenario Management.  The different aspects include the lightweight nature of sandboxes on the cube; the process involved with initiating Scenario Management and adding sandboxes; as well as, the workflow supported by Scenario Management.  
Scenarios are private work areas in which users can model different assumptions within the data and see the effect on aggregated results, without affecting the existing data.
Each scenario is a virtual slice of a cube in which one or more users can model data and then commit or discard the changes.

## Exercise 1-1	Sandbox Data

In the following exercises, the lightweight nature of a sandbox will be on display.  In this exercise we are going to learn about the sandbox dimension that is created when sandboxing is enabled in an application.

## Exercise 1-2	Create a Scenario-Enabled Sample cube

You can create a scenario-enabled cube by importing the scenario-enabled sample application workbook.

1.	In the Essbase web interface, click Import.
 

2.	Click Catalog.
 

3.	Drill down into the Gallery, Cubes, and General folders.
Naviagte to All Files > gallery > Applications > Demo Samples > Block Storage


 
4.	Select Sample_Basic_Scenario.xlsx and click Select.
5.	Provide a unique name and click OK.

 

 
## Exercise 1-4	Creating a Scenario

Adding a Scenario to a Sandbox enabled cube
To create a scenario, you specify general information about your scenario, including creating a scenario name, selecting a due date, selecting an application and cube, and choosing whether to use calculated values. Then you add users and define whether each user is a participant or an approver.
1.	In Essbase, login as a user with database update (or higher) permission to at least one application.
2.	Click Scenarios.
3.	Click Create Scenario.

 

4.	On the General Information tab, enter a scenario name and select a Priority (optional), Due Date, Application, and Database (cube). You will only see applications for which you have minimum database update permission.

 
5.	Turn on Use Calculated Values if you want to merge calculated values to base values when running calculation scripts on scenarios.
6.	(Optional) Enter a description.
7.	On the Users tab, click Add   for a list of users.
8.	Add the users that you want.
9.	Close the Add Users dialog box.
10.	For each user, keep the default (Participant), or select Approver.
11.	Select Approver. 
Scenario user roles determine the workflow for the scenario.
 
12.	Save your change.
Exercise 1-4	Lightweight Sandboxes
Show that sandboxes are lightweight
In this exercise you will be introduced to the concept that creating sandboxes has little impact on resource usage such as disk space.
Connect to Sample_Scenario-Basic in smartview analysis.
 
Create a private connection to your environment, http://<MachineIP>/essbase/smartview Login with user.  If you are not already connected..
Refresh the data.

Questions: 
Do you see Data for the sandboxes (sb#)?
Is there a variance between any of the sb# members and Base?
If the loaded file contained no references to any sb# members how did the data get there?
Takeaway:  By default, all created Sandboxes will have the same values as the data loaded into the base.  The data in the sandbox is dynamically queried and will not use any extra storage disk space.  Only values that are modified as part of a scenario will be stored.  This makes creating and using most scenarios a very light weight operation. 

## Exercise 1-5	Model Data

As a scenario user, you can model data slices in your own scenario.
1.	In Essbase, click Scenario.
2.	On the Scenarios page, locate the scenario in which you want to model data.
3.	Launch Smart View by clicking the Excel   icon before the scenario name.
4.	Make data changes and perform your what-if analysis in Smart View.

 

Or you can make use of provided smartview analysis xls to perform what if analysis.

 
Open Scenario_Comparison file and create connection with Sample_Scenario – Basic.
Make changes to sandbox member sb0 Actual data and submit data.

 

You will notice updated data will reflect only against sb0 dimension intersection.

## Exercise 1-6	Scenario Workflow

Now we will use the Scenario workflow to submit and ultimately merge the scenario data with the base. In the real case, the scenario flow that we will simulate is:
•	Participant user is submitting the data for approval
•	Approver user can review the data and decides to approve
•	Once data is approved, Data can be applied to the Base by Participant.
Since you are doing it by yourself, you will need to play roles of both participant and approver. 
Let’s start:
1) 	Login to Essbase on cloud. (Consider yourself as Participant user). Navigate to scenarios.
2) 	Highlight the scenario created previously.
3) 	Select Actions->Submit, enter a comment if needed
 
Tip:  If you don’t have an Approver assigned for the scenario the Action Submit will not be available
4) 	Highlight the scenario created previously, select Actions->Approve, enter a comment if needed. (Consider yourself as an Approver).
 

5) 	Login to the Essbase cloud. (Consider yourself as Participant).
6) 	Highlight the scenario created previously.
7) 	Select Actions->Apply
 

8) 	Go to Smart View and retrieve data into the Comparison tab (make sure you have an active connection in the ‘Comparison’ tab to the same application you connected to while submitting the data)
 
You should see the changes have been applied to the Base.

## Understand Scenario User Roles and Workflow

You can review a scenario using an optional approval workflow.
Scenario user role assignments determine the workflow for scenarios. You must have at least one approver to enable the scenario workflow. Without an approver, participants do not have the option to submit the scenario for approval, for example, and there is no option to approve or reject the scenario.
The only action for scenarios without at least one approver is Apply. Without an approver, the scenario owner can still change data values in the scenario and apply data changes to the cube (or reject them), without going through an approval process.
Participants can participate in a what-if analysis. They must have Database Update or Database Access user role. Adding participants is not mandatory.
Approvers monitor the process, and approve or reject scenarios. They must have Database Access or higher role. Scenarios can have multiple approvers, in which case each one must approve the scenario before it can be submitted.
Participants and approvers with the Database Access user role cannot write to a scenario until they are granted write access through a filter.
Participants and approvers are not mandatory. The scenario owner can change data values in the scenario and commit data changes to the cube (or reject them) without designating participants or approvers.

 


---
title: Ask the Expert - Gauging quality and engagement
description: Learn to build reports that answer quality and engagement questions. This webinar was recorded on November 13, 2019.
activity: use
doc-type: feature video
team: Technical Marketing
kt: 9914
---
# Ask the Expert - Gauging quality and engagement

Learn to build reports that answer quality and engagement questions. This webinar was recorded on November 13, 2019.

>[!VIDEO](https://video.tv.adobe.com/v/341120/?quality=12)

## Q&A

**Question**

There are some fields that are available to filter by but are not available when you try to group by them. Are you working to make them consistent options?

**Answer**

The reporting tools will not allow you to group by a dynamic field or one that can have multiple chioces selected at once, like a checkbox field. You can only group on fields that have a single value, even though they might have many choices.

You can filter by checkboxes, and view them, you just can't group on them.

**Question**

In the iteration on job-roles example, can I show the primary one bold?

**Answer**

In the iteration we can identify the primary job role. We need to do this in a valueexpression, but HTML codes are not recognized in a valueexpression. So we need to come up with another way to identify the role as being the primary. I put "**" before and after the primary role name in this code. Give it a try and see how you like it:

```
displayname=All Job Roles 
listdelimiter=<p> 
listmethod=nested(userRoles).lists 
textmode=true
type=iterate 
valueexpression=IF({user}.{roleID}={role}.{ID},CONCAT("**",{role}.{name},"**"),{role}. {name})
valueformat=HTML
```

This will give you a list like this:

```
Support Engineer 
QA Engineer 
**Designer**
```

Where Designer is the primary role for this user.

**Question**

Hi! I'm putting together a workflow for our Editorial team that keeps track of where an article is in its lifecycle (initial writing --> department(s) reviews --> final edits --> publish). They want to easily see which Milestone or Task it is currently at. The feedback I'm getting is the standard Milestone view (with the red or green shading) is too "busy and complex." Is there a way to just show the "Project Name" and "Current Milestone" in a table or grid?

**Answer**

Yes. You can create a task report that will show the milestone tasks currently being worked on and what task it's associated with. You can do that in a table or in a list report.

**Question**

Can we have proof information combined with project information in a report?

**Answer**

If you have created a Proof Approval report, project information can be pulled into columns usitng text mode. For example, if you wanted to reference the project name in a column, you could use the following:

```
displayname=Project Name
textmode=true 
valuefield=documentVersion:document:project:name 
valueformat=HTML
```

**Question**

I would also like more info on reporting on proof data as it relates to the project. For example, a project report that includes proof decision and comments.

**Answer**

In order to reference project information and proof information in a single report, you will want to create a Proof Approval report. Currently, comments from a proof cannot be pulled into this report, however, each proof approver decision can be found on its own line item under the Approver Decision column.

**Question**

I use sharecol often in order to create single page status (many many columns). However, I find that if after i create a report I want to add a column at the top of the page it is very time consuming to go back and modify. Do you have any tips or tricks to make this type of change?

**Answer**

If you're talking about putting a column at the top of a text mode columns list, you're just going to need to renumber your columns manually.

But if you've already created the report with the first column being some shared columns and you want to put another shared column on the top of the list, this is easier.

In the Report editor just add a couple of new columns and drag them to the far left of your Columns (View) screen. after you do this take a look at what used to be the left column and you'll notice the text mode column numbers have all incremented. Drag as many blank columns over there as you need. Be sure and put something in those blank columns before you save it or else they will be stripped out.

**Question**

Hi - with regards to the final bug report - how can the reports be done for multiple projects - if bugs are coming in for multiple projects??

**Answer**

You can filter by portfolio or project, depending on how you've organized your work.

You can also filter on request queues. You might want to set up request queues for each project where you can create customer users as Reviewers that can login and submit tickets directly to the request queues you've shared with them.

**Question**

The first reports were based on projects/project name, can this be done on tasks also and if so whats the best way to group them, as possibly the task name would be different more often than not...thanks!

**Answer**

All these reports can be done as either task, issue or project reports, depending on how you decide to track things.

A common way to group tasks would be to group them first by their project name and then by the task name within each project. That way if you have two tasks with the same name it's easy to see which project their in.

**Question**

I want to know what proofs are outstanding, what task and project they are tied to, when it was routed, when it is due, and who is moderator & the approver.

**Answer**

Outstanding proofs can be filtered by Awaiting Decision > Equals > True within a Proof Approval report. There is a column for Approver, which will tell you who has not made a decision yet.

You can reference the task or project the proof is tied to using text mode (see examples below).

```
displayname=Task Name
textmode=true 
valuefield=documentVersion:document:task:name 
valueformat=HTML
```

```
displayname=Project Name
textmode=true 
valuefield=documentVersion:document:project:name
valueformat=HTML
```

As for the routing date, due date and moderator, those fields currently cannot be pulled into any of Workfront's reports, so you would need to click into the Proof directly to view that information.

**Question**

Can you set up a custom form to automatically send to a requestor once their request is completed? Like as a "customer satisfaction" survey?

**Answer**

Here's one thing you can do that might meet your need. You can attach a Reminder Notification to an issue which will send an email to the "Entered By" after there was an Actual Completion Date entered. The Entered By is the person who created the issue.

You would create the Reminder Notification like we did in the webinar for "Reminder to fill out the After Action Review (AAR)", except this would be an Issue reminder. You would probably want to create an email template for it as well to provide a link to the survey. You will have to apply the reminder notification manually to each issue (or use bulk edit).

An integration would be better as it could automate the manual steps, but the reminder notification can be done right away.

**Question**

I created a report showing projects by template type. I can list the project owner but not the people assigned to a project.

**Answer**

If you want to pull in the Project Team (Staffing tab) to a column within your project report, you will want need to create this via text mode. The text mode is as follows:

```
displayname=Staffing 
listdelimiter=<p> 
listmethod=nested(projectUsers).lists 
textmode=true
type=iterate 
valuefield=user:name 
valueformat=HTML
```

## Text Mode code for the AAR Engagement Report

```
column.0.displayname=Task Details
column.0.value=<b>Project Name:</b>&nbsp;
column.0.valueformat=HTML
column.0.sharecol=true
column.1.valuefield=project:name
column.1.valueformat=HTML
column.1.sharecol=true
column.2.value=<br>
column.2.valueformat=HTML
column.2.sharecol=true
column.3.value=<b>Task Name:</b>&nbsp;
column.3.valueformat=HTML
column.3.sharecol=true
column.4.valuefield=name
column.4.valueformat=HTML
column.4.sharecol=true
column.5.value=<br>
column.5.valueformat=HTML
column.5.sharecol=true
column.6.value=<b>Task Owner:</b>&nbsp;
column.6.valueformat=HTML
column.6.sharecol=true
column.7.valuefield=assignedTo:name
column.7.valueformat=HTML
column.7.sharecol=true
column.8.value=<br>
column.8.valueformat=HTML
column.8.sharecol=true
column.9.value=<b>Actual Completion Date:</b>&nbsp;
column.9.valueformat=HTML
column.9.sharecol=true
column.10.valuefield=actualCompletionDate
column.10.valueformat=HTML
column.11.displayname=Name of Reviewer
column.11.linkedname=Name of Reviewer
column.11.namekey=view.relatedcolumn
column.11.namekeyargkey.0=Name of Reviewer
column.11.namekeyargkey.1=name
column.11.querysort=DE:Name of Reviewer:name
column.11.valuefield=Name of Reviewer:name
column.11.valueformat=customReferenceObjectAsString
column.12.displayname=AAR 1
column.12.description=In your view, does the work match stakeholders’ expectations? Did we achieve the intended results?
column.12.value=<b>AAR 1 Score:</b>&nbsp;
column.12.valueformat=HTML
column.12.sharecol=true
column.13.valuefield=AAR 1 - In your view, does the work match stakeholders’ expectations? Did we achieve the intended results?
column.13.valueformat=customDataLabelsAsString
column.13.sharecol=true
column.14.value=<br>
column.14.valueformat=HTML
column.14.sharecol=true
column.15.value=<br><b>AAR 1 User Comment:</b>&nbsp;
column.15.valueformat=HTML
column.15.sharecol=true
column.16.valuefield=AAR 1 User Comment
column.16.valueformat=customDataLabelsAsString
column.17.linkedname=direct
column.17.namekey=AAR 1 Reviewer Comment
column.17.querysort=DE:AAR 1 Reviewer Comment
column.17.valuefield=AAR 1 Reviewer Comment
column.17.valueformat=customDataLabelsAsString
column.18.linkedname=direct
column.18.displayname=AAR 1 Needs Attn
column.18.querysort=DE:AAR 1 Needs Attention
column.18.valuefield=AAR 1 Needs Attention
column.18.valueformat=customDataLabelsAsString
column.19.linkedname=direct
column.19.displayname=AAR 1 Needs Attn Notes
column.19.querysort=DE:AAR 1 Needs Attention Notes
column.19.valuefield=AAR 1 Needs Attention Notes
column.19.valueformat=customDataLabelsAsString
column.20.displayname=AAR 2
column.20.description=Do You Believe This Work Will Make an Impact?
column.20.value=<b>AAR 2 Score:</b>&nbsp;
column.20.valueformat=HTML
column.20.sharecol=true
column.21.valuefield=AAR 2 - Do You Believe This Work Will Make an Impact?
column.21.valueformat=customDataLabelsAsString
column.21.sharecol=true
column.22.value=<br>
column.22.valueformat=HTML
column.22.sharecol=true
column.23.value=<br><b>AAR 2 User Comment:</b>&nbsp;
column.23.valueformat=HTML
column.23.sharecol=true
column.24.valuefield=AAR 2 User Comment
column.24.valueformat=customDataLabelsAsString
column.25.linkedname=direct
column.25.namekey=AAR 2 Reviewer Comment
column.25.querysort=DE:AAR 2 Reviewer Comment
column.25.valuefield=AAR 2 Reviewer Comment
column.25.valueformat=customDataLabelsAsString
column.26.linkedname=direct
column.26.displayname=AAR 2 Needs Attn
column.26.querysort=DE:AAR 2 Needs Attention
column.26.valuefield=AAR 2 Needs Attention
column.26.valueformat=customDataLabelsAsString
column.27.linkedname=direct
column.27.displayname=AAR 2 Needs Attn Notes
column.27.querysort=DE:AAR 2 Needs Attention Notes
column.27.valuefield=AAR 2 Needs Attention Notes
column.27.valueformat=customDataLabelsAsString
column.28.displayname=AAR 3
column.28.description=Are you proud of the work you did on this?
column.28.value=<b>AAR 3 Score:</b>&nbsp;
column.28.valueformat=HTML
column.28.sharecol=true
column.29.valuefield=AAR 3 - Are you proud of the work you did on this?
column.29.valueformat=customDataLabelsAsString
column.29.sharecol=true
column.30.value=<br>
column.30.valueformat=HTML
column.30.sharecol=true
column.31.value=<br><b>AAR 3 User Comment:</b>&nbsp;
column.31.valueformat=HTML
column.31.sharecol=true
column.32.valuefield=AAR 3 User Comment
column.32.valueformat=customDataLabelsAsString
column.33.linkedname=direct
column.33.namekey=AAR 3 Reviewer Comment
column.33.querysort=DE:AAR 3 Reviewer Comment
column.33.valuefield=AAR 3 Reviewer Comment
column.33.valueformat=customDataLabelsAsString
column.34.linkedname=direct
column.34.displayname=AAR 3 Needs Attn
column.34.querysort=DE:AAR 3 Needs Attention
column.34.valuefield=AAR 3 Needs Attention
column.34.valueformat=customDataLabelsAsString
column.35.linkedname=direct
column.35.displayname=AAR 3 Needs Attn Notes
column.35.querysort=DE:AAR 3 Needs Attention Notes
column.35.valuefield=AAR 3 Needs Attention Notes
column.35.valueformat=customDataLabelsAsString
column.36.displayname=Done
column.36.valuefield=Review Complete
column.36.valueformat=customDataLabelsAsString
```

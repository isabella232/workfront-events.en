---
title: Ask the Expert - Measuring velocity
description: Learn to measure and track velocity using [!DNL Workfront] reporting. This workshop was recorded on August 14, 2019.
activity: use
doc-type: feature video
team: Technical Marketing
kt: 9912
---
# Ask the Expert - Measuring velocity

Learn to measure and track velocity using [!DNL Workfront] reporting. This workshop was recorded on August 14, 2019.

>[!VIDEO](https://video.tv.adobe.com/v/341057/?quality=12)

## Custom fields used in the presentation

Save some time by copying and pasting the calculations below.

**First Commit Date**

Format: Date

Calculation:

```
IF(ISBLANK(First Commit Date),Default Baseline.Planned Completion Date,First Commit Date)
```

**First Duration**

Format: Text

Calculation:

```
IF(ISBLANK(First Duration),Default Baseline.Duration,First Duration)
```

**Work-to-Commit Ratio**

Format:Number

Calculation:

```
ROUND(DIV(Actual Duration,First Duration),1)
```

**Work-to-Commit Ratio Status**

Format:Text

Calculation:

```
IF({Work-to-Commit Ratio}>2,"Terrible",IF({Work-to-CommitRatio}>1.6,"Poor",IF({Work-to-Commit Ratio}>1.2,"Not Bad","Exc ellent")))
```

**Adjusted Velocity**

Format:Number

Calculation:

```
ROUND(DIV(Actual Duration,Duration),1)
```

**Adjusted Velocity Status**

Format:Text

Calculation:

```
IF(Adjusted Velocity>2,"Terrible",IF(Adjusted Velocity>1.6,"Poor",IF(Adjusted Velocity>1.2,"Not Bad","Excellent")))
```

## Q&A

**Question**

Hello, thanks for organizing this webinar. I have a question about Field in Workfront. In our system, we created a custom field called "State" which is a combination of Status and Condition. This State field contains lot of statues in thousand projects which is very important for our Tableau data extract. However, now we want to eliminate this field and use Conditon field, the native field instead. Do you have any idea how can I flip this field over without losing data. All I can think of doing it without losing data right now is switch it manually from project to project.

**Answer**

For a situation like this you can use filtering and bulk editing to semi-automate the chore of populating the Condition field based on your State custom field.

Here are the steps:

1. Determine which State values you want to map to Condition values. For example, let’s say you have a State value of “Late” and “Very Late” that both map to a Condition value of “In Trouble”
1. Create a project report showing all projects with a State value of “Late” and “Very Late”
1. Run the report. Make sure you are showing all projects (see options at lower right of the report)
1. Click on the checkbox in the upper left of the report in the bar with column headings. This will select all the projects in the report
1. Click on the Edit button above the report list 
1. Set the Condition Type to Manual
1. Set the Condition field to In Trouble
1. Click Save Changes


**Question**

How is Excellent, Not Bad, etc defined?

**Answer**

This was just an example, but here’s how I set it up. First I calculated two indexes:

Adjusted Velocity

The formula for this is Actual Duration/Planned Duration (which is stored in the Duration field in a project). Since the Planned Duration of the project can change every time the project is replanned, the Planned Duration represents the final replan.

Work-to-Commit Ratio

This formula is like Adjusted Velocity except that instead of using the Planned Duration value from the final replan we want to use the Planned Duration that was first promised to the customer. We’re assuming that the Original baseline contains this information (and we’re planning from now on to ask our project managers to plan their projects in this way so that we can capture accurate data). We captured this duration value from the original baseline and called it First Duration.

By dividing Actual Duration by either Planned Duration or First Duration we end up with a number that can tell us how close we came to being on target. If the Planned Duration or First Duration are equal to the Actual Duration the index will equal 1. If Actual Duration is greater the answer will be more than 1. The greater the number the worse we did on meeting our date.

So, given all that I decided to assign statuses for both Adjusted Velocity and the Work-to-Commit Ratio as follows:
 
* 1.1 or below I called Excellent. 
* 1.2 to 1.5 I called Not Bad.
* 1.6 to 1.9 I called Poor.
* 2 or greater I called Terrible.

**Question**

What needs to be done by the worker to track the amt of time it takes to do the projects?

**Answer**

We're not tracking actual hours spent working on the projects here, we're just tracking and comparing duration. But if you're tracking hours, and want to use actual hours over planned hours to calculate velocity, you could do this same type of report by comparing planned hours to actual hours. You would want to capture planned hours from the Original baseline as well.

**Question**

Can you provide filters used for Velocity?

**Answer**

I used two filter rules for the Velocity reports:

* Categories >> ID >> Equal >> WPI Project Data (this is the custom form that contained all the calculated fields. I only want to see projects that are using this custom form)
* Project >> Status >> Equal >> Complete (I only want to see completed projects because they have an Actual Duration value that represents how long it took to get everything done. Current projects would not provide an accurate Actual Duration for calculating velocity)

I also added other filtering to keep my report small enough to manage for the webinar, but in your production environment you would probably want to see all projects with the WPI custom form in a particular time period. You might want to filter on the project Actual Completion Date for that.

**Question**

If you copy a project does it carry the same baselines to the new project?

**Answer**

No, the baselines are not included in the copied project

**Question**

For a task approval process, can you show me how to create a report that provides an audit trail by task in a project with a time/date stamp for each approver?

**Answer**

Create a Task report. In the Columns (View) tab click on Add Column. In the "Show in this column:" box type "approv". This will show you the various approval fields available to report on. I would suggest you add a column for everything at first (except any IDs), then you can see what information is displayed.

Next go to the Filters tab and add a filter rule for:

Task >> Is Approval >> Equal >> True. This will only show tasks that have an approval attached.

Add additional filters as needed.

**Question**

I would like to create a proof report. A list of projects showing how many proofs they have and how many versions of that proof exist.

**Answer**

Create a document report.

The default view will show the version number. You’ll want to leave that there but you can change any other columns.

Group the report by Project Name.

Filter the report by Current Version:Proof ID is not blank.

This will give you a list of all the proofs in each project. It will have a row for each proof and display the version number (which will be the same as the total number of versions).

**Question**

Can you use velocity at task level? Rather than project level?

**Answer**

Yes, but you will need to copy the project custom form and create a task custom form from it. Then you will need to edit the calculation in the First Commit Date field and change the reference to "Default Baseline" to "Default Baseline Task". Do the same for First Duration. After that you can attach the task custom form to any tasks you want to measure. You will need to create task reports instead of project reports for these. However you will still need to make sure that the Original project baseline is set as the default baseline. All the task data is kept in the same baseline with the project data.

**Question**

Does the first commit date have to be set manually by the project owner? Or could it pull from existing fields?

**Answer**

The First Commit Date is captuerd from the default baseline. As long as the default baseline is the original baseline this will show the planed completion date of the project at the time it was first set to Current status.

**Question**

Calculated fields in custom forms still need to be periodically refreshed correct? Or will that happen automatically overnight (or at some other trigger) now?

**Answer**

Calculated fields are recalculated:

* When a user edits the object
* On bulk edit with activated Recalculate Custom expressions
* Modifications to the form with selected ‘Update previous calculations’ option

**Question**

If the velocity is considering Duration, should Percent Complete in Project Preference be based on Duration?

**Answer**

No, the Project Preferences option refers only to how Percent Complete is calculated. The duration value itself is not affected by this setting.

**Question**

What is the difference between first and plan duration?

**Answer**

First Duration is the number of days you originally promised the customer the project would take. We get this number from the original baseline that was recorded when the project was changed from Planning to Current.

Planned Duration is the number of days from the start of your project to the Planned Completion Date. Initially these two durations are the same, but if the project was ever replanned and the Planned Completion Date changed, so did the Planned Duration.

The value of the Velocity reports comes from our being able to see how much the Planned Duration has changed from the First Duration. We can see this as far back as when we first started recording baselines as projects changed from Planning to Current.

**Question**

Can you have workers set by color so they are the same across all reports?

**Answer**

If you group by Assigned To >> Name in a task report then you can assign a color to particular workers in the Chart tab. Just choose the Custom Colors option next to the Assignged To >> Name box in the Chart tab and add a color for each worker.

**Question**

I am trying to determine if it is possible to create a dashboard with one area that looks at a task level custom form to see if it is present and secondary if certain fields are not blank. Is this possible?

**Answer**

Let’s see if I understand your question. Suppose I have a task custom form called Tammy Form with a field in it named Tammy Field.

You’re wanting a task report that will show all tasks that have Tammy Form attached and where Tammy Field is has some value in it.

Yes, you can do that. You would just need a filter in your task report with two filter rules:

Categories >> ID Equal Tammy Form

Task >> Tammy Field Is Not Blank

**Question**

Is there a way to create a report to look for a specific named document in the Document Library? Part of the dashboard we want to measure if certain documents exist.

**Answer**

Yes. You need to create a Document report. It sounds like you might want to provide a specific document name each time you run the report. If that’s the case I would recommend going to Report Options and selecting Report Prompts. Add a prompt for Document >> Name.

**Question**

Can you choose a colour / hex value not listed in the chart tab but that is a new colour which is new hex value for example a new colour from my brand colours to allow me customise the reports?

**Answer**

Yes, you can enter any RGB code that you might have been able to find. This is a standard code that tells the amount of Red, Green and Blue contained in the color. Workfront will accept any hex value from 000000 to FFFFFF, so if you know the code of your brand color you can use it.

**Question**

Can you please re-state the definition of the reports in the dashboard (provide a statement of what each report measures)?

**Answer**

Adjusted Velocity Status Chart

> This shows how well we did on completing projects on time when comparing the Actual Duration of the project with the Planned Duration. The Planned Duration having been adjusted as the project was replanned during its life cycle.

Work-to-Commit Ratio Status Chart

> This shows how well we did on completing projects on time when comparing the Actual Duration of the project with the First Duration. The First Duration being the original time we promised the customer that the project would take to complete. The First Duration was calculated from the Duration value of the project when it was first changed from Planning to Current status. This was the Duration recorded in the Original baseline.

Velocity Status List Report

> This report contains all the calculated custom fields and the significant dates for the same projects in the charts. Its purpose is to allow us to check our calculations and get more detail information if desired.

**Question**

How did you add the new data to the x axis?

**Answer**

When you group by anything in a report it will allow you to create a chart. You can then set the X or Y axis in the Chart tab.

**Question**

Can you go over the difference between first duration and actual duration?

**Answer**

First Duration is the number of days you originally promised the customer the project would take. We get this number from the original baseline that was recorded when the project was changed from Planning to Current.

Actual Duration is the number of days from the start of your project to the Actual Completion Date.

**Question**

How does the project baseline factor into this report?

**Answer**

The Original baseline of the project contains the Planned Completion Date and the Planned Duration that existed when the project was first changed to the status of Current. If your process was to plan the project before setting it to Current then this would represent the date you committed to complete the project by.

**Question**

Is there a way to mass apply the new form to old projects?

**Answer**

Yes, you can select multiple projects from a list. When you do this an "Edit" option appears at the top left of your list. Clicking on Edit when multiple objects are selected puts you in what we call "bulk edit". You can add a custom form to multiple projects in this way.

A shortcut for adding custom forms to a large number of projects is to create a report that you filter to include only those projects you want. Then, instead of selecting projects individually, just click on the checkbox above the first checkbox in the list and you will select the entire list.

**Question**

Is it possible to remove duplicate entries from within the grouping on an assignment report, but not across groupings?

**Answer**

The best way to think about groupings in lists reports is this:

First, you control what items show up in the list using the Filter tab. There will be no duplicate entries. The filter is applied to each object. If it passes through the filter it will appear once in the list, if it doesn’t it won’t appear at all.

Next grouping is applied to the filtered list. A grouping identifies one thing about the objects in the list, like the name of the portfolio it’s in (you can’t group on a list of things, only on a single thing). Then all objects with the same value will appear in that grouping, like all projects in the same portfolio. Any projects that don’t have a portfolio selected will appear in the grouping named “No Value”.

As a result there is no way any objects can appear in more than one grouping. And whether an object appears in the list at all is entirely controlled by the filter (and if the person running the report has rights to view it).

**Question**

Would you recommend any other report to track Velocity? Just a high level recommendation is great because I know there's not enough time to go through in details.

**Answer**

As with any report, the first thing you need to do is decide what you want to know. The next step is to access that information, which in some cases means you need to start tracking it.

One reason I decided to compare Actual Duration with two kinds of Planned Duration was because I thought it provided interesting insights about velocity. The data was also already available, so I didn’t have to start tracking it. With a few calculations I could extract the data in a form I could report on it.

But you might just as well decide to track other information about tasks or projects to report on.

Workfront doesn’t have any built-in velocity reports, so I would recommend you and your team brainstorm on what you want to know to determine velocity and then see what you need to track.

**Question**

Are you able to calculate anything at the COLUMN level? Instead of calling a calculated FIELD from a custom form?

**Answer**

It would have been possible to use a valueexpression in text mode to do these calculations. We could not have done First Duration or First Commit Date though, we needed to capture those in a place where they wouldn't change.

As for Work-to-Commit Ratio Status and Adjusted Velocity Status, these needed to be custom fields so we could use them in the Chart tab. The Chart tab does not recognize text mode groupings, they need to be custom fields. And since we needed Work-to-Commit Ratio and Adjusted Velocity to calculate those statuses we needed them to be custom fields as well. So in this case they all needed to be custom fields, but it’s always good to consider both ways and choose what will work best. Thanks for the question.

**Question**

Our projects change often due to customer delays or changes throughout. Our report might show all as 'terrible'. What is a recommendation for tracking reasons for change? We thought of adding a custom form at the document level that reports reason for change (either internal or client change), but wondering what a best practice is.

**Answer**

The best practice is to use a dropdown to track this. Put as many "reasons" as you can think of in there to start with, then add an "other" option to capture a reason that's not on the list. If that new reason looks or becomes common add it to your dropdown. You can easily report on things in a dropdown list, and you can group on this field (you can't group on checkboxes or a multi-select dropdown).

Just another comment on this. You may not want to include all projects in your Velocity reports. If you’re fixing bugs or “going where no one has gone before” you’re probably not making the same kind of a commitment to a completion date as if you’re building a house that you’ve built many times before.

So make sure you focus your velocity reporting on places where it can help you meet your goals.

**Question**

If I set the default baseline on a project to 'Original' and then take the project out of current and put it back in current, will it change my default baseline?

**Answer**

Yes. Everytime you change the status to Current you'll get a new baseline and it will be the new default. But all the previous baselines will still exist and you can manually set the original baseline to be the default baseline again.

**Question**

Is there a way to set-up in a report which fields are editable? Can I set restrictions for certain fields?

**Answer**

You can restrict view and edit rights for fields in a custom form. You will need to include the fields in a section, and in the section settings you can choose the rights needed for users to be able to view or edit fields in the section.

**Question**

Can you create a report that looks for a specific named document in the document library?

**Answer**

Yes. You need to create a Document report. It sounds like you might want to provide a specific document name each time you run the report. If that’s the case I would recommend going to Report Options and selecting Report Prompts. Add a prompt for Document >> Name.

**Question**

In reports, why are values available as column but not available for selection or grouping. For example: Issue Source.

**Answer**

The main reason a column might be viewable but is not available for grouping would be that it could contain a list, like a checkboxes custom field or task assignments. Grouping on a list is not allowed.

**Question**

How can I separate in a report (by which fields) when the entry of hrs happened and when the hrs were actually performed?

**Answer**

The Entry Date field for the Hour object refers to the date the hours were worked. This makes Entry Date different than on other objects, where it means the date the object was created. Even though there is not a creation date for hours there is a "Last Updated Date", which is initially the creation date and then any date the hour was edited thereafter.

**Question**

From a reporting standpoint how can we access Baseline data? I have a project with multiple baselines. I want to see how individual tasks were planned in each baseline. Is there a way to write a report that will show the project plan for each baseline?

**Answer**

A report will show you whatever fields you want to see for the baseline that is currently set as the default, so you could change the baseline and refresh your report to see fields with the new baseline.

But if you want to see information about your tasks graphically you can do that using the Gantt chart feature. Turn Gantt on in a task list (using the Gantt icon in the upper right next to Autosave) then go to the Settings icon just below and to the right and click on it. Check the Baseline box and it will show you all the baselines. You can select these one at a time and see the changes in your tasks in the Gantt view.

**Question**

How to create a report to find the changes in its status for a defined period for example last month.

**Answer**

The Analytics feature in Workfront provides a slick way for you to view historical data, including status changes.

But you can also get status change information using a Note report. You can filter to see status changes on projects if you are tracking the Project Status field.

So first, go to Setup>Interface>Update Feeds and make sure Project Status is one of the Built-in Fields that is being tracked. If it isn’t you need to add it.

Now create a Note report and do the following:

In the Columns (View) tab:

* Replace the “Note Text” column for “Audit Text”. This will display information about what the status changed from and to
* Leave the “Project: Name” and the “Entry Date” columns
* Click on the “Entry Date” column and then check “Sort by this column” in the Column Settings panel. If you want to see the most recent status changes on top sort it descending.

In the Groupings tab:

* Group by Project: Name

In the Filters tab create the following filter rules:

* Note >> Audit Type >> Equal >> Status Change
* add any additional rules to filter by the Note Entry Date. You might prefer to leave this out of Filters and use a report prompt instead
* Filter on project, portfolio or other data as desired.

**Question**

As a Planner can you pull reports for other users?

**Answer**

A Planner can create reports and share them with any users, even with people who are not users. When viewing the report, go to Report Actions>Sharing, then click on the gear icon in the upper right of the Report Access box. Choose the "Make this public to external users." option. You can copy the link provided and send it to anyone. They will see the report in real time in their browser.

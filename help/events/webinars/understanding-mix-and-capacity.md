---
title: Ask the Expert - Understanding mix and capacity
description: Learn to measure mix and capacity within your enterprise. This webinar was recorded on October 2, 2019.
activity: use
doc-type: feature video
team: Technical Marketing
kt: 9913
---
# Ask the Expert - Understanding mix and capacity

Learn to measure mix and capacity within your enterprise. This webinar was recorded on October 2, 2019.

>[!VIDEO](https://video.tv.adobe.com/v/341119/?quality=12)

## Q&A

**Question**

How do you put %s on a column chart?

**Answer**

The % values listed in the Mix Report were there because in the chart tab we chose "Group Columns" and "Stacked to 100%". If we chose "Stacked" it would show the planned hour totals and not the percent.

**Question**

If your department/organizations workload is a mix of projects/tasks, and issues/requests, how do you recommend getting a high-level review (in a Workfront report) of a WPI.

**Answer**

Projects, tasks and issues need to each have their own reports with their own custom forms. They can each use the same Work Type field however. You may want to display the three reports in one dashboard.

**Question**

Do we have to bulk edit tasks in order to make them operational or strategic?

**Answer**

The technique we're suggesting is to create a report that will allow you to get a list of tasks that are operational. Once you have that you can select all the tasks at once, bulk edit them, then attach the custom form with Work Type and set the work type to Operational for all the tasks at once. You would follow the same procudure to gather a list of strategic tasks, bulk edit them and add the custom form, etc.

A few ideas are mentioned in the Webinar for custom prompts which might help you get a list, like checking for certain words in the task name, the project owner, portfolio, or users assigned. These are just ideas. You should devise a report that works best in your situation.

**Question**

If I have 4 categories in my mix, can I create a goal for each and then report on delta between forecast vs plan vs actual? (4 categories Campaign, Business Unit, Web, and Product). We have the categories at the project level in custom form/fields. Goal would be create a quarterly forecast (budget/forecast) then track planned hours towards that and ultimately actual.

**Answer**

If you have all the categories in one custom field (let's call it Work Type for now), just create a project report grouping on Planned Hours first and Work Type second. Filter your project report to show projects in Planning within desired date ranges. Use a chart with grouped columns or bars stacked to 100% if you want to see percentages. This could be your Forecast report.

You could copy the report and edit it to create a report based on Current projects, still showing the mix based on Planned Hours.

You can copy the report again, change it to group by Actual Hours instead of Planned Hours, and show only completed projects within desired date ranges. This would show the percent mix based on actual hours.

**Question**

Will this work if you have several category IDs on a project or task?

**Answer**

Yes, if you have multiple IDs they need to be separated by a tab, like this: 

```
EXISTS:1:$$EXISTSMOD=NOTEXISTS
EXISTS:1:$$OBJCODE=OBJCAT
EXISTS:1:categoryID=5d76d82600e7926bb51eeb1e0886810e 5d54288d01034619f2eb2c74f6472f18
EXISTS:1:objID=FIELD:ID
```

The best way to separate them with a tab character is to create your list of categories in the builder first. Put in multiple custom form names and when you switch to text mode you will see them as IDs separated by tabs.

The multiple IDs are treated as ORs, so if any one of them are attached to the task it will not appear on the report.

**Question**

Are the report prompts 'ANDed' or are they 'ORed'?

**Answer**

The Individual custom prompts are 'ANDed'. So if you specify Pam as the project owner and Bill as assigned to the task you will only see tasks assigned to Bill that are in projects where Pam is the project owner.

**Question**

Why can you only sort by certain columns? i.e. you can't sort by assignments.

**Answer**

"Assignments" is a list, and you can't sort or group on a list of items. You can only sort or group on an individual item.

To illustrate the point, imagine a list of assignments like this on one task: 

```
Jane
Bill
Dan
```

And a list of assignments like this on another task: 

```
Bill
Jane
Helen
```

Which task should appear first in a sort? You could say "sort by the first name in the list" but this is not neccesarily useful, since you can't control the order. Workfront avoids the problem by not allowing you to sort by lists at all.

What about grouping by a list? If we could group by a list of names you would find all tasks assigned to Jane, Bill, Dan grouped together and all tasks assigned to Jane, Dan, Bill (same list, but in a different order) in a different grouping. Again, Workfront avoids the problem by not allowing grouping by lists.

**Question**

Are planned hours used for strattegic tasks and actual hours for operational?

**Answer**

No. In our example we are using Planned Hours to show the level of effort planned for both strategic and operational tasks. This allows us to compare them easily, whether in the past, present or future. You can also used actual hours to compare strategic and operational tasks, but only for tasks in the past since actual hours are the hours people have reported as the time they actually spent working on the tasks.

**Question**

In the resource planner, how do we account for tasks that were planned in the past, but not completed? The planned hours do not seem to roll forward and therefore, does not show in future weeks as tasks/hours that need resources.

**Answer**

There is no "automatic" rolling forward of uncompleted work. You will need to replan your project when this happens. Maybe the resources that you had originally assigned to a certain task are not available in the new timeframe, so the project manager has to look at this and decide the best way to replan. This might mean involving stakeholders and getting approvals for the changes in the plan.

**Question**

Rather than inputting 2 hours/day for checking email, breaks, would you recommend adjusting their FTE?

**Answer**

Yes, if you set the FTE to .75 that will show a user as available 6 hours per day in the Resource Planner. This will be their availability every day. If you want to show them as unavailable for different periods depending on the date, such as unavailable the last day of each quarter, then an overhead project is the way to do this.

Some people prefer overhead projects because they can build them for themselves and change them when they want, whereas they may not have rights to edit their own FTE.

**Question**

Is the data for the team capacity dashboard available to anyone you share the report with regardless of what permissions they have on the work?

**Answer**

If a user does not have permission to view the object, it will not be visible within the report/dashboard. However, if you are wanting everyone to see the same results, you can go into Report Actions > Edit > Report Settings and enter in your name in the field, "Run this report with the access rights of." This will allow the users who are shared on this report to see the exact results that you see. It will not grant them additional access to the result itself, so some results may or may not be clickable.

**Question**

How can we create a report that shows all staff assigned to a project overall (not at task level)?

**Answer**

You can create a column within a Project Report that shows all users listed as part of the Staffing tab (Project Team). You will want to use the following text mode:

```
displayname=Project Team
listdelimiter=<p>
listmethod=nested(projectUsers).lists
textmode=true
type=iterate
valuefield=user:name
valueformat=HTML
```

**Question**

I would like to have a report/dashboard that incorporates how my team works. In particular the folllowing scenarios: - Projects I own / Projects created for me / Tasks I assigned to others / Tasks assigned to me

**Answer**

Projects I own

There is a Built-In report named "Current Projects" which will show you all Current projects. You can edit this project and add a filter rule:Project > Owner ID > Equal > $$USER.IDThen save and rename the report to "Projects I Own".

Projects created for me

There is a Built-In report named "My Projects" which will show you all the Current projects where you are on the project team (meaning you are the Owner, Sponsor, or assigned to task). Not sure if this is what you're asking for but there are no other ways to know if someone created a project for you other than making you the project owner, sponsor or assigning you to a task.

Tasks I assigned to others

Create a task report with whatever filters you want, then go to the Filter tab and click on Switch to Text Mode. Add this code to whatever is already there:

```
EXISTS:1:$$OBJCODE=ASSGN
EXISTS:1:taskID=FIELD:ID
EXISTS:1:assignedByID=$$USER.ID
```

This will show you all tasks where the logged in user assigned at least one of the current assignees. If assignees were assigned by multiple people only the name of the first person who assigned someone will appear as "Requested By" on the task landing page. If you want to see all of the people assigned and who assigned each one you can add a column to your view, switch to text mode, and replace whatever is there with this:

```
displayname=All Assignees and Requesters
listdelimiter=<p>
listmethod=nested(assignments).lists
textmode=true
type=iterate
valueexpression=CONCAT("Assigned To: ",{assignedTo}.{name},"; Requested By: ",{assignedBy}.{name})
valueformat=HTML
```

Tasks assigned to me

There is a Built-In report named "My Tasks" which will show you all the incomplete tasks on Current projects where you are the task owner. I would suggest you change the filter to show you all tasks where you are one of the potentially many users assigned, not just the task owner. You do this by removing the filter rule

```
Task > Assigned To ID > Equal > $$USER.ID 
```

and replacing it with

```
Assignment Users > ID > Equal > $$USER.ID
```

**Question**

Is there a way to customize labels on charts? I've found that when I create a chart to reflect project statuses- the name of the home group ends up being included in the label.

**Answer**

Labels on charts use the field name of what you're grouping on. So the only way you can change the labels is to use a calculated custom field with whatever name you want. In the calculation section of the field put the field name of the native field you want to group by.

**Question**

How do you colour code the report bars on Chuck's Team Assignements please? I.e. amber for behind, red for late & green for on time? Also can you change the order to be more logical i.e. Red/Amber/Green or the reverse?

**Answer**

To change the colors used in the report for the Progress Status options, edit the report and click on the Chart tab. Look for the "Custom Colors >" drop down. It will appear next to the "Left (Y) Axis" box or the "Group Data by" box, depending on whether or not you choose to group columns or bars. In that drop down you can select colors. If you click on the numbers in the lower right of the color options you'll be able to select your color from a larger pallette.

Unfortunately you cannot change the order of these.

**Question**

Can you create a chart where it points to the Count of projects that a worker is assigned a task within?

**Answer**

Yes, here's how:

* Create a project report
* If the user in question is the logged in user the filter should include this line: 

```
   Project Users > ID > Equal >$$USER.ID 
```

* If not, put the user name in place of [!DNL $$USER.ID]. This will show all the projects where this person is assigned a task or is the owner or sponsor. If you only want to see projects where they are assigned tasks you should add these two additional filter rules:

```
   Project > Owner ID > Not Equal > $$USERID
   Project > Sponsor ID > Not Equal > $$USERID
```

* Create at least one grouping so you can create a chart. Group on anything, like company. Then click on the Chart tab and choose a chart. "Record Count" will be the default for one axis. This will be the number of projects the user has an assignment in.

When a user is given an assignment on a project (assigned to a task or project owner or project sponsor) that person is added to the project team and can be seen in the Staffing tab under the People subtab. If a user is removed from being the project owner, sponsor, or having any task assignments their name is still on the project team. It must be removed manually if you want it removed. Keep in mind this could affect the accuracy of your report results. To remove someone from the project team go to Staffing > People, select the person or persons, then click the Remove button that appears above the list.

**Question**

How can you change the descending order of a column in text mode (in a grouping)?

**Answer**

You can choose to sort most columns in the Columns (View) tab when building a report. This will sort your entire list report if you have no groupings. If you have groupings it will sort according to that choice within each grouping.

**Question**

How can I create column that will identify Team Members assigned to an approval stage?

**Answer**

If you are running a Task or Issue/Request report, there is a column available within the Report Builder called "Approvers and Status" that will pull in this information.

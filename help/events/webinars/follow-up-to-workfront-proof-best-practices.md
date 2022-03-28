---
title: Ask the Expert - Follow Up to Workfront Proof Best Practices
description: Learn why you should use automated workflow templates, how to create them, and how to adjust proof settings to ensure privacy. This webinar was recorded on March 4, 2020.

activity: use
doc-type: feature video
team: Technical Marketing
kt: 9917
---
# Ask the Expert - Follow Up to Workfront Proof Best Practices

Learn why you should use automated workflow templates, how to create them, and how to adjust proof settings to ensure privacy. This webinar was recorded on March 4, 2020.

>[!VIDEO](https://video.tv.adobe.com/v/341123/?quality=12)

## Q&A

**Question**

It appears that our instance auto generates proofs when uploading documents. Is there a way to turn this function on/off?

**Answer**

Yes, this setting can be turned off within your personal profile. If you click into My Settings > Preferences, there is a checkbox for "Automatically generate proofs when uploading documents" that can be selected or de-selected.

**Question**

Are you able to create Workflow that have empty stages so you can fill in individuals after attaching it to allow multiple teams to use a flow?

**Answer**

Yes, automated workflow templates can have blank stages so that depending on the team using it, different users can be added.

**Question**

In our use case, the designer uploads the document but the account manager generates the proof and sets up the approval flow. When a new version is needed the designer adds the version as document only and the process starts over. Is there a way to still have the account manager manage the proof flow and the designer manage the versioning without having to build the flow each time you generate the new proof?

**Answer**

If you set the Designer up with an Access Level of Work or Plan in Workfront, they will be given a proofing license. If their proofing license is set to Supervisor or Administrator, then they will be able to create new versions of proofs without having to take the manual step of having the Account Manager converting the new version and applying a workflow. The new version will just adopt the workflow from the previous version (and can also be altered or changed at this time).

**Question**

What is recommended for "Email Alerts?" decisions or all alerts?

**Answer**

I recommend that the Proof Creator / Owner is set to "Decisions" for their email alert. I recommend that all other proof recipients are set to "Disabled" for their email alert (even though the email alert is set to disabled, they will still receive New Proof, New Version, Late Proof and @Mention Email notifications). This setup makes sure that the email alerts are targetted and keeps email to a minimum.

**Question**

Are you able to change the owner of the proof that gets notified when the decisions are made? We tried to use the proofing tool but we weren't able to change the doc owner from the person who uploaded the original document. Example: A marketing manager uploaded the original document but it was a marketing specialist that ultimately was responsible for getting decisions and making changes.

**Answer**

To change the owner of the proof you will want to follow this path: Documents > Select the Proof > Click on "Proof Details" > Within the proof details window, locate the recipient that you would like to make the owner of the proof > Click on the Elipses button for that recipient and choose "Make Owner".

**Question**

Is there any tracking of the number of rounds of reviews have occurred?

**Answer**

Typically, rounds of revisions matches the number of proof versions.

**Question**

Can a person be in more than one stage? In other words, if we have a manager in an early review cycle who has final review in a later stage, how would we set that up?

**Answer**

While you cannot add a proof recipient to more than one stage of review on a proof, once the stage of review they are in is activated, they will be on the proof through the remaining stages for that version. This would allow them to continue to comment and reply to comments even though other stages have started. The key to make sure that this works is to make sure that you do not have stages lock when the new stage starts.

**Question**

Can you edit existing workflows?

**Answer**

Yes, you will want to navigate into Workfront Proof and then select Workflows from the left hand menu. There, you can edit stages, add users, remove users, add stages, etc.

**Question**

Is there a specific benefit to having the approval workflow of a document on the proof rather than the task? We have it set up to be on the document/art development task so IF the art is rejected at any stage of the approval process, the task goes back into action for the assigned designer to revise. That way, we don't have to work in two places. BUT, maybe I'm missing something important about going this route.

**Answer**

In the case of proofing, you are managing the approval process using the proof workflow engine. This allows you to use the collaborative proof review tool to gather feedback, comments, markups, decisions and stages. You will have the ability to utilize multiple workflow triggers to route the proof and can utilize settings that are unique to proof stages, such as Locking, Private Stages, Primary Decision makers. You also have the option of assigning unique proof roles and unique proof email notifications. Additionally, you have the option of reviewing content as varied as Static, Video and Interactive Proofs (around 150 different file types).

**Question**

Who can set the stage to a private stage? Admins only?

**Answer**

Creating the template is the admin responsibility, but any user who can create a proof can make the stage private.

**Question**

Is the deadline included in the email notification?

**Answer**

Yes, if you apply a deadline to a proof, that will appear in the email notification.

**Question**

Can you share a template with a Proof group?

**Answer**

You can - however, note that it will only be shared with members of the group that have Proof Licenses. You will not be able to share templates with Workfront Users or Guests that do not have proof licenses.

**Question**

How does a proof get rerouted to proof owner if rejected?

**Answer**

The proof owner remains on the proof through all of the proofs stages. If the proof is rejected, the proof itself does not need to be routed back to the owner. Instead the proof owner will be notified via email of the decision made, review the comments and get started on a new version.

**Question**

How to turn off/hide 'Download' document in Proof?

**Answer**

When you add a new proof, you will want to scroll to the bottom until you get to Proof Settings. There, you will see a checkbox for "Download original file" that you can select or de-select?

**Question**

How does this privacy setting in Account Settings affect proofing users who are specifically using the automated comparison (side by side with auto compare) -- Does setting default to DISabled prevent reviewer from comparing two versions?

**Answer**

For the Sharing Setting of "Recipients can View All Versions" - if it is set to "Disabled", if the recipient was not on version 1 but is on version 2, they will not be able to compare version 1 and 2. Note that Workfront Users with the Proof Permission level of Supervisor or Administrator will be able to see all versions regardless of the setting.

**Question**

Can we have several people upload a new version? for example a copywriter uploads version 1 and then we have the proofer in stage 1 . They see a change that needs to be made, can the upload version 2?

**Answer**

You can have proof recipients create new versions of proofs if they meet the following criteria: 1) They are the owner of the proof - or 2) They are set with the Author or Moderator proof role on the proof - or 3) They are setup with the Proof Permission Level of Supervisor or Administrator.

**Question**

How do you handle multiple proofs (eg. A, B and C) with the automated workflow. Do you start again?

**Answer**

You can apply an automated workflow template to mulitple proofs at the time of creating the initial version of the proofs. To do this, follow this path: Documents > Add New > Proof. On the New Proof page, select mulltiple files to upload, apply the automated worklflow template and create the proofs.

**Question**

Can a proof be exported with comments into a PDF?

**Answer**

You can export a Print Summary on a proof to a PDF file. This will contain all comments, markups, replies and decisions.

**Question**

Where can I see the proof settings?

**Answer**

To see the proof settings on an existing proof, you will want to follow this path: Documents Tab > Select the Proof > Click on "Proof Details" > From within the Proof Details Window that opens, you will want to expand the "Settings" area.

**Question**

Can you tag anyone in the private stage?

**Answer**

If you are a proof recipient within the private stage, you will be able to tag anyone within that private stage. If you are not in the private stage, you will not be able to tag someone from within the private stage.

**Question**

Once you activate a stage are you able to deactivate it?

**Answer**

You will not be able to deactivate an active stage, however, you can "Lock" the stage which will prevent people within the stage from making comments and decisions.

**Question**

What happens behind the scenes when 1 or more reviewers in a stage says changes required? Who gets notified to upload a new version?

**Answer**

This will depend on the proof creator and/or proof recipients "Email Alert" setting on the proof. I recommend that Proof Creators/Owners are set with the Email Alert of "Decisions" so that they are notified by email any time a decision is made on the proof.

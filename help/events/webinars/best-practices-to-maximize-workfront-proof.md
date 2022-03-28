---
title: Ask the Expert - Best Practices to Maximize Workfront Proof
description: Learn how to configure settings, enable great reporting, and avoid common pitfalls in Proof. This webinar was recorded on February 26, 2020.
activity: use
doc-type: feature video
team: Technical Marketing
kt: 9916
---
# Ask the Expert - Best Practices to Maximize Workfront Proof

Learn how to configure settings for success, access views (and other tricks) to enable great reporting, and understand how to avoid common pitfalls in Proof. This webinar was recorded on February 26, 2020.

>[!VIDEO](https://video.tv.adobe.com/v/341122/?quality=12)

## Q&A

**Question**

Currently, in order to give a recipient the ability to share a proof that was shared with them you have to manually check the "subscription" box under proof settings. Are there any plans to make this box auto-check by default?

**Answer**

This can be enabled/disabled as a default for individual users by an admin by following this path: PHQ Login > Account Settings > Users > Click into the User's Name > Default Proof Settings.

**Question**

If you don't select "New Proof" and you upload a doc and the user is set to "automatically generate proof". Are you able to modify those settings after the files are already uploaded?

**Answer**

Yes. You can adjust all proof settings by selecting the proof in the Documents tab and then clicking on Proof Details.

**Question**

Is this presentation applicable to the stand alone tool?

**Answer**

Recommendations on Proof Roles, Email Alerts, Decision Options, Forwarding Emails and Workflow Template Grouping/Sharing/Settings are all relevant to stand alone Proof.

**Question**

What would you use a Proof template for?

**Answer**

If your organization's content review process is often repeated or content is often reviewed by the same people, you can create workflow templates that contain those reviewers with proof roles and notification settings that you specify.

**Question**

What is a Proof Workflow Template?

**Answer**

A Proof Workflow Template is a template with a predetermined proof routing workflow that can applied to proofs. They allow you to both standardize and automate proof approval processes. 

**Question**

How can you create a proof template?

**Answer**

As an Administrator, you will want to follow this path: PHQ Login > Workflows > New > New Template.

**Question**

Does that Template Sharing functionality allow sharing with Groups and Teams or just individual users?

**Answer**

At this time you are unable to share workflow templates with Workfront Groups, Teams, Job Roles or Companies. You can however share them with individuals and can share with Proof Groups. To create a Proof Group, follow this path: PHQ Login > Groups > New Group.

**Question**

When submitting a proof - under Organization - is there away to clean up the folders each user sees so they only see the folders that are applicable to them? Instead of all the folders that have been made within the companies account?

**Answer**

This question is related to Workfront Proof Standalone. Within stand alone Workfront Proof you can utilize Private Folders in order to hide folders from specific users. This will allow for a more streamlined list of folders to choose from. Note that you can also use type-ahead logic to locate the folder that you would like to add a proof to as well.

**Question**

Do reviewers and approvers have the option to change these notification settings?

**Answer**

Administrators within Workfront have the ability to change the default email alert settings for users and contacts. Proof creators can then change the notification setting when creatng a proof as well as on their existing proofs. 

Recipients on proofs can always change their email alert for specific proofs at the proof level within the Proof Viewer tool by selecting the Settings Icon in the left menu.

**Question**

Do the email alerts override the global noticications?

**Answer**

Proof email alerts are completely independent of the global notification settings.

**Question**

If reviewers are set to "disabled," how will they know if there's a new proof for them to review if they have rejected a previous one?

**Answer**

Email Alerts are independent of the New Proof Email, New Version Email, At Risk Email, Late Email and @Mentions Email. If you choose "Disabled" as the Email Alert you will just be disabling notifications about activity such as comments, replies and decisions on the proof (with the exception of @Mention emails from comments).

**Question**

Is the disable emails setting Enterprise wide? or is it by Portfolio?

**Answer**

The setting located within Setup > Email > Review and Approval that enables/disables emails to be sent when proof recipients make comments is Enterprise Wide (it is a global setting).

**Question**

I have a "Guest" user who was added to the Proof and cannot review the proof. And the user does not have access in Workfront.

**Answer**

If the Guest can access the proof, but not make comments/decisions, make sure to check their Proof Role on the Proof. In this case, they may have been added to the proof with the "Read Only" proof role. If they are setup as a Reviewer or Reviewer & Approver on the proof and still cannot make comments/markups/decisions please submit a support ticket.

**Question**

Do guest users require a license?

**Answer**

Guest users do not require a license.

**Question**

I dont' see the proof decision box?

**Answer**

If you do not see the proof decision box on a proof, you may be set up on the proof with a proof role of Read Only or Reviewer, or the stage that you are in on the proof has not yet started.

**Question**

Can you clarify the setting in WF>Setup - if you have the option on to send email for every comment - these are sent even if the email in PHQ is Disabled? and who gets the emails??

**Answer**

The Workfront Setup > Email > Review and Approval notification option is independent of the Email Alert options at the proof level. If this is enabled everyone on every proof will get an email every time someone on the proofs that they are on makes a comment.

**Question**

Earlier you recommended "disabled" for email alerts outside of the proof owner. Will the recipients still get an email notification that a proof has been assigned to them in that case?

**Answer**

Yes. Email Alerts (which can be set to All Activity, Disabled, Decisions etc) are independent of Proof Notification Emails (New Proof, New Version, At Risk Proof, Late Proof, @Mentions).

**Question**

What if you have an instance where someone is added to a proof and they feel like they shouldn't be on there? Wouldn't removing "Not Relevant" not give them an option to choose?

**Answer**

This is a good use for the Not Relevant Decision option. However, if someone should not be on the proof, I would recommend that they @Mention the proof owner in a comment on the proof and ask to be removed. If someone that should make a decision on the proof makes a decision of "Not Relevant" when they should make a decision of Approved or Changes Required this could alter how the workflow applied to that proof works.

**Question**

Where can I find the checkbox for "require login" for guest users?

**Answer**

This will be located within the Proof Settings on the Proof Creation Page when creating a proof. If the proof has already been created, you can access this setting by selecting the proof in the Documents tab and clicking into Proof Details > Settings. Note that you can only share Login Required proofs with people that have a Proofing License.

**Question**

Can someone remove themself from a proof if they were added by someone else?

**Answer**

If the person has edit rights to the proof that they were added to they can remove themselves. People with Edit Rights will be Workfront Users with an Administrator or Supervisor level Proofing License as well as people added to the proof with Author or Moderator proof roles. Anyone else will need to removed by someone with edit rights.

**Question**

Why would I use document approval vs. Proof approval or vice versa?

**Answer**

Document Approval can be used for a document that does not require comments and markups inline with the document being approved. For example, I just need you to look at this document and either approve or reject it. Proof will allow for comments and markups within the document in the Proof Viewer tool. For example, I need you to look at this proof, add comments, add markups and make a decision. In the future, the plan is to unify the two pieces of functionality as they are very similar.

**Question**

We are a Marketing dept and we do an internal proof approval and then need to send out externally to the requestor. We don't give access to Requestors to our projects. We also don't want them to see all of our comments in the internal proof. Now we are making a new clean proof and downloading it and emailing it to them. We want to get them using Proof HQ but aren't sure how to accomplish that with out it also giving them access to our project. Any suggestions?

**Answer**

I would recommend using Automated Workflow Templates which will allow you to utilize "Private Stages". Private Stages allow you to hide the comments, markups and decisions from Guest Reviewers in other stages. This would allow your Internal Proof Review to be completely hidden from the external requestor. 

**Question**

Once a proof has been created by someone else, what's the best way to add yourself to be a reviewer and approver?

**Answer**

If you are a Workfront user with the Proof Permission of Administrator or Supervisor, you can add yourself as a Reviewer and Approver to any proof that you have access to. Otherwise, you will want to have the proof owner (or someone else with edit rights to the proof) add you.

**Question**

We have tried tagging users in a proof but,they do not receive an email notification. Is there something in account settings to make sure an email is sent?

**Answer**

I would recommend checking Email Filters / Spam Folder to see if the notifications have gone there and then make the necessary adjustments within the email application to whitelist those emails. You can also contact our support team with assistance on this.

**Question**

You can only @ someone if they have a proof license, correct? As in, this person has never been in the proof and you want to tag (@) them.

**Answer**

If you are a Guest or a Workfront User with a Proofing License of Manager you can @Mention anyone that is on the proof (regardless of if that person has a license or not). If you are a Workfront User with a Proofing License of Supervisor or Administrator or you are the Proof Owner you can @Mention anyone within your Contact List in the proofing platform.

**Question**

Biggest issue here: email %2B addressing (duplicate email addresses). Why and how does that happen and how can it be remedied?

**Answer**

This can happen if someone adds someone to a proof manually by using the wrong email address. If you run into this, an administrator can remove the incorrect email address from the Proof account by following this path: PHQ Login > Contacts > Select the incorrect email / guest instance > Delete. If you are running into issues with users being added with duplicate email addresses, please reach out to our support team for assistance.

**Question**

Once a decision is made and you have to change the proof back to production. What kind of access do you need to give to the production team so they can use the action of the comment if the proof is locked?

**Answer**

If a proof is locked, you will need to unlock the proof in order for people to Action Comments or Reply to Comments. People with the following permissions can unlock the proof: The Proof Owner, Workfront Users with a Proofing License Level of Administrator or Supervisor.

**Question**

What is the best solution for teams to know of proofs that are already in a persons queue?

**Answer**

You can create a Proof Approvals report inside of Workfront. You can then apply filters that to only display proofs for specific users that still require a decision to be made.

**Question**

Is there a way to download proofs with their associated approvals into a folder?

**Answer**

You can access and download a Print Summary report for your proofs which will include all comments, replies, markups, actions and decisions across all versions.

**Question**

When requesting users have access to reporting ProofHQ, will this also give them access to the section on the left (ie. workflows, contacts, account settings, etc)?

**Answer**

This will depend on their Proof License Level. If they are set up with the Manager or Supervisor license they will be able to access Contacts, but will not be able to access Account Settings and Workflows. If they are set up with the Administrator license they will have access Account Settings and Workflows.

**Question**

In my organization, the Project Manager sends approval request to the stakeholders for review/comments. You mentioned that we should not Add names to the Approval fields, how do you as the PM shares the creative proof to stakeholders?

**Answer**

The Approval field is for Document Approvals, which is fine to use if you just require a simple document approval. If you would like a Proof Approval (with comments, markups and a proof decision) you will want to add the Stakeholders to the proof with the proof role of Reviewer & Approver.

**Question**

How do you add people as new roles on any proof that has already been created?

**Answer**

To add proof recipients and select their proof role on an existing proof, you will want to follow this path: Select the proof in the documents tab > then click in Proof Details. When the proof details window opens, click into the Elipses button in the upper right of the stage and select "Share". You will then be able to add the recipients and select their proof role and email alert.

**Question**

If we grant access to Proof HQ to proof managers/ creators, are we able to block off the admin areas such as workflows, groups, etc?

**Answer**

Yes, This is determined by the Users Proof Permission. Users with the Proof Permission of Manager or Supervisor will not have access to Account Settings and Workflow Templates. Users with the Proof Permission of Administrator will have access to Account Settings and Workflow Templates. All Users with access will be able to access the Groups area.

**Question**

How can users see all the proofs they are assigned to without being a proof manager?

**Answer**

If a user would like to see all proofs that they still need to make a decision on, they will be able to use the Home or My Updates area in Workfront (depending on their access level). You can also create a Proof Approval report and apply filters to only show proofs that the logged in user is a Reviewer & Approver on.

**Question**

Hello, can you go over automated proofing workflows, for situations where there are 3 rounds of design and feedback and how to accommodate for when feedback is provided late, and how that can best be tied into tasks in WF for each round (design and project manager feedback)?

**Answer**

While you can take many different approaches to how you utilize tasks along with Review & Approval. An approach that I like to take is to have a task for "Proof Routing" and I use the proof workflow to manage the notifications to recipients (instead of assigning them a task). You could then create a task for "Proof Routing Round 2" and "Proof Routing Round 3" which can help you keep track of how many rounds went around. You will also be able to keep track of the progress on the proofs using the Proof Dashboard (PHQ Login > Dashboard > Proofs to Manage). This view will indicate the number of late proofs (as well as At Risk proofs) that you are managing.

**Question**

When a proof is deleted is a copy of that proof still on your servers?

**Answer**

Yes. If you delete a proof it resides within the Trash area of the associated Proof Account, It can be restored from there if needed and will remain there until and unless the trash is emptied.

**Question**

Is there a way to have new decision to be triggered if the another user rejects or approves with changes. ie. Proofing dept sees something, the project manager will have to make a new decision... even if they looked at it already and approved it. (trying to not make the proj manager not have to wait on proofreading dept to do their review)?

**Answer**

While this cannot be automated, you can set the Project Manager with the Email Alert of Decisions. This way when the proofreading department makes their decision, the Project Manager will be notified of the decision that was made and can then go back into the proof, review the comments made by the proofreading department and then change their decision if needed.

**Question**

Why when I check "Ask for Approval" when I send an Update in the Proof detail section, I only see the status SOC and not SOCD. Should we avoid using this checkbox? What is best practice for sending an update on a proof.

**Answer**

When using the "Ask for Appoval" function, you are working with the Document Approval functionality which will be independent of Proofing and the SOCD Progress Bar. If you need to update the proof role of a proof recipient, what you will want to do is follow this path: From the Documents Tab, select the proof > then click on Proof Details. When the proof details window opens you will see the list of recipients and the proof role (as well as Email Alert) option can be adjusted in line. This would allow you to (for example) change the proof role from Reviewer to Reviewer & Approver.

**Question**

Is it possible to ensure that final approvers don't have access to previous versions (and comments) if there in the same proof document? Does a new proof document need to be created, or is there a way to keep all versions and comments in one, and designate access to versions?

**Answer**

Within the Account Settings inside of proof you can control sharing / visibility access to your proofs. To update this setting so that proof recipients only see the versions of proofs that you designate (instead of seeing all versions of the proof) you will want to follow this path: PHQ Login > Account Settings > Settings > Sharing > Recipients can view all versions = Disabled.

**Question**

Can you add the proof dashboard screen as an external page to a WF dashboard? Will non-admins see the dashboard?

**Answer**

You can add the Proof Dashboard as an external page within a Dashboard. Note that this would only be visible by users with a proofing license.

**Question**

The Dashboard and Reporting features in ProofHQ are only available for Admins who have access to Proof though, right? Not general Planners who don't have admin access?

**Answer**

This is correct. Although, you can submit a support case with Workfront to request that all of your Proofing License users have access to the Proof system.

**Question**

Hello, a question on proof ownership flexibility: If a new Proof version upload is required in the absence of the original owner, is the best practice for them to add a colleague to the workflow as an Author and they will decide "Not Relevant"? (Delegating ownership only seems to work for a single version).

**Answer**

This use case and workflow would absolutely work. Another thing that you could consider however, is to have users that might need to upload new versions to proofs that they are not the owner be set up with the Proof Permission Level of Supervisor or Administrator. This permission level will allow them to upload new versions to proofs that they are not the owner of without having to add them to the proof as an Author or Moderator (which would both require a decision).

**Question**

As I understand it, you cannot add the same user on subsequent stages in an automated workflow, and this is problematic for us. Is this something you can alter to allow the same user to be in multiple stages?

**Answer**

While you cannot add a proof recipient to more than one stage of review on a proof, once the stage of review they are in is activated, they will be on the proof through the remaining stages for that version. This would allow them to continue to comment and reply to comments even though other stages have started. The key to make sure that this works is to make sure that you do not have stages lock when new stages start.

**Question**

Can you explain the routing of proofs between stages? How can you close one and move to the next stage?

**Answer**

There are a few options that we have available in automated workflow templates that will allow the to move from one stage to the next. Options that you can use include "On Proof Creation", "When All Decisions Are Approved in a parent stage" "When All Decisions Are Approved or Approved with Changes in a parent stage", "When All Decisions Are Made in a parent stage" as well as some other options.

**Question**

Can you remove a proof from a document that was automatically generated, but you didn't want it to be a proof?

**Answer**

If you have the setting for "Automatically generate proofs when uploading documents" is turned on, you will not be able to remove a proof from a document. Instead, you will want to re-upload that via the Add New > Documents button.

**Question**

Can a user say on stage 3 of the proof flow add another person as a Review & Approver?

**Answer**

If that user has Edit rights on the proof they can. People with edit rights will be: The Proof Owner, Proof Recipients added to the proof with the Proof Role of Author or Moderator, Proof License Users with the Proof Permission Level of Supervisor or Administrator.

**Question**

If a user is designated as an author can they upload a new version of the proof? This would be someone other than the proof originator.

**Answer**

Proof recipients with the proof role of Author and Moderator can add new versions to the proofs that they are on with that proof role.

**Question**

External users receive an email-per-proof for review. This can be challenging for them to track the status of all of the proofs that they have in play. Are there any dashboards or email status list options or upcoming features for external users to track their status on multiple proofs?

**Answer**

I would recommend adding these External Users to Workfront with a free Reviewer license. This will give them access to a My Updates page which will include a list of all outstanding proofs that they need to make a decision on.

**Question**

Can you explain more about the Decisions notifications? Will I only get notifications with proof comments from Reviewers and Approvals or will I also get the the comments from Reviewers and when would I get those?

**Answer**

Decision Email Alert notifications are only sent when Decisions are made on the proof. They will not be sent when comments are made. However, if you get a Decision email alert that indicates that a recipient on the proof made a decision of Changes Required, then you will know that is a good time to review the comments that they have added (which will be in the proof).

**Question**

In regards to the issue with forwarding emails, are you actually logging in as that owner of the email? And would this happen with locked down environments? Would it happen with an SSO environment?

**Answer**

This would log you into the proof as the person that forwarded the email to you. Using Login Required on proofs and using SSO will prevent you from accessing the proof as the person that forwarded you the email.

**Question**

Where do I access the dashboard and reports in proofing?

**Answer**

If you have a checkbox icon to the right of your search bar in Workfront, that means you have an integrated Workfront and Proof account. By clicking on that checkbox, you will be taken to Workfront Proof and the home screen will be the dashboard. Reports can be built using the Views option in your left hand panel.

**Question**

Under the "Role" section, there are 2 checkmarks at the bottom that mentions being about to add someone using an @mention etc. In the Proof settings, you can set default Roles for each person but there is not option to have those checkmarks automatically checked, so you are having to do that each time you create a proof. How can you make that a default for a user?

**Answer**

There is currently not a way to make this a default setting for proof recipients. However, you can save these as default settings for recipients within Automated Workflow Templates.

**Question**

How do you switch a proof owner?

**Answer**

To switch the owner of a proof you will want to follow this path: Within the Documents tab, select the proof and click into "Proof Details". The proof details tab will open. If the person that you would like to make owner of the proof is not yet on the proof, you will want to add them as a recipient by clicking into the Elipses button and selecting Share. Once the person is added to the proof (or if they are already on the proof) you will select their corresponding Elipses button to select "Make Owner". They will now be made the owner of the proof.

**Question**

In terms of new versions of proofs... the only way I understand to do this is to drag and drop the file on top the existing file. Is this the proper way to do so?

**Answer**

I would recommend creating new versions in this manner: select the proof in the Documents Tab, then click on the More button, choose New Version > Proof. This will take you to the New Version page which will carry over the workflow as well as allow you to make any adjustments that you need to make before routing the new version.

**Question**

Are you able to disable comments on proofs in order to share with a client so they don't see all of the internal feedback from the team? So that you don't have to re-generate a new proof.

**Answer**

I would recommend using Automated Workflow Templates which will allow you to utilize "Private Stages". Private Stages allow you to hide the comments, markups and decisions from Guest Reviewers in other stages. This would allow your Internal Proof Review to be completely hidden from the external requestor. 

**Question**

Does the Workfront Proof stage only add when using Automated Workflows is used and someone not added to the workflow opens the proof?

**Answer**

The "Workfront Proof" stage will be added to proofs if a non-recipient clicks into the proof. It will also be applied if someone converts a Basic Workflow Proof to an Automated Workfront Proof.

**Question**

Do we have the ability to set up a proof workflow where more than one decision can be made?

We're trying to provide reporting to our internal legal team on when outside legal counsel has completed reviews on proofs (how many days on average it takes them to complete their review, who completes it, etc.)

We started by adding a new decision to the proof workflow called "OC Review Complete", and figured we could put together a report to track these.

The problem is, it appears only one decision can be made on the workflow.

**Answer**

More than one decision can be made on a proof - however, there will only be one overall status on a proof which will come from the worst case scenario decision on the proof - or the decision made by a Primary Decision maker. 

Because of your reporting requirements, what I would recommend is that you have everyone on the proof use the same decision options (Approved, Approved with Changes, Changes Required) and then use the Reports within the Dashboard of Proof (PHQ Login > Reports) and apply the filter option to filter by recipients (include the outside legal counsel recipients in the filter) you will then be able to see the average turn around time on their proofs.

**Question**

Once a new version is dragged and dropped onto an existing proof, why do ALL the roles change or specifically go away?

**Answer**

When dragging and dropping a document as a new version, you are correct that the workflow is stripped from the new version. If you would like to retain the workflow from the previous version to the next version, select the proof in the Documents Tab, then click on the More button, choose New Version > Proof. This will take you to the New Version page which will carry over the workflow as well as allow you to make any adjustments that you need to make before routing the new version.

**Question**

Scenario – Forwarding proofs: An external client reviewing a proof may want to circulate internally at their organization before approving our proof. The others reviewing won’t necessarily be in the system, so it doesn’t seem @ in the comments would work. How should they best share - forward the email and they’d highlight to the recipient that any comments would not appear as their name?

**Answer**

You would want to use the Proof Subscriptions functionality. This can be enabled in the settings for the proof and allows for recipients on the proof to forward a generic public link to the proof and then allowing people to subscribe to the proof (essentially adding themselves).

**Question**

What is a best practice for using the folders within documents?

**Answer**

This will depend on the nature of the project, but something that you could consider is an Active Proofs Folder which contains all of the proofs / versions actively being routed around and an Approved Proofs Folder which contains all of the proofs that are finalized and approved. Once a proof is fully approved, you move it from the Active Proofs Folder into the Approved Proofs Folder.

**Question**

If I have 3 people on a group of reviews, can I set that I need approvals from 2 of them out of the 3?

**Answer**

Yes. You will want to add the two people that you need a decision from as Reviewers & Approvers and the third person as a Reviewer.

**Question**

We would like to send a proof to an external client (non-Workfront user) to review and comment on. We want to send them a clean proof (in other words – one with no internal comments on it). What are the correct step-up steps to make this happen to ensure that the external client gets the proof (just the proof, no access to the project itself) and how do the external clients “send” us back their marked up proof? We do not currently use proof templates/automated workflows.

**Answer**

I would recommend using automated workflow / automated workflow templates for this as it will allow you to use the "Private Stage" functionality. When using the Private Stage functionality you could have the comments/decisions and recipients of certain stages of review remain hidden from people in other stages. As an example, you could have an Interal Stage as a Private Stage and a Client Stage. The Clients will not be able to see anything to do with the Internal Stage while you would be able to see the activity in the Client Stage.

**Question**

Is it possible to keep specific users (aka proofreader) in one early stage without having them be looped in on later stages?

**Answer**

Once someone is added to a version of a proof in a stage, they will remain on that version of the proof through the remaining stages. You do have the option to lock their stage when the next stage begins (or manually) which will prevent them from being able to make any further comments.

**Question**

Where can we view a list of everyone who has reviewed and/or approved a proof, one what day and what time? For auditing purposes, etc. Also is there a place we can see all reviews and approvals for all versions of a proof?

**Answer**

To see a list of activity such as when comments and decisions were made you will want to click into the Activity History in the Proof Details. To access this, follow this path: Select the Proof in the Documents Tab > Click on Proof Details > Expand the Activity section. If you would like to see this information at the version level, follow this path: Select the Proof in the Documents Tab > Click on the Details Tab > Towards the bottom of the screen you will see a Versions section. From here you can access the proof details at the version level.

**Question**

Can you please talk a bit about private stages in proofing.

**Answer**

When a stage is made private, comments and decisions are not visible to people who are not added to this stage or are not Supervisors, Administrators, or Billing Administrators in the account. Also, reviewers who are added to a private stage can see only the stage they are added to on the proof and comments made in that stage.

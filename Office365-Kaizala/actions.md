---
title: Kaizala Actions
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 6/25/2019
audience: Admin
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.reviewer: nitinjms2
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 1eacc59a-dd14-43e9-b6b0-3c78773d5496
description: Learn how to use Kaizala Actions to get work done within a conversation context inside Kaizala.
---

# Kaizala Actions

Actions help people get work done through a conversation in Kaizala. Some Actions – like Jobs, Surveys, and Polls – are ready out-of-the-box with pre-defined settings. Once you publish an Action, people can find it in the Kaizala app and use it in a conversation from the Action Palette.

You can create new Kaizala Actions through the Action Designer, found in the [Kaizala management portal](https://manage.kaiza.la).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3aku3]

## Create Kaizala Action

1. To create a new Kaizala Action, go to **Extensions** > **Actions** from the left navigation bar.

2. Select **New Action** from the top right of the page. You will find a list of Action templates for you to choose from. Action templates are arranged in three categories.

   - **Collect Information** – Allows Action creator to create Actions that can be used to collect information from group members. Actions created using these templates can be added to the groups, and group members can respond anytime. It doesn't require to be posted in the group.

   - **Request Information** – Allows Action creator to create Actions that can be used to request information from group members. Actions created using these templates can be added to the groups, but need to be sent in the group for other users to respond with data.

   - **Post Information** – Allows Action creator to create Actions that can be used to post information to all group members.
    
3. Select a template:
    
   - **New Form** – Use to collect feedback from group members. It sends out a form for people to answer a question.

   - **Feedback** – Use to collect any type of feedback from a group.

   - **New Attendance** – Use to collect attendance from group members. This template enables custom configurations to customize attendance requirements of customers.

   - **New Survey** – Use to request specific answers from group members. Create a Survey Action with pre-filled questions. You can send this Action via the app at regular intervals.

   - **New Checklist** – Use to request updates on pre-configured checklist items from group members.

   - **Announcement** – Use to collect any type of feedback from a group.
    
4. Fill out the information on the page, and click or tap **Next**.

   |Menu  |What it's for  |
   |---------|---------|
   | Action name     | Pick a name of the survey or poll that people see in Kaizala.         |
   | Brief description     | Show a description in the **Discover** tab of the Kaizala app.         |
   | Customize icon     | Choose the icon for your Kaizala Action.         |
   
5. Enter the relevant details described in the next section based on the selected template.
    
### For Survey or Form template

1. Enter a card title. People will see this on the card-view of the Action after it's been posted.

2. Enter the question details and choose your answer types. You can add questions on a new page.

3. After you have entered the question, click or tap **Next**.

4. On the next page, tap the boxes to select if you would want the users to find:
        
   - Action introduction page (where people can find details about the Action)

   - Summary page (where people can review their submissions before submitting their responses)

   - Request for user's location as part of the response
        
### For Attendance template

1. Enter a card title. People will see this on the card-view of the Action after it's been posted.

2. You can choose to set cut-off time (if required).
   - Select daily cut-off time. Users submitting their attendance after cut-off time would be marked late.
   - Set time zone.

3. You can also set custom attendance statuses (for example, Present, Absent, Work from home, on Leave) for users to select.

4. Click or tap **Next**.

5. On **Setting** page, tap the boxes to select if you would want the users:
        
   - To submit their photo while submitting their attendance.

   - To allow multiple check-in in a single day. Users can submit attendance as check-ins at different times for the day.

   - To capture a phone number in the response.

   - To checkout for every check-in.

   - To allow addition of responder attributes in the generated attendance report.

 ### For Checklist template

1. Enter a name for the checklist. People will see this on the card-view of the Action after it's been posted.

2. Add checklist items, as many as required, by clicking **Add another item**.

3. After you have added all checklist items, click or tap **Next**.

4. On **Action preferences** page, tap the boxes to select if you would want the users to:
        
   - Edit checklist items on app after the checklist has been sent on the group.

   - Add verification step. This can be required in cases where one of the group members is supposed to verify all completed checklist items before it is finally submitted.

### For Feedback or Announcement template

1. Do relevant customizations on Response view, Immersive view, and Chat view.
   
2. After you are done, click **Submit**. People can now see the detail page of the new Action; however, it’s still a draft.
    
3. To make the Action live, you need to publish it. Read more about [how to publish an Action](https://docs.microsoft.com/kaizala/actions/publish#steps-to-publish-an-action).
    
## Add Kaizala Action to a group

You can publish a Kaizala Action to one or more groups. When you do so, all the group members will see it in the **Discover** tab of the Kaizala mobile app. The Action only appears to members of the group you selected.
  
Actions will be visible directly in the Action Palette, if the group has one.
  
### To add a Kaizala Action to a group
  
1. Select a group from the **Groups** page.
    
2. Go to the **Action** tab. Click or tap **Add Action**.
    
3. Select the Action that you want to publish. Choose the user roles for which you would like the Action to be published.
    
4. Click or tap **Publish**.
    
### To remove a Kaizala Action from a group
  
1. Go to the **Groups** page, and select the relevant group.
    
2. Go to the **Action** tab. Find the Action that you want to remove.
    
3. Click or tap **More** ![Screenshot of More icon](media/more-icon.png), and then click or tap **Remove**.
    
## Activate or deactivate a Kaizala Action

If you deactivate a Kaizala Action, you can’t publish it to any new groups. The Action will continue to work for existing groups. An Action can be removed from a group without being reactivated. However, once you remove it, you can't re-publish it to the same group unless you reactivate it first.
  
## Remove Kaizala Action

To remove a Kaizala Action, go to the action list and select **Remove**. This will unpublish it from every group that originally received it.

## Change ownership for Kaizala Action

If there ever arises a need to change creator of an Action published within a tenant, the tenant admin can change ownership for that concerned Action.

1. Go to the **Extensions** > **Action** tab. Find the Action that you want to change ownership for.
    
2. Click or tap **Change Ownership**. This is available only for tenant admins.

3. Enter the user's Office 365 email ID to whom Action ownership must be changed to. The user must have previously logged on to Kaizala management portal and registered the phone number on both the Kaizala management portal and the Kaizala app.

Want to learn more? For more information on how to customize Actions for your organization's specific needs, contact [kaizalafeedback@microsoft.com](mailto:kaizalafeedback@microsoft.com).
  


---
title: Kaizala groups
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/11/2019
ms.audience: Admin
ms.topic: article
ms.service: Kaizala
ms.custom: Kaizala
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 858bead0-f99b-4215-83c6-b8812bbe3edd
description: Learn how to send instant messages, pictures, and documents to groups of Kaizala users.
---

# Kaizala groups

With Microsoft Kaizala, you can send instant messages, pictures, and documents to other Kaizala users. You can also create Kaizala Actions, like polls and surveys, and send them to an individual user or a group. You can create Kaizala groups and add users to them individually or in bulk. The groups can be created either both from the mobile app and the Kaizala management portal. However, bulk creation and management capabilities are only available through the Kaizala management portal.
  
For information about how to add users to Kaizala groups, see [Kaizala users](users.md). 
  
## Kaizala groups

There are two type of Kaizala groups:
  
![Kaizala organization groups view](media/c05e9bd2-05cb-4178-a44a-053e01db36bc.png)
  
- **Organization groups** - These groups belong to your organization and are created by using the Kaizala management portal. A group admin can link a Kaizala group, created through the mobile app, to an organization through the **Settings** page, or from the **Private Groups** tab. Kaizala group admins can only manage the groups for which they are admins. Conversely, Office 365 global admins have access and the ability to manage all organization groups, even those for which they aren't members.
    
- **Private groups** - These are the groups that aren't linked to any organization and are created by using the mobile app. Kaizala private groups can't be managed via the Kaizala management portal. Only Kaizala group members and Kaizala group admins can view or manage private groups. To be able to manage these groups, the Kaizala group admin has to link them to an organization group. 
    
## Create Kaizala groups

Follow the steps to create a new Kaizala group.
  
1. On the Kaizala management portal, from the left navigation bar, choose **Groups**. Select **Create Group**, enter the group name, and then click or tap **Create**. 
    
    ![Enter the name to create a new Kaizala group](media/f913453e-6a66-45bd-a51c-114ebf5be0d7.png)
  
2. On the **Users** tab, make sure the phone numbers are from the correct region. Enter a phone number in the text box for every user you want to add to this Kaizala group. You can also enter a list of comma-separated phone numbers. Finally, click or tap **Add users**. For example, to add three users, enter: **99885544, 99885543, 99885542**. 
    
    ![Add users to Kaizala groups](media/d71f75ba-24bb-443c-8cfe-f46a4c95d9b3.png)
  
Once you've added users to Kaizala groups, you can start sending surveys, polls, and other actions by using the mobile app. For more information, see [Kaizala Actions](actions.md). 
  
## Add multiple user phone numbers to a Kaizala group

If you want to add several users without using the comma separated list, you can do so using **Bulk upload**. There are two types of group mapping: 
  
- **User Group Mapping** - Use this CSV template file to enter the group name, users' phone numbers, and user type. You can add multiple groups at a time. The CSV template file contains relevant instructions and examples. Read the instructions carefully before filling and uploading the file. This file is mandatory and must be uploaded before proceeding to the next step. 
    
- **Parent Group Mapping** - Use this CSV template file to define the group hierarchy. Parent and child group name can be provided in the list to set up the groups to fit the required organization structure. This file is optional. The groups, for which the child group name doesn't exist in the template CSV file, are ignored in the parent group mapping file. 
    
   ![Bulk add users to Kaizala](media/8f4f5b63-ae6e-4aac-959f-a9022612a058.png)
  
You can add multiple groups and users at once from an Excel spreadsheet or other file saved in CSV format. [Add several users at the same time to Office 365 - Admin Help](https://support.office.com/article/1f5767ed-e717-4f24-969c-6ea9d412ca88#__toc316652088)
  
1. Click or tap **Groups**, and then click or tap **Bulk Upload Users**. 
    
2. On the **Bulk Upload Users** page, download the **User Group Mapping** CSV template file. Follow the steps to add your groups and user phone numbers. If you want to define group hierarchy, download and use the **Parent Group Mapping** CSV template file. Save the file to a location that you'll remember. 
    
3. On the **Bulk Upload Users** page, select the file you saved previously, and click **Upload**. 
    
    > [!NOTE]
    > If there are problems with the file, they are displayed in the panel. Click on the job time stamp link to see the detailed logs. 
  
4. If there aren't any problems with the file, click **Upload** to upload your groups and users info. 
    
## Add a Kaizala subgroup

1. On the Kaizala management portal, from the left navigation bar, choose **Groups**. Select a group you want to modify. 
2. Select **Sub-Groups** from the top navigation bar of the group. Then choose a group you want to link from the drop-down list and click or tap **Add Group**. 
    
    ![Add a Kaizala subgroup to a parent group](media/890765a2-9e2e-409f-88fa-0e478dfeb0c6.png)
    
    > [!NOTE]
    > The drop-down list remains empty if you don't have any available groups to link, so make sure you have an group available to link. Create one before you try to add it as a subgroup.
  
### Remove a Kaizala subgroup

1. On the Kaizala management portal, from the left navigation bar, choose **Groups**.
2. Choose a group from the drop-down list, and then click or tap **Remove**. 
    
    ![Add a Kaizala subgroup to a parent group](media/890765a2-9e2e-409f-88fa-0e478dfeb0c6.png)
    
## Add a connector

1. On the Kaizala management portal, from the left navigation bar, choose **Groups**. Select a group where you want to add a connector.
2. Select **Connectors** from the top navigation bar of the group. Choose a connector you want to link from the drop-down list, and then click or tap **Add connector**. 

## Add an action

1. On the Kaizala management portal, from the left navigation bar, choose **Groups**. Select a group where you want to add a connector.
2. Select **Actions** from the top navigation bar of the group. Choose an action you want to link from the drop-down list, and then click or tap **Add action**.
3. Select an action you want to add and check which roles can send this action.
4. Publish the action.    
  
## Export Kaizala group information

You can export all Kaizala group information to a CSV file.
  
1. On the Kaizala management portal, from the left navigation bar, choose **Groups**. Then choose **Bulk Upload Users**. 
    
2. Click or tap **Export Existing Groups**. 
    
You can then view groups and users information from an Excel spreadsheet or another app that can open CSV files. For more information, see [Add several users at the same time to Office 365 - Admin Help](https://support.office.com/article/1f5767ed-e717-4f24-969c-6ea9d412ca88#__toc316652088).
  
## Troubleshooting Kaizala groups

Read this section to help troubleshoot group issues that you're having in Kaizala.
  
### I am unable to add groups through the Bulk Upload Users feature

For each bulk upload activity, there is a unique job that gets created. From the Kaizala home page, go to **Groups** > **Bulk Upload Users** to view the history of bulk upload jobs. Find the job that you're having issues with, select the job name, and read the error log to find any errors. Fix the errors and then try to re-run the bulk upload. 
  
### I already created a group from the mobile app. How do I convert this to an organization group?

By default, when a group is created from the mobile app, it's created as a private group. You can convert it to an organization group. 

- Using the [Kaizala management portal](https://manage.kaiza.la):
  1. Select **Groups** in left navigation bar. 
  2. On the **Groups** page, select the **Private** tab. 
  3. Select a group, and then select **Map to Organization**.

- Using the Kaizala mobile app:
  1. Tap **Chats**, and then open the group.
  2. Tap the group name.
  3. Tap the **More** icon.
  4. Tap **Add to organization**.
  
### I am a Kaizala organization admin. I converted an organization group to a private group, which I am not a member of, and now I can't see it anymore. Where did it go?

This is by design. Kaizala organization admins can only see the organization groups. They can't see other private groups unless they are a member or administrator of those groups.
  


---
title: Kaizala groups
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/21/2019
audience: Admin
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.reviewer: rahul-mi
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

You can create Kaizala groups from the mobile app and the management portal. You can add members to groups one at a time, or through a bulk upload. Keep in mind, bulk uploads are only possible through the Kaizala management portal.
  
For information about how to add users to Kaizala groups, see [Kaizala users](users.md). 
  
## Kaizala groups

There are two types of Kaizala groups:
  
![Kaizala organization groups view.](media/c05e9bd2-05cb-4178-a44a-053e01db36bc.png)
  
- **Organization groups** belong to your organization and are created in the Kaizala management portal. A group admin can link a Kaizala group, created through the mobile app, to an organization through the **Settings** page, or from the **Private Groups** tab. As the name implies, public group admins only oversee specific public groups. Conversely, Office 365 global admins can manage all organization groups, even those for which they aren't members.
    
- **Private groups** aren't linked to any organization and are created in the mobile app. They can't be managed via the Kaizala management portal. Only Kaizala group members and admins can view or manage private groups. To manage these groups, the Kaizala group admin must link them to an organization group. 
    
## Create Kaizala groups

Follow these steps to create a new Kaizala group.
  
1. On the Kaizala management portal, from the left navigation bar, choose **Groups**. Select **Create Group**, enter the group name, and then click or tap **Create**. 
    
    ![Enter the name to create a new Kaizala group.](media/f913453e-6a66-45bd-a51c-114ebf5be0d7.png)
  
2. On the **Users** tab, make sure the phone numbers are from the correct region. Enter a phone number in the box for each user. You can also enter a list of comma-separated phone numbers. For example, to add three users, enter: **99885544, 99885543, 99885542**. Finally, click or tap **Add users**. 
    
    ![Add users to Kaizala groups.](media/d71f75ba-24bb-443c-8cfe-f46a4c95d9b3.png)
  
Once you've added users to Kaizala groups, you can start sending surveys, polls, and other actions in the mobile app. For more information, see [Kaizala Actions](actions.md). 
  
## Add multiple user phone numbers to a Kaizala group

**Bulk upload** lets you add several users at once without creating a comma-separated list. There are two types of group mapping:
  
- **User Group Mapping** - Use this CSV template to enter the group name, users' phone numbers and user type. You can add multiple groups at a time. The CSV template contains relevant instructions and examples. Read the instructions carefully before filling out the file. 
    
- **Parent Group Mapping** - Use this CSV template to define the group hierarchy. Parent and child group names can mirror your company’s structure. This file is optional. The groups, for which the child group name doesn't exist in the template, are ignored in the parent group mapping file. 
    
   ![Bulk add users to Kaizala.](media/8f4f5b63-ae6e-4aac-959f-a9022612a058.png)
  
You can add multiple groups and users at once from an Excel spreadsheet or other file saved in CSV format. For more information, see [Add several users at the same time to Office 365 - Admin Help](https://support.office.com/article/1f5767ed-e717-4f24-969c-6ea9d412ca88#__toc316652088).
  
1. Select **Groups**, and then select **Bulk Upload Users**. 
    
2. On the **Bulk Upload Users** page, download the **User Group Mapping** CSV template file. Follow the steps to add your groups and user phone numbers. If you want to define group hierarchy, download and use the **Parent Group Mapping** CSV template file. Save the file to a location that you'll remember. 
    
3. On the **Bulk Upload Users** page, select the file you saved previously, and select **Upload**. 
    
    > [!NOTE]
    > If there are problems with the file, they are displayed in the panel. Click on the job time stamp link to see the detailed logs. 
  
4. If there aren't any problems with the file, select **Upload** to upload your groups and users info. 
    
## Add a Kaizala subgroup

1. On the Kaizala management portal, from the left navigation bar, select **Groups**. Select a group you want to modify. 
2. Select **Sub-Groups** from the top navigation bar of the group. Then select a group you want to link from the drop-down list and select **Add Group**. 
    
    ![Add a Kaizala subgroup to a parent group.](media/890765a2-9e2e-409f-88fa-0e478dfeb0c6.png)
    
    > [!NOTE]
    > The drop-down list remains empty if you don't have any available groups to link, so make sure you have an group available to link. Create one before you try to add it as a subgroup.
  
### Remove a Kaizala subgroup

1. On the Kaizala management portal, from the left navigation bar, select **Groups**.
2. Choose a group from the drop-down list, and then choose **Remove**. 
    
    ![Add a Kaizala subgroup to a parent group.](media/890765a2-9e2e-409f-88fa-0e478dfeb0c6.png)
    
## Add a connector

1. On the Kaizala management portal, from the left navigation bar, select **Groups**. Select a group where you want to add a connector.
2. Select **Connectors** from the top navigation bar of the group. Choose a connector you want to link from the drop-down list, and then choose **Add connector**. 

## Add an action

1. On the Kaizala management portal, from the left navigation bar, select **Groups**. Select a group where you want to add a connector.
2. Select **Actions** from the top navigation bar of the group. Choose an action you want to link from the drop-down list, and then choose **Add action**.
3. Select an action you want to add and check which roles can send this action.
4. Publish the action.    
  
## Export Kaizala group information

You can export all Kaizala group information to a CSV file.
  
1. On the Kaizala management portal, from the left navigation bar, select **Groups**. Then select **Bulk Upload Users**. 
    
2. Select **Export Existing Groups**. 
    
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
  3. Tap **More** ![Screenshot of More icon.](media/more-icon.png).
  4. Tap **Add to organization**.
  
### I am a Kaizala organization admin. I converted an organization group to a private group, which I am not a member of, and now I can't see it anymore. Where did it go?

This is by design. Kaizala organization admins can only see the organization groups. They can't see other private groups unless they are a member or administrator of those groups.
  


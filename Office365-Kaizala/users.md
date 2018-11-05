---
title: Create Kaizala users
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 8/21/2018
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
ms.assetid: ff03275f-00a0-4fa6-a1cf-1e97a8e79a0a
description: Learn how to create Kaizala users such that they can send instant messages, pictures, and documents, or setup a new poll or survey.
---

# Create Kaizala users

Before you can send instant messages, pictures, and documents, or setup a new poll or survey, you'll have to create Kaizala users. You can add users individually or in bulk. For managing users in groups, check out [Kaizala groups](groups.md).
  
## View all users in an organization


On the Kaizala management portal, from the left navigation pane, choose **Users**. You'll see a list of all users that have possible access to your organization. This includes all users who were uploaded directly through the **Upload User** process, along with the members of organization groups, mapped to your organization. 
    
You can also select up to 4 columns that can be shown for each user, by choosing **More** \> **Select Columns**. 
  
![Add a Kaizala user's phone number](media/a2709c0c-0672-44a6-8918-388dab316b2a.png)
  
Kaizala organization admins can define and manage user attributes for an organization. They can add custom user attributes (employee ID, manager, etc) in the Kaizala Management Portal, which makes it easier for admins and other users to identify a user.
  
### Set up attributes for all users in the organization

- Click or tap **Users** \> **More**. Then select **Change Attributes** from the drop-down menu. 
    
- To add a new attribute, select **Add New**. Then choose from a range of pre-defined suggested attributes or add a new one. 
    
    ![Change attributes on Kaizala users, like name, phone number and job title.](media/661ce7d7-0ef7-4c40-a850-31fa44aed4ee.png)
  
  - You can decide whether it's optional or mandatory for users to enter data, for a list item selected from the suggested attributes.
    
  - For a custom attribute, you can enter the name of the attribute, select its type (string, number, Yes/No and date/time), and select whether it is mandatory or optional for users to enter data for it.
    
  - Once you've made changes to the attribute, click **+** to add it to the list, or **-** to remove it 
    
  - You can add multiple attributes at once.
    
- Once you've finalized the list of attributes, click **Save** to add the new changes to the organization's attribute list. 
    
## Add users in bulk to your organization


If you want to add several users without using the comma separated list, you can do so using **Bulk upload**. 
  
- Click **Users** \> **Add Users**. Then select **Import Multiple Users**. 
    
- On the **Import Multiple Users** page, download the CSV template. [Add several users at the same time to Office 365 - Admin Help](https://support.office.com/article/1f5767ed-e717-4f24-969c-6ea9d412ca88#__toc316652088).
    
- Follow the template to add your users and their phone numbers to Kaizala. Save the file in .csv format.
    
- Click **Select a File** and choose the file you saved above. Finally click **Upload**. 
    
    ![Bulk add users to Kaizala](media/8f4f5b63-ae6e-4aac-959f-a9022612a058.png)
  
- On the **Upload Users History** page, you can check the status of the uploaded file. Click **Refresh** to get the latest status. If the status is **Completed**, you can find the updated user list on the Users page. 
    
> [!NOTE]
> You can update info for an existing user by re-uploading the file with updated data for that user. 
  
## Find history of all user upload operations


- Click **Users** \> **Add users**. Then select **View Import History** from the drop-down. 
    
    ![Kaizala import history page](media/23cbc5fc-5b57-4ceb-ad9f-e165b52ebcbc.png)
  
- On the **View Import History** page, you can find a list of all user upload operations. Each list item has the following info: 
    
  - **File Name**
    
  - **Uploaded by**
    
  - **Date** - timestamp when the file was uploaded. 
    
  - **Status** of the uploaded file. This can be one of the following values : 
    
  - **Processing** - the file has been sent for processing and hasn't been uploaded yet. 
    
  - **Completed** - the file has either been successfully uploaded, or partially uploaded  due to some errors. 
    
  - **Failed** - the file hasn't been uploaded successfully. Download the error log file for the upload to check out any issues. 
    
  - **Download** - clicking the icon downloads the originally uploaded file. 
    
## Export users' data for your organization


- Click **Users** \> **Export Users**. Then select **Create New Request**. 
    
    ![Create a new request to export Kaizala users](media/2f444aab-c793-478a-8197-6d9c331bc47b.png)
  
- On the **Export History** page, you can check the status of the export request. Click **Refresh** to get the latest status. If the status is Completed, you can download the requested file by clicking on the download icon beside the specific request. 
    
## Find history of all export users operation


- Click **Users** \> **Export Users**. Then select **View Export History**. 
    
- On the **Export History** page, you can find a list of all user upload operations. Each list-item has following info 
    
    ![Kaizala export history page](media/9421c55c-52fc-4971-bb95-1bda020b353d.png)
  
  - File Name
    
  - Exported by
    
  - Date - timestamp when the file was uploaded.
    
  - **Status** of the exported file. This can be one of the following values : 
    
  - **Queued** - the request has been queued. 
    
  - **Completed** - the file has either been successfully exported, or partially exported due to some errors. 
    
  - **Failed** - the file wasn't exported successfully. Download the error log file for the upload to check out any issues. 
    
  - **Download** - Clicking the icon downloads the requested export file. 
    
## Find a detailed view of user's profile in the organization


To find a detailed view of a user's profile:
  
- Click **Users**. Then select a user from the user list for your organization. 
    
- Click on the phone number for that user to see a detailed view.
    
## Remove a user from a Kaizala group


- Click **Users**. Then select a user from the user list for your organization. 
    
- Click on the phone number for that user to see a detailed view.
    
- On the details page for the user, click **Delete**. Clicking **Delete** will remove the user from the organization. Once you delete a user, they get removed from all organizational groups on Kaizala. All data, including messages, Kaizala Actions and attachments for these groups will be deleted from their device. 
    
## Kaizala user roles


There are 3 different user roles in Kaizala. Here are the available roles and what people assigned to them can do.
  
|||
|:-----|:-----|
|**Role** <br/> |**What they do in Office 365** <br/> |
|**Kaizala Organization Administrator** <br/> |Kaizala organization admin is a user who can manage Kaizala for your organization. The built-in Office 365 role,  * global admin * is an equivalent of the Kaizala organization admin. Office 365 global admins will have access and ability to manage all organization groups, even those they aren't direct members or admins of.  <br/> |
|**Kaizala Group Administrator** <br/> |Kaizala Group administrator is a Kaizala Group member with special privileges. Unlike an organization admin, they have to be an admin of the group they are handling to have said privileges. Group admins can perform all the actions a organization admin can, but only on the groups they are explicitly made an admin of.  <br/> |
|**Member** <br/> |A Kaizala user with no special privileges. They can only take part in 1:1 and group communication and view attributes of their own groups and conversations. They can't add or remove other members from the group.  <br/> |
   
### What can the Kaizala user roles do?
<a name="__which_services_do"> </a>

|**Feature Access**|**Kaizala Org Admin**|**Group Admin**|**Member**|
|:-----|:-----|:-----|:-----|
|Add or Remove Users  <br/> |Manage all users of the organization  <br/> |Manage Users for groups with direct group admin privileges  <br/> |Not available  <br/> |
|View Groups  <br/> |All organization groups  <br/> |Own organization groups with admin role  <br/> |Own organization groups with member role  <br/> |
|View Groups  <br/> |All organization groups in the hierarchy  <br/> |All organization groups in the hierarchy  <br/> |All organization groups in the hierarchy  <br/> |
|Add or remove users from groups  <br/> |All organization groups  <br/> |Own groups with direct group admin privileges  <br/> |Not available  <br/> |
|View Connectors  <br/> |Self-created or all connecters in org  <br/> |Self-created or all connecters in org  <br/> |Self-created or all connecters in org  <br/> |
|Publish or Unpublish Connectors  <br/> |To all organization groups  <br/> |To own organization groups with admin role  <br/> |Not available  <br/> |
|View Actions  <br/> |Self-created or all Actions in org  <br/> |Self-created or all Actions in org  <br/> |Self-created or all Actions in org  <br/> |
|Publish or Unpublish Actions  <br/> |To all organization groups  <br/> |To own organization groups with admin role  <br/> |Not available  <br/> |
|View Reports  <br/> |Reports for all organization groups  <br/> |Reports for all organization groups with direct admin privileges  <br/> |Not available  <br/> |
|Manage groups to Organization mapping (in Settings page)  <br/> |All organization groups  <br/> |All groups with direct admin privileges  <br/> |Not available  <br/> |
   


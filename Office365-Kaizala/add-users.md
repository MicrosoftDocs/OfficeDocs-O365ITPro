---
title: Add users to the organization directory in Kaizala
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: Admin
ms.date: 05/01/2019
ms.topic: article
ms.service: Kaizala
ms.custom: Kaizala
ms.reviewer: nitinjms2
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to create or add users to the organization directory in Kaizala.
---

# Add users to the organization directory in Kaizala

Before you can send instant messages, pictures, and documents, or set up a new poll or survey, you'll have to create or add Kaizala users in your organization. You can add users individually or in bulk. For managing users in groups, see [Kaizala groups](groups.md).

Organization admins can create or add new users in organization directory networks. However, users when added by a group admin in any organization group also become a part of the organization directory.

Users can be added to the Employee network in any of the following ways:

- Users added by an organization admin as Employees, either in bulk or individually
- Users synced automatically from Azure Active Directory (Azure AD)
- Users who have signed in to their Kaizala mobile app using an Office 365 account

Similarly, users can be added to the Others network:

- Non-employee users added by a group admin to their organization groups
- Users added by an organization admin as Others, either in bulk or individually

However, tenant admins can always move a user between networks.
  
## Add users in bulk to your organization directory

If you want to add several users at once, you can do so using the **Import Users** option. 
  
1. Select **Directory** \. Open **Employee** or **Others** network tab.
2. Select **Import Users** 
3. On the **Import Users** dialog box, download the CSV template. See how to [add several users at the same time to Office 365](https://support.office.com/article/1f5767ed-e717-4f24-969c-6ea9d412ca88#__toc316652088).
4. Follow the template to add your users and their phone numbers to Kaizala. Save the file in .csv format.
5. Select **Select a File**, and choose the file you previously saved. Finally, select **Upload**. 
6. On the **Upload Users History** page, you can check the status of the uploaded file. Select **Refresh** to get the latest status. If the status is **Completed**, you can find the updated user list under the earlier selected network – Employee or Others. 
    
> [!NOTE]
> You can update info for an existing user by re-uploading the file with updated data for that user. 
  
## Find history of all user upload operations

1. Select **Directory**. Then select **View csv import history** from the drop-down list. 
2. On the **View Import History** page, you can find a list of all user upload operations. Each list item has the following information: 
   - **File Name**
   - **Uploaded by**
   - **Date** - timestamp when the file was uploaded. 
   - **Status** of the uploaded file. This can be one of the following values: 
     - **Processing** - the file has been sent for processing and hasn't been uploaded yet. 
     - **Completed** - the file has either been successfully uploaded, or partially uploaded  due to some errors. 
     - **Failed** - the file hasn't been uploaded successfully. Download the error log file for the upload to check out any issues. 
   - **Download** - click the icon to download the originally uploaded file. 
    
## Export users' data for your organization

1. Select **Directory** \> **Export Users**. Then select **Create New Request**. 
2. On the **Export History** page, you can check the status of the export request. Select **Refresh** to get the latest status. If the status is **Completed**, you can download the requested file by clicking the download icon beside the specific request. 
    
## Find history of all export users operation

1. Select **Directory** \> **Export Users**. Then select **View Export History**. 
2. On the **Export History** page, you can find a list of all user upload operations. Each list item has following information: 
   - **File Name**
   - **Exported by**
   - **Date** - timestamp when the file was uploaded.
   - **Status** of the exported file. This can be one of the following values: 
     - **Queued** - the request has been queued. 
     - **Completed** - the file has either been successfully exported, or partially exported due to some errors. 
     - **Failed** - the file wasn't exported successfully. Download the error log file for the upload to check out any issues. 
   - **Download** - Clicking the icon downloads the requested export file. 
    
## Find a detailed view of user's profile in the organization

To find a detailed view of a user's profile:
  
1. Select **Directory**. Then select a user from the user list for your organization. 
2. Select the user to see the user's details.
    

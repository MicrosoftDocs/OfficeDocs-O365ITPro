---
title: "Manage GDPR data subject requests in Yammer Enterprise"
f1.keywords:
- NOCSH
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 12/16/2018
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
ms.assetid: eae49f12-4661-4ba5-aa72-01248f0709bf
description: "Erase all information about a Yammer user to comply with GDPR data subject requests."
ROBOTS: NOINDEX; NOFOLLOW
---

# Manage GDPR data subject requests in Yammer Enterprise

As a verified admin, you can erase a user from Yammer to comply with a [General Data Protection Regulation (GDPR) data subject request](https://go.microsoft.com/fwlink/?linkid=874693). When you erase a user, personally identifying information about the user is removed. This does not remove the user's messages or files. You can review a user's messages and files in order to decide which ones to delete. Any content associated with the user that remains will be identified with an ID, but not with the user's name.

> [!IMPORTANT] 
> Before deleting data or erasing a user to honor a GDPR data subject request, your network data retention setting must be set to **Hard Delete**.

Choose the approach that makes sense for your situation, and **follow the steps in the order listed**. The order matters: once you erase a user you can no longer find their data to delete it.

|||
|:-----|:-----|
|**Approach**|**Steps**|
|Keep all messages and files created by the user.|Remove the user by using the **Erase the user** option. This removes the user from the home network and any external networks they belong to, but does not delete any of their messages or files.|
|Delete all messages created by the user and decide which files to delete|1. Do one per-user export of the user's data for the home network, and one for each external network they belong to.<br>2. Remove the user from each network by using the **Permanently remove this user, and remove their messages** option.<br>3. In the home network, use the **Erase the user** option.<br>4. Within 14 days, remove any files stored in Yammer in the home network as necessary, as well as any information not included in the per user export.*|
|Review files and messages created by the user and decide which to keep and which to delete|1. Do one per-user export of the user's data for the home network, and one for each external networks they belong to.<br>2. In the home network, use the **Erase this user** option.<br>3. Within 14 days, remove any files or messages as necessary from the home network, as well as any information not included in the per user export.*|

 \* If you prefer to have more than 14 days to review and delete files and messages, you can do this prior to erasing the user.

> [!IMPORTANT]
> Closing an AAD account does not delete the user and their information. To delete user information, you must go the Yammer admin center and complete the instructions provided below.

<a name="DataRetention"> </a>  
## Ensure your network data retention policy is set to Hard Delete before deleting a user or the user's data

Yammer has data retention settings that either soft-delete or hard-delete data when a user deletes a message or file. If this is set to **Soft Delete**, data a user has deleted continues to be stored. If the Yammer data retention setting is set to **Hard Delete**, the deleted information is no longer stored in Yammer
  
This has two implications for complying with GDPR:
  
- When you're doing the actual erase of the user and deleting their data, the network data retention policy must be set to **Hard Delete**.
    
- If your data retention policy has been set to **Soft Delete** in the past, data the user deleted will show up in the data export. In order to permanently delete the soft-deleted data, you must delete it while the network is set to **Hard Delete**. 
    
To see the data retention settings for your network, go to Yammer settings \> **Network Admin** \> **Content and Security** \> **Data Retention**.
  
If needed, change the settings to **Hard Delete**.
  
1. In Yammer settings, select **Network Admin**.
    
2. Under **Content and Security** select **Data Retention**.
    
3. Select **Hard Delete**.

<a name="ExportUser"> </a>
## Export data for one user

> [!NOTE]
> You must export user data for the home network, and for each external network the user is a member of. 
  
1. In the Yammer admin center, go to **Content and Security** \> **Export User Data**.
    
2. Type the user's name and select the user.
    
3. Click **Export**.
    
    Data is exported into a .zip file containing the following files.
    
|||
|:-----|:-----|
|**File** <br/> |**Contents** <br/> |
|**log.txt** <br/> |Summarizes the number of entries in each .csv file, and lists any errors that occur during the export.  <br/> |
|**request.txt** <br/> |Parameters use for the export.  <br/> |
|**Broadcast.csv** <br/>|For any live event video posted by the user, includes the network ID, group ID and name, title, description, links to the video, and additional information about the video. <br><br/>The video content is not included in the export. The video is saved in Microsoft Stream. For GDPR information for Stream, see [Office 365 Data Subject Requests for the GDPR, Stream](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#stream)<br/>|
|**Files.csv** <br/> | For any file added or modified by this user from Yammer, lists the Yammer ID, type of file, name, description, and path to the file, along with metadata including the group it was posted in. The storage_path column shows whether the file is stored in Yammer or SharePoint. <br><br/> Files.csv does not contain the actual files.<br><br>Files that are stored in Yammer are exported in their native format to the **Files** folder of the zip file. Files that are stored in SharePoint are not exported. <br><br>The file_ID and path columns in Files.csv can be used to identify the files in the **Files** folder or to go directly to the file in Yammer. For information about how to go directly to a specific file, see [Delete specific messages or files](gdpr-requests-in-yammer-enterprise.md#DeleteMessagesFiles).  <br><br> For files that are stored in SharePoint, use the download_url column to download the file. Or, you can use [Content Search in Office 365](https://docs.microsoft.com/office365/securitycompliance/content-search) to find files stored in SharePoint and created or modified by a specific user. <br><br>To delete a file, whether it is saved in Yammer or SharePoint, always delete it from Yammer. This erases the metadata in Yammer as well as the metadata and file in SharePoint. If you delete the file from SharePoint directly, the Yammer metadata still remains.|
|**Groups.csv** <br/> | For any group created or modified by the user, lists the Yammer group ID, name, description, privacy status, whether the group is internal or external, link to the group, creation date, and updated date. This file also includes the aggregated total number of polls the user voted on, and the polls the user created.  <br/> |
|**LikedMessages.csv** <br/> | For any message liked by the user, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, the ids for attachments, and creation and deletion information. A list of polls you created will also be provided. For announcements, includes the title of the announcement. <br/> |
|**Messages.csv** <br/> | For any message sent or modified by the user, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, the ids for attachments, and creation and deletion information. A list of polls you created will also be provided. For announcements, includes the title of the announcement. <br><br/> For information about how to go directly to a specific message in Yammer, see [Delete specific messages or files](gdpr-requests-in-yammer-enterprise.md#DeleteMessagesFiles).  <br/> |
|**BestReplyMessages.csv** <br/>| For any message marked as best reply by the user, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, the ids for attachments, and creation and deletion information. <br/>|
|**Topics.csv** <br/> |For any topic created by the user during the specified date range, lists the creation information and a link to the topic.  <br/> |
|**Files folder**.  <br/> | This folder contains files that are stored in Yammer and have been created or modified by the user during the specified time period. It does not contain Yammer files that are stored in SharePoint.<br><br>Files are in their native format and are named with their Yammer ID. For example, a PowerPoint presentation might be listed as 127815379.pptx.  <br><br/> For information about how to delete a specific file, see [Delete specific messages or files](gdpr-requests-in-yammer-enterprise.md#DeleteMessagesFiles).  <br/> |
   
4. When the user's account activity data is ready, you'll receive a Yammer inbox message with a link to the data. Click the link to open it.
    
Exported data does not contain bookmarked messages, group membership, followed or following users, followed topics, and the user's notification, application, and language settings. To find this data for an individual user, click the Yammer settings icon ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), click **People**, and click the name of the user whose data you want to view. This page shows the user's profile, conversations they've participated in, any files, images, and videos they have posted, along with their bookmarks, followed and following users, and followed topics.

### Troubleshoot data export

- If the .zip file is corrupted and can't be unzipped, try again. If this doesn't work, [contact Support](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- If the log.txt file shows export errors for one category of data, try again. If there are still errors, [contact Support](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

<a name="DeleteMessagesFiles"> </a> 
## Delete specific messages or files 

Use the Yammer file ID from the export to go directly to the file in Yammer and delete it. 

> [!IMPORTANT]
> For Yammer files stored in SharePoint, delete the files from Yammer in order to remove the Yammer metadata as well as the file.
  
**To locate and delete a specific message:**
    
1. Build the URL for the message. Use **https&#58;//www&#46;yammer&#46;com**/*network_name*/**#**/**Threads**/**show?threadId=** *thread_id*. For example, http&#58;//www&#46;yammer&#46;com/contosomkt&#46;onmicrosoft&#46;com/#/threads/show?threadID=135893.
  
2. In the message, click the **More** icon ![More icon (...)](../media/d9378a9a-fb0a-4313-96e5-bc6c9f1d5827.png), and then click **Delete**.
    
**To locate and delete a specific Yammer file stored in Yammer or SharePoint:**
    
  - Use the **Search** box in Yammer. For example, for a file named 12345678.pptx in the export, search for 1235678.pptx. In the search results, click **Go to File**, and then click **Delete this File**.
 
  - You can also build the URL for the file. Use **https&#58;//www&#46;yammer&#46;com**/*network_name*/**#**/**files**/*file_number*, for example https&#58;//www&#46;yammer&#46;com/contosomkt&#46;onmicrosoft&#46;com/#/files/12345678. On the Yammer page for the file, click **Delete this File**. 

<a name="OtherData"> </a>
## Find and delete user data not included in the per-user export

There is some user data that is not included in an export. To find this data for a user, go to Yammer settings ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png) \> **People**, and click the name of the user.
  
The following table shows how to change or delete this data if needed.
  
****

|**Type of data**|**How to change or delete it**|
|:-----|:-----|
|Bookmarked messages, group membership, followed or following users, and followed topics  <br/> |When you select the [Erase a user from your Yammer home network and external networks](gdpr-requests-in-yammer-enterprise.md#RemoveUser) to remove a user from Yammer, this information is deleted after the 14-day suspension period. <br><br> A user can change or delete this information. For steps, see [Tips for staying organized in Yammer](https://support.office.com/article/40ae9666-75c0-4254-a84c-d87a9542f380.aspx).  <br/> |
|User settings, including notification, application, and language settings  <br/> |When you select the [Erase a user from your Yammer home network and external networks](gdpr-requests-in-yammer-enterprise.md#RemoveUser) to remove a user from Yammer this information is deleted after the 14-day suspension period. As an admin, you can't change this information for a user.<br><br>A user can change their own settings. For steps, see [Change my Yammer profile and settings](https://support.office.com/article/a3aeca0e-de34-4897-9b59-de6516542851.aspx).  <br/> |
|User profile  <br/> | If the user has a Yammer identity, there are two options: <br><br/>- When you select the [Erase a user from your Yammer home network and external networks](gdpr-requests-in-yammer-enterprise.md#RemoveUser) to remove the user from Yammer, this information is deleted in Yammer after the 14-day suspension period.<br><br/>- The user has full control of their own profile, and can modify the values. For information, see [Edit the user's profile and settings (done by user)](gdpr-requests-in-yammer-enterprise.md#EditProfile).<br><br/> If the user has an Office 365 identity, the Yammer user profile is pulled automatically from Office 365, which gets the profile information from Azure Active Directory (AAD). Yammer users can temporarily change their profiles in Yammer, but these changes are overwritten when there is a change in AAD, so to permanently change or delete a user's profile, you must change or delete directory data in Office 365 and AAD. See [Manage Yammer users across their lifecycle from Office 365](https://support.office.com/article/365-6c4c8fff-6444-404a-bffc-f9da0bcc3039.aspx) and [Add or change profile information for a user in Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=871865).  <br/> |
   
 
<a name="EditProfile"> </a>
## Edit the user's profile and settings (done by user)

A user can edit their own profile. Administrators can't change the user profile or settings. 
  
- The user can click the Yammer settings icon ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then click **Edit Settings**.
    
- Select the tab for the change you want to make:
    
  - To change your profile, select **Profile**. 
    
  - To change your password, select **Password**. 
    
  - To edit your notifications, select **Networks**. 
    
  - To see your account activity, select **Account Activity**. 
    
  - To see what applications you've installed, select **My Applications**. 
    
  - To set preferences, select **Preferences**.
    
<a name="RemoveGroup"> </a>
## Remove a user from a group including an external group

1. In the group, click **Members**.
    
2. Click the Settings icon ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png) next to the user's name. 
    
3. Click **Remove from group**.
    
## Remove an external participant from a conversation
<a name="RemoveThread"> </a>

- In the Yammer conversation, click **Remove Participants**. 
    
<a name="RemoveUser"> </a>    
## Erase a user from your Yammer home network and external networks

> [!IMPORTANT]
> When you erase a user, there is a 14-day window for you to decide which files and messages to save or delete in the home network before the user-identifying data is completely erased. If you want to review and delete some or all of the user's messages and files, be sure to export user data and do the deletions before erasing the user's account, or within 14 days after selecting **Erase this user**. After the 14-day window, files and messages will continue to exist but will be marked as belonging to a former user.<br><br>After a user's account transitions from deactivated to removed, you can no longer associate user data with the user, which means you can no longer export and review their data. 
  
> [!IMPORTANT]
> If you want to review and delete messages and files in external groups, external threads, and networks that the user is a guest member in, follow the instructions in [Delete specific messages or Yammer files stored in Yammer or SharePoint](gdpr-requests-in-yammer-enterprise.md#DeleteMessagesFiles) *before*  erasing the user. As soon as you click **Erase this user**, you will no longer be able to associate the user with these messages and files.
  
> [!IMPORTANT]
> Removing a user from their home Yammer network will also remove them from all external networks. You must remove guest users separately in each external network they are a member of. 
  
When you erase a user, the following user data is deleted:
  
- Who the person is following, the connection to conversations and topics they were following, and the connection to users who were following them

- Bookmarks, language preferences, notification settings, and account activity

- Profile

- Group memberships

- The list of networks they were a member of

As an admin, you can erase a user from your home network and from any external networks they belong to. 
  
 **Remove a user (done by admin)**
  
1. In the Yammer admin center, go to **Users** \> **Remove Users**.

2. Enter an existing user's name. After you select the user, the options for removal are displayed.

    ![After you select a name, the remove user options are displayed.](../media/a48da79c-7f5f-479b-8b75-a3e67285c141.png)
  
      - If you want to keep all the user's files and messages, select **Erase this user**.

      - If you want to review the user's messages and files, and if you have already reviewed and deleted any messages or files in external groups, threads, or networks the user is a guest member in:

        1. Select **Erase this user. Wipe their name and personal information, but leave their messages. (Can't be undone after 14 days):** This deactivates the user for 14 days so that you can export user data and evaluate home network files and messages before the user is permanently deleted.

        This option marks the user as deactivated. The deactivated user is listed on the **Remove Users** page. Within 14 days, you can reactivate the user. 

        ![Deactivated user list](../media/162b43ed-acd1-4085-8073-b43845c30999.png)
  
        After 14 days, a message is sent to all the networks admins and verified admins informing them the user has been deleted.

        2. Click **Submit**.

        3. In the confirmation dialog, click **Yes, Permanently Delete Account**.

        4. Within the 14 days, follow the directions in [Delete specific messages or files](gdpr-requests-in-yammer-enterprise.md#DeleteMessagesFiles).

  - If you want to delete all a user's messages before you erase the user:

      1. Select **Permanently remove this user and remove their messages**, and then click **Submit**.
      2. When that completes, select **Erase this user**. This removes the user's name and activity data.
    
<a name="Reactivate"> </a>
## Reactivate a deactivated account after using Erase this user

When a user's account gets deactivated by using the **Erase this user** option, you have 14 days to reactivate the user. 
  
1. Go to the Yammer Admin center.
    
2. Click **Remove Users**. 
    
3. Go to the **Deactivated Users** section. This section will only be visible when there is at least one deactivated user account. 
    
4. Click **Reactivate** for each user you want to reactivated. 
    
    After 14 days, the user cannot be reactivated.
    
## Related articles

[Manage Yammer data compliance](manage-data-compliance.md)
  
[Manage GDPR data subject requests in Yammer Basic](gdpr-requests-in-yammer-basic.md)
  
[Export data from Yammer Enterprise](export-yammer-enterprise-data.md)


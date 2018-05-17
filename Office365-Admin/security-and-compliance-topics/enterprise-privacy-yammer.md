---
title: "Enterprise Privacy Yammer"
ms.author: v-irpast
author: v-irpast
ms.date: 4/25/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eae49f12-4661-4ba5-aa72-01248f0709bf
description: "As a verified admin, you can export and delete user data. First export all messages and files a user added to your Yammer enterprise network and review the content of those messages and files, and then use the identifying information provided in the export to go directly to each message or file in Yammer and delete it as needed."
---

# Enterprise Privacy: Yammer

As a verified admin, you can export and delete user data. First export all messages and files a user added to your Yammer enterprise network and review the content of those messages and files, and then use the identifying information provided in the export to go directly to each message or file in Yammer and delete it as needed.
  
You can also remove a user's account, which removes personal information about the user including their profile, but leaves any posts and messages.
  
> [!IMPORTANT]
> Export the user's messages and files prior to deleting the user's account, or within 14-days after selecting **Erase this user**. After a user's account transitions from deactivated to removed, you can no longer export their data. 
  
Yammer has data retention settings that either soft-delete or hard-delete data when a user deletes a message or file. If this is set to **Soft Delete**, data a user has deleted will be included in the export. If the Yammer data retention setting is set to **Hard Delete**, the deleted information is no longer stored in Yammer, so will not be included in the export. To see the settings for your network, go to Yammer settings > **Network Admin** > **Content and Security** > **Data Retention**.
  
## In this topic

- [Export data for one user](enterprise-privacy-yammer.md#ExportUser)
    
- [Find user data not included in the per-user export](enterprise-privacy-yammer.md#OtherData)
    
- [Delete specific messages or files](enterprise-privacy-yammer.md#DeleteMessagesFiles)
    
- [Remove a user from your Yammer home network and external networks](enterprise-privacy-yammer.md#RemoveUser)
    
- [Additional ways to delete data](enterprise-privacy-yammer.md#AdditionalDelete)
    
## Export data for one user
<a name="ExportUser"> </a>

> [!NOTE]
> You must export user data for each network the user is a member of. 
  
1. In the Yammer admin center, go to **Content and Security** > **Export user data**.
    
2. Type the user's name.
    
3. If you want to export files, select **Include attachments**.
    
4. Click **Export**.
    
    Data is exported into a .zip file.
    
  - **.txt files**
    
  - **request.txt** Contains the parameters for the export. 
    
  - **log.txt** Summarizes the number of entries in each .csv file. 
    
  - **.CSV files:** There is one .CSV file for each type of data: 
    
  - **Files.csv** For any file added or modified by this user, lists the Yammer ID, type of file, name, description, and path to the file in Yammer, along with metadata including the group it was posted in. 
    
    Files.csv does not contain the actual file. If you selected to include attachments in your export, files can be found in the **Files** folder of the zip file. The file ID in Files.csv can be used to identify the files in the **Files** folder or to go directly to the file in Yammer. 
    
  - **Groups.csv** For any group created or modified by the user, lists the Yammer group ID, name, description, privacy status, whether the group is internal or external, link to the group, creation date, and updated date. 
    
  - **Messages.csv** For any message sent or modified by the user, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, the ids for attachments, and creation and deletion information. 
    
  - **Topics.csv** For any topic created by the user during the specified date range, lists the creation information and a link to the topic. 
    
  - **Files folder:** This folder contain files that have been created or modified by the user during the specified time period. Files are in their native format and are named with their Yammer ID. 
    
5. When the user's account activity data is ready, you'll receive a Yammer inbox message with a link to the data. Click the link to open it.
    
## Find user data not included in the per-user export
<a name="OtherData"> </a>

There is some data that is not included in an export. To find this data for a user, go to Yammer settings ![Yammer settings icon](/Office365/Admin/media/9704ce70-56ce-43f7-96c6-f253b0413d40.png) > **People**, and click the name of the user.
  
The following table shows how to change or delete this data if needed.
  
****

|**Type of data**|**How to change or delete it**|
|:-----|:-----|
|Bookmarked messages, group membership, followed or following users, and followed topics  <br/> |When you select the [Remove a user from your Yammer home network and external networks](enterprise-privacy-yammer.md#RemoveUser) to remove a user from Yammer, this information is deleted after the 14-day suspension period. As an admin, you can't change this information for a user.  <br/> A user can change or delete this information. For steps, see [Tips for staying organized in Yammer](https://support.office.com/article/40ae9666-75c0-4254-a84c-d87a9542f380.aspx).  <br/> |
|User settings, including notification, application, and language settings  <br/> |When you select the [Remove a user from your Yammer home network and external networks](enterprise-privacy-yammer.md#RemoveUser) to remove a user from Yammer this information is deleted after the 14-day suspension period. As an admin, you can't change this information for a user.  <br/> A user can change their own settings. For steps, see [Change my Yammer profile and settings](https://support.office.com/article/a3aeca0e-de34-4897-9b59-de6516542851.aspx).  <br/> |
|User profile  <br/> | If the user has a Yammer identity, there are two options:  <br/>  When you select the [Remove a user from your Yammer home network and external networks](enterprise-privacy-yammer.md#RemoveUser) to remove the user from Yammer, this information is deleted in Yammer after the 14-day suspension period.  <br/>  The user has full control of their own profile, and can modify the values. For information, see [Change my Yammer profile and settings](https://support.office.com/article/a3aeca0e-de34-4897-9b59-de6516542851.aspx).  <br/>  If the user has an Office 365 identity, the Yammer user profile is pulled automatically from Office 365, which gets the profile information from Azure Active Directory (AAD). Yammer users can temporarily change their profiles in Yammer, but these changes are overwritten when there is a change in AAD, so to permanently change or delete a user's profile, you must change or delete directory data in Office 365 and AAD. See [Manage Yammer users across their lifecycle from Office 365](https://support.office.com/article/365-6c4c8fff-6444-404a-bffc-f9da0bcc3039.aspx) and [Add or change profile information for a user in Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=871865).  <br/> |
   
## Delete specific messages or files
<a name="DeleteMessagesFiles"> </a>

If you have the ID for a message or file, you can go to it in Yammer and delete it.
  
- To locate and delete a specific message in Yammer:
    
1. Build the URL for the message. Use https://www.yammer.com/<network_name>/#/Threads/show?threadId=<thread_id>. For example, https://www.yammer.com/contosomkt.onmicrosoft.com/#/Threads/show?threadId=1040647232.
    
2. In the message, click the **More** icon ![More icon (...)](/Office365/Admin/media/d9378a9a-fb0a-4313-96e5-bc6c9f1d5827.png), and then click **Delete**.
    
- To locate and delete a specific file in Yammer:
    
  - Use the **Search** box in Yammer. For example, for a file named 12345678.pptx in the export, search for 1235678.pptx. In the search results, click **Go to File** file, and then click **Delete this File**.
    
  - Or, build the URL for the file. Use https://www.yammer.com/<network_name>/#/files/<file_number>, for example https://www.yammer.com/contosomkt.onmicrosoft.com/#/files/12345678. On the Yammer page for the file, click **Delete this File**.
    
## Remove a user from your Yammer home network and external networks
<a name="RemoveUser"> </a>

> [!IMPORTANT]
> During the 14-day window, you can export the user's data to identify their files and messages, and then decide which ones to delete either by in-product deletion or by using a PowerShell script. > After this 14 days, you can no longer associate user data with this user, which means you can no longer export the user's data. 
  
> [!IMPORTANT]
> For regular users, delete the user from your home Yammer network. Guest users must be deleted separately in each external network they are a member of. 
  
1. In the Yammer admin center, go to **Users** > **Remove Users**.
    
2. Enter an existing user's name.
    
3. Select **Erase this user. Wipe their name and personal information, but leave their messages. (Can't be undone after 14 days):** This suspends the user for 14 days so that you can export user data and evaluate files and messages before the user is permanently deleted. 
    
    This option marks the user as deactivated. The deactivated user is listed on the **Remove Users** page. Within 14 days, you can reactivate the user. 
    
    ![Deactivated user list](/Office365/Admin/media/162b43ed-acd1-4085-8073-b43845c30999.png)
  
    After 14 days, a message is sent to all the networks admins and verified admins informing them the user has been deleted, and the following user data is deleted:
    
  - Who the person is following, the connection to conversations and topics they were following, and the connection to users who were following them
    
  - Bookmarks, language preferences, notification settings, and account activity
    
  - Profile
    
  - Group memberships
    
  - The list of networks they were a member of
    
4. Click **Submit**.
    
## Reactivating a suspended account
<a name="RemoveUser"> </a>

If a user's account gets suspended, you will have 14 days to reactivate the user. You can reactivate the user's account by following the steps below:
  
1. Go to the Yammer Admin center
  
2. Go to the Deactivated User section
  
3. Click **Reactivate** for each user you want to reactivated 
  
## Additional ways to delete data
<a name="AdditionalDelete"> </a>

A user can delete his or her own Yammer account. For more information, see [Change my Yammer profile and settings](https://support.office.com/article/a3aeca0e-de34-4897-9b59-de6516542851.aspx).
  
## See Also
<a name="AdditionalDelete"> </a>

[Manage Yammer data compliance](manage-yammer-data-compliance.md)
  
[Export data from Yammer Basic](export-data-from-yammer-basic.md)
  
[Manage Yammer Basic users](../user-topics/manage-yammer-basic-users.md)
  


---
title: "Export data from Yammer Enterprise"
ms.author: v-irpast
author: v-irpast
ms.date: 4/6/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: MOE150
ms.assetid: b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2
description: "Verified admins can export data from Yammer Enterprise."
---

# Export data from Yammer Enterprise

As a verified admin, you can export Yammer Enterprise data for all users in order to monitor usage and for discovery purposes.
  
> [!NOTE]
> Exported data can't be used for migrating content between Yammer networks. For migration information, see [Network migration: Consolidate multiple Yammer networks](../network-and-domain-topics/network-migration-consolidate-multiple-yammer-networks.md). To export all Yammer users, see [Audit Yammer users](../user-topics/audit-yammer-users-in-networks-connected-to-office-365.md). 
  
## Export Yammer data by date range and network

1. In the Yammer admin center, go to **Content and Security** > **Export data**.
    
2. Specify the data to include:
    ![Export page, showing export options](/Office365/Admin/media/9961176e-dcb5-453c-82a1-ff9d986877ad.png)
  
  - **Date range:** Only data in the specified date range will be included. 
    
  - **Attachments:** If not selected, you'll get a list of files. If selected, you also get a **Files** folder with all files in their native format. 
    
  - **External networks:** If not selected, you'll only get data from your home network. If selected, you'll get a separate folder for the data from each network. Each network is identified by its ID, and the full network names are listed in **Networks.csv**. 
    ![Each network has its own folder, labeled with the network ID](/Office365/Admin/media/5b8e96a8-b8bf-4467-b6d2-6a0bb9175d3c.png)
  
3. Click **Export**.
    
    Data is exported into a .zip file. If there is more than one network exported, a separate folder is created for each network. 
    
  - **.txt files**
    
  - **request.txt** Contains the parameters for the export. 
    
  - **log.txt** Summarizes the number of entries in each .csv file. 
    
  - **.CSV files:** There is one .csv file for each type of data: 
    
  - **Admins.csv** Lists the name, email, and type of all Yammer admins for each selected network. 
    
  - **Files.csv** For any file added or modified during the specified date range, lists the Yammer ID, type of file, name, description, and path to the file in Yammer, along with metadata including the group it was posted in. 
    
    Files.csv does not contain the actual file. If you selected to include attachments in your export, files can be found in the Files folder of the .zip file. Use the ID from Files.csv to identify a specific file in the Files folder.
    
  - **Groups.csv** For any group created or modified during the specified date range, lists the Yammer ID, name, description, privacy status, whether the group is internal or external, link to the group, who created the group, creation date, and updated date. 
    
  - **Messages.csv** For any message sent or modified during the specified date range, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, attachments, and creation and deletion information. 
    
  - **MessageThreadsInbound.csv** Includes IDs of external participants for inbound messages, which are helpful if you need to [Find external messaging participants](../external-messaging-topics/find-external-messaging-participants-in-a-yammer-network.md).
    
  - **MessageThreadsOutbound.csv** Includes IDs of external participants in outbound messages. 
    
  - **MessageVersions.csv** Includes IDs and modification information for messages that have been edited. 
    
  - **Networks.csv** Lists all networks included in the export. 
    
  - **Pages.csv** For any page created or modified during the specified date range, lists the IDs, dates, and owners of the page. 
    
  - **Topics.csv** For any topic created during the specified date range, lists the creation information and a link to the topic. 
    
  - **Users.csv** For any user who joined, or was deleted or suspended during the specified date range, lists email, job-title, location, department, a link to the user, and information about the users current state. 
    
  - **Files folder:** This folder contain files that have been created or modified during the specified time period. Files are in their native format but are named with their Yammer ID. 
    
The following types of data are not included in this export:
  
- Data available in the user's settings, including their profile, the networks they are members of, their account activity, applications, notifications, and language preferences, and their org chart.
    
- User's activity data.
    
- Bookmarked messages, group membership, followed or following users, or followed topics. To find this information for a user, click the user's name. 
    
To find this data for an individual user, click the Yammer settings icon ![Yammer settings icon](/Office365/Admin/media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), click **People**, and click the name of the user whose data you want to view. This page shows the user's profile, conversations they've participated in, any files, images, and videos they have posted, along with their bookmarks, followed and following users, and followed topics.
  
## Find and delete specific messages or files
<a name="DeleteMessagesFiles"> </a>

If you have the ID for a message or file, you can go directly to it in Yammer, and delete it if needed.
  
- To find and delete a specific message in Yammer: 
    
1. Build the URL for the message. Use https://www.yammer.com/<network_name>/#/Threads/show?threadId=<thread_id>. For example, https://www.yammer.com/contosomkt.onmicrosoft.com/#/Threads/show?threadId=1040647232.
    
2. In the message, click the **More** icon ![More icon (...)](/Office365/Admin/media/d9378a9a-fb0a-4313-96e5-bc6c9f1d5827.png), and then click **Delete**.
    
- To find and delete a specific file in Yammer:
    
  - Use the **Search** box in Yammer. For example, for a file named 12345678.pptx in the export, search for 1235678.pptx. In the search results, click **Go to File** file, and then click **Delete this File**.
    
  -  Or, build the URL for the file. Use https://www.yammer.com/< network_name>/#/files/<file_number>, for example https://www.yammer.com/contosomkt.onmicrosoft.com/#/files/12345678. On the Yammer page for the file, click **Delete this File**.
    
## Set up automatic data exports
<a name="DeleteMessagesFiles"> </a>

To set up automatic recurring exports, use the Yammer API. For information about the Data Export API, go to [/export](https://go.microsoft.com/fwlink/?LinkID=534735) on the Yammer Developer Center. 
  
## See also
<a name="DeleteMessagesFiles"> </a>

#### Other Resources

[View Group Insights in Yammer](https://support.office.com/article/73f9fa6d-d442-4f25-9194-d5317c9328ab.aspx)
  
[Office 365 Reports in the Admin Center - Yammer activity report](https://support.office.com/article/c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
  
[Audit Yammer user data](../user-topics/audit-yammer-users-in-networks-connected-to-office-365.md)
  
[Manage Yammer data compliance](manage-yammer-data-compliance.md)


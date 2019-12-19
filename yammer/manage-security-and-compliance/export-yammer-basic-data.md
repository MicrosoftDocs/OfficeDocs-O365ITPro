---
title: "Export data from Yammer Basic"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.assetid: 872612f0-780a-47ed-9daf-da5af065c5e6
description: "Users can export their own data in Yammer Basic."
---

# Export data from Yammer Basic

Each user can export their own data in Yammer Basic. It is not possible to export data for all users. 
  
1. Click the Yammer settings icon ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then click **Edit Settings**.
    
2. Click **Networks**. 
    
3. For each network you belong to, select **Download Data**. 
    
    ![On the networks page, to export data, use the Download Data link next to the network name](../media/b8b47324-6eaa-4f20-a211-e329b29c2b57.png)
  
    Data is exported into a .zip file. If you're a member of more than one network, a separate folder is created for each network. 
    
      - **.txt files**
        
      - **request.txt** Contains the parameters for the export. 
        
      - **log.txt** Summarizes the number of entries in each .csv file. 
        
      - **.CSV files:** There is one .csv file for each type of data: 
        
      - **Files.csv** For any file you added or modified during the specified date range, lists the Yammer ID, type of file, name, description, and path to the file in Yammer, along with metadata including the group it was posted in. 
        
        This data can be used to link directly to a Yammer file. Files.csv does not contain the actual file. If you selected to include attachments in your export, files can be found in the Files folder of the .zip file. Use the ID from Files.csv to identify a specific file in the Files folder.
        
      - **Groups.csv** For any group you created or modified during the specified date range, lists the Yammer ID, name, description, privacy status, whether the group is internal or external, link to the group, creation date, and updated date. 
        
       - **LikedMessages.csv** For any message you liked during the specified date range, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, the full text of the message, attachments, and creation and deletion information. For announcements, includes the title of the announcement.

        - **Messages.csv** For any message you sent or modified during the specified date range, lists the message ID, thread ID, group ID, group name, privacy status, sender ID, name and email, the full body of the message, the full text of the message, attachments, and creation and deletion information. For announcements, includes the title of the announcement.
        
      - **Networks.csv** Lists all networks included in the export. 
        
      - **Pages.csv** For any page you created or modified during the specified date range, lists the IDs, dates, and owners of the page. 
        
      - **Topics.csv** For any topic you created during the specified date range, lists the creation information and a link to the topic. 
        
      - **Files folder:** This folder contain files that have been created or modified by you during the specified time period. Files are in their native format but are named with their Yammer ID. 
        
        To locate an exported file in Yammer, use the **Search** box in Yammer. For example, for a file named 12345678.ppx in the export, search for 1235678.ppx. Or, go to **https&#58;//www&#46;yammer&#46;com**/*network_name*/**#**/**files**/*file_number*, for example:<br>
        https&#58;//www&#46;yammer&#46;com/contosomkt&#46;onmicrosoft&#46;com/#/files/12345678
    
4. When your account activity data is ready, you'll receive a Yammer inbox message with a link to the data. Click the link to open it.
    
## Troubleshoot data export

- If the .zip file is corrupted and can't be unzipped, try again. If this doesn't work, [contact Support](https://go.microsoft.com/fwlink/?linkid=523736).

- If the log.txt file shows export errors for one category of data, try again. If there are still errors, [contact Support](https://go.microsoft.com/fwlink/?linkid=523736).

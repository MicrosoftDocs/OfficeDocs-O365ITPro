---
title: "Manage Yammer data compliance"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 5/29/2018
audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.service: yammer
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 8c4651fa-12c2-4ced-b4ea-2200c0a630ed
description: "Monitor your Yammer data with these features: keyword monitoring, security settings, data export, data retention, and analytics."
---

# Manage Yammer data compliance

As a verified admin, you can keep your users' Yammer posts appropriate and meet security and compliance requirements. You can set up alerts for content that matches keywords, set data retention policies, and if needed, you can view private content. You can also [export data from Yammer](export-yammer-enterprise-data.md).

<a name="MonitorKeywords"> </a> 
## Monitor Keywords

Monitor sensitive content by specifying keywords such as banned words or employees' personal information. All messages in internal and external networks, including messages to and from external participants can be monitored.
  
 **Set person responsible for monitoring, editing, and deleting flagged posts**
  
1. In the Yammer admin center, go to **Content and security** > **Monitor Keywords**, and enter the person's email address in **Email Address**. This person should be a verified admin so they have permission to delete messages anywhere in Yammer.
    
2. When a post matches a keyword, the person listed in **Email Address** receives an email. They can then click a link in the email to review, edit, or delete the flagged post. 
    
 **Specify keywords and phrases to monitor**
  
1. In the Yammer admin center, go to **Content and Security** \> **Monitor Keywords**.
    
2. Enter the words and phrases you want to monitor, each on its own line.
    
    You can use regular expresssions to match patterns. For information on using regular expressions, see [Regular Expression Language](https://go.microsoft.com/fwlink/?LinkId=524073).
    
    Here are some examples of regular expressions commonly used for monitoring.
    
|**Purpose**|**Pattern**|**Matches**|
|:-----|:-----|:-----|
|Word boundary  <br/> |\bword\b  <br/> |\btheme\b matches "theme" but not "themes" or "them"  <br/> |
|Credit cards  <br/> |\b(?:\d[ ‐]\*?){13,16}\b  <br/> |1234 5678 90123  <br/> 1234 5678 9012 3456  <br/> 1234‐5678‐9012‐3456  <br/> |
|Social Security numbers  <br/> |\b\d{3}[ -]\d{2}[ -]\d{4}\b  <br/> |123 45 6789  <br/> 123‐45‐6789  <br/> |
Monitor group create|has created|Matthew has created the Easter Region Sales group.
   
   > [!TIP]
   > For a starting point for creating your keyword list, visit: http://www.bannedwordlist.com ([http://www.bannedwordlist.com](https://go.microsoft.com/fwlink/?LinkId=525065)). 
  
<a name="DataRetention"> </a>
## Data retention

You can control whether deleted messages and files stored in Yammer are retained and available in data exports.
  
 **Set whether to retain deleted messages and files stored in Yammer**
  
1. In the Yammer admin center, go to **Content and Security** \> **Data Retention**.
    
2. To prevent deleted data from being available in exported data, select **Hard Delete**. Or, to enable deleted data to appear in exported data, select **Soft Delete**.
    
    Retained data stored in Yammer can be permanently deleted by using the Yammer Developer API. To do this you export the data to identify the data that needs to be permanently deleted, and then write a custom PowerShell script to loop through the specific items to delete. For information, see the REST API section of  [Develop apps for Yammer](https://go.microsoft.com/fwlink/?linkid=874797). 

 **Set whether to retain deleted files stored in SharePoint**

For Yammer files saved in SharePoint, Office 365 data retention settings apply. For more information, see [Overview of retention policies](https://docs.microsoft.com/en-us/office365/securitycompliance/retention-policies).
    
<a name="ContentMode"> </a>
## Content mode

If as a verified admin, you have a legal reason to view private messages, you can select to see them. For more information, see [Monitor private content in Yammer](monitor-private-content.md)
  
## See also

[Overview of security and compliance in Yammer](security-and-compliance.md)

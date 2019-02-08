---
title: "Office 365 Reports in the Admin Center - Email activity"
ms.author: kwekua
author: kwekua
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_ReportsEmailActivity'
- 'O365E_ReportsEmailActivity'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: "Learn how to get an email activity report using the Office 365 Reports dashboard in the Office 365 admin center."
---

# Office 365 Reports in the Admin Center - Email activity

The new Office 365 **Reports** dashboard shows you the activity overview across the Office 365 products in your organization. It enables you to drill in to individual product level reports to give you more granular insight about the activities within each product. Check out [the Reports overview topic](activity-reports.md).
  
For example, you can get a high level view of email traffic within your organization from the Reports page, and then you can drill into the Email activity widget to understand the trends and per user level details of the email activity within your organization.
  
> [!NOTE]
> You must be a global administrator in Office 365 or an Exchange, SharePoint, Skype for Business administrator, or Reports reader to see Office 365 reports. 
  
## How to get to the email activity report

1. Go to the Office 365 admin center \> **Reports**
    
2. Click on the **Email Activity** widget on the **Reports** dashboard or select from the drop down. <br/>![Admin center reports - select Email activity](../media/e49cca5e-f84d-4f3d-bb34-973203bb2047.png)
  
## Interpret the email activity report

You can get a view into your user's email activity by looking at the **Activity** and **Users** charts. 
  
![Email activity report](../media/NewEmailActivity.jpg)
  
|||
|:-----|:-----|
|1.  <br/> |The **Email activity** report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days. However, if you click into a particular day in the report, the table (7) will show data for up to 28 days from the current date (not the date the report was generated).  <br/> |
|2.  <br/> |Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.  <br/> |
|3.  <br/> |The **Activity** chart enables you to understand the trend of the amount of email activity going on in your organization. You can understand the split of email send or read or received activities.  <br/> |
|4.  <br/> |The **Users** chart enables you to understand the trend of the amount of unique users who are generating the email activities. You can look at the trend of users performing send, reading or receiving email activities.  <br/> |
|5.  <br/> | On the **Activity** chart, the Y axis is the count of activity of the type email sent, email received and email read.  <br/>  On the **Users** activity chart, the Y axis is the user's performing activity of the type email sent, email received and email read.  <br/>  The X axis on both charts is the selected date range for this specific report.  <br/> |
|6.  <br/> |You can filter the series you see on the chart by clicking on an item in the legend. For example, on the **Activity** chart, click or tap **Sent**, **Received** or **Read** ![Filter charts for specific related data](../media/a3a9cb3d-b8b1-4c6a-9f6f-18aebf74c3a0.png) to see only the info related to each one. Changing this selection doesn't change the info in the grid table.  <br/> |
|7.  <br/> | The table shows you a breakdown of the email activities at the per-user level. This shows all users that have an Exchange product assigned to them and their email activities. <br/> <br/>  **User name** is the email address of the user.  <br/> **Display Name** is the full name if the user.  <br/> **Deleted** refers to the user whose current state is deleted, but was active during some part of the reporting period of the report.  <br/> **Deleted date** is the date the user was deleted.  <br/> **Last activity date** refers to the last time the user performed a read or send email activity.  <br/> **Send actions** is the number of times an email send action was recorded for the user.  <br/> **Receive actions** is the number of times an email received action was recorded for the user.  <br/> **Read actions** is the number of times an email read action was recorded for the user.  <br/> **Product assigned** is the Office 365 products that are assigned to this user.  <br/>  If your organization's policies prevents you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **How do I hide user level details?** section in the [Activity Reports in the Office 365 Admin Center Preview](activity-reports.md).  <br/> |
|8.  <br/> |You can also export the report data into an Excel .csv file, by clicking or tapping the **Export** ![Office 365 reports](../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) link. This exports data of all users and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 users, you can sort and filter within the table in the report itself. If you have more than 2000 users, in order to filter and sort, you will need to export the data.  <br/> |
|||
   


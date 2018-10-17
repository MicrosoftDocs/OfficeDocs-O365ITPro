---
title: "Office 365 Reports in the Admin Center - Email apps usage"
ms.author: kwekua
author: kwekua
manager: scotv

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365E_ReportsEmailClients
O365M_ReportsEmailClients'
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: "Learn how to get Email apps usage report to know about email apps connecting to Exchange Online and the Outlook version users are using."
---

# Office 365 Reports in the Admin Center - Email apps usage

The new Office 365 **Reports** dashboard shows you the activity overview across the Office 365 products in your organization. It enables you to drill in to individual product level reports to give you more granular insight about the activities within each product. Check out [the Reports overview topic](activity-reports.md). In the Office 365 email apps usage report, you can see how many email apps are connecting to Exchange Online. You can also see the version information of Outlook apps that users are using, which will allow you to follow up with those who are using unsupported versions to install supported versions of Outlook.
  
> [!NOTE]
> You must be a global administrator in Office 365 or an Exchange, SharePoint, Skype for Business administrator, or reports reader to see Office 365 reports. 
  
## How to get to the Office 365 email apps report

1. Go to the Office 365 admin center \> **Reports** \> **Usage**.
    
2. From the Select a report drop down, select **Email app usage**.<br/>![Email clients used dropdown](../media/a15932dd-8beb-4c2e-9bc2-99972984cadf.png)
  
## Interpret the Office 365 email apps report

You can get a view into Office 365 email apps activity by looking at the **Users** and **Clients** charts. 
  
![Email clients used](../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |The **Office 365 email apps used** report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days. However, if you click into a particular day in the report, the table (7) will show data for up to 28 days from the current date (not the date the report was generated).  <br/> |
|2.  <br/> |Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.  <br/> |
|3.  <br/> |The **Users** view shows you the number of unique users that connected to Exchange Online using any email app.  <br/> |
|4.  <br/> |The **Apps** view shows you the number of unique users by app over the selected time period.  <br/> |
|5.  <br/> |The **Versions** view shows you the number of unique users for each version of Outlook in Wondows.  <br/> |
|6.  <br/> | On the **Users** chart, the Y axis is the total count of unique users that connected to an app on any day of the reporting period.  <br/>  On the **Users** chart, the X axis is number of unique users that used the app for that reporting period.  <br/>  On the **Apps** chart, the Y axis is the total count of unique users who used a specific app during the reporting period.  <br/>  On the **Apps** chart, the X axis is the list of apps in your organization.  <br/>  On the **Versions** chart, the Y axis is the total count of unique users using a specific version of Outlook desktop. If the report can't resolve the version number of Outlook, the quantity will show as Undetermined.  <br/>  On the **Versions** chart, the X axis is the list of apps in your organization.  <br/> |
|7.  <br/> |You can filter the series you see on the chart by clicking on an item in the legend. For example, on the **Users** chart, click or tap **Mac mail** or **Outlook** ![List of email clients. Click on the email client to get more reporting data on that client.](../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) to see only the info related to each one. Changing this selection doesn't change the info in the grid table. Mac mail, Outlook for Mac, Outlook mobile, Outlook desktop, and Outlook on the web are examples of email apps you may have in your organization.  <br/> |
|8.  <br/> | You might not see all the items in the list below in the columns until you add them.<br/> **User name** is the name of the email app's owner.  <br/> **Last Activity Date** is the latest date the app connected to Exchange Online.  <br/> **Mac mail**, **Mac Outlook** and **Outlook**, **Outlook mobile** and **Outlook on the web** are examples of email apps you may have in your organization.  <br/>  If your organization's policies prevents you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **How do I hide user level details?** section in the [Activity Reports in the Office 365 Admin Center Preview](activity-reports.md).  <br/> |
|9.  <br/> |Click or tap **Manage columns** to add or remove columns from the report.  <br/> ![office 365 email apps usage report - choose columns](../media/c17b2a5c-db41-474a-8334-0e5a621b2f16.png)|
|10.  <br/> |You can also export the report data into an Excel .csv file, by clicking or tapping the **Export** ![Office 365 reports](../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) link. This exports data of all users and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 users, you can sort and filter within the table in the report itself. If you have more than 2000 users, in order to filter and sort, you will need to export the data.  <br/> |
|||
   


---
title: "Office 365 Reports in the Admin Center - Yammer activity report"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_ReportsYammerActivity'
- 'O365E_ReportsYammerActivity'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_Yammer
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a
description: "Get the Yammer Activity report and know more about the number of users using Yammer to post, like, or read a message."
---

# Office 365 Reports in the Admin Center - Yammer activity report

As an Office 365 admin, the **Reports** dashboard shows you data on the usage of the Office 365 products within your organization. Check out [Activity Reports in the Office 365 Admin Center](activity-reports.md). With the **Yammer Activity report**, you can understand the level of engagement of your organization with Yammer by looking at the number of unique users using Yammer to post, like or read a message and the amount of activity generated across the organization. 
  
> [!NOTE]
> You must be a global administrator in Office 365 or an Exchange, SharePoint, Skype for Business administrator, or reports reader to see Office 365 reports. 
  
## How to get to the Yammer activity report

1. Go to the Office 365 admin center \> **Reports** \> **Usage**. 
    
2. Select the **Yammer Activity** widget on the **Reports** dashboard. 
    
    ![Yammer Activity reports widget in the Office 365 Reports dashboard](../media/3edb83ae-c1bd-4d23-bc8f-930e54c54c15.png)
  
    Or, select **Yammer activity** from the **Select a report** dropdown. 
    
    ![Select a report menu in the Office 365 Reports dashboard](../media/8101651b-948f-4c81-a5d8-eb310242cb62.JPG)
  
## Interpret the Yammer activity report

You can get a view into your user's Yammer activity by looking at the Activity and Users charts.
  
![Yammer Activity report showing a graph of activity and table of user details for that activity.](../media/92e8b2c6-166a-4154-9824-3fb6bbedf0db.JPG)
  
The activity report contains the following information.
  
- Use the day tabs to view the **Yammer activity** report trends over the last 7 days, 30 days, 90 days, or 180 days. However, if you click into a particular day in the report, the table will show data for up to 28 days from the current date (not the date the report was generated). 
    
- Each report has a date for when the report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.
    
- You can view the **Activity** chart to understand the trend of the amount of Yammer activity going on in your organization. You can understand the split of messages posted, read, or liked. 
    
    ![Activity view in the Office 365 Yammer activity report](../media/76983516-2c5f-43a1-a5e3-c414e9f17638.JPG)
  
  - On the **Activity** chart, the Y axis is the count of activity of the messages posted, read, or liked. 
    
- You can view the **User** chart to understand the trend of the amount of unique users who are generating the Yammer activities. You can look at the trend of users posting, reading, or liking Yammer messages. 
    
    ![Users view in the Office 365 Yammer activity report](../media/b1098162-7b79-430f-bfe4-9d3957d56885.JPG)
  
  - On the **Users** activity chart, the Y axis is the user posting, reading, or liking Yammer messages. 
    
  - The X axis on both charts is the selected date range for this specific report.
    
- You can filter the series you see on the chart by clicking on an item in the legend. For example, on the **Activity** chart, click or tap **Posted**, **Read**, or **Liked** to see only the info related to each one. 
    
    ![Posted, Read, and Liked options for the Yammer Activity report](../media/8b832afc-415c-409b-816f-cb02b7a71e69.png)
  
    Changing this selection doesn't change the info in the grid table.
    
- The table under the graph shows you a breakdown of the Yammer activities at the per-user level.
    
    You can use the menu to filter and sort the data.
    
    ![Screenshot of menu options for Yammer reports](../media/9d32240c-f1ff-400b-9c4e-a21b48651530.JPG)
  
    You can also add and remove columns. The available columns are:
    
  - **User name** is the email address of the user. You can display the actual email address or make this field anonymous. 
    
    This grid shows users who logged into Yammer using the Office 365 account or who logged into the network using single sign-on.
    
  - **Display name** is the full name of the user. You can display the actual email address or make this field anonymous. 
    
  - **User state** is one of three values: Activated, Deleted, or Suspended. 
    
    These reports show data for active, suspended, and deleted users. They do not reflect pending users, because pending users cannot post, read, or like a message.
    
  - **State change date (UTC)** is the date on which the user's state was changed in Yammer. 
    
  - **Last activity date (UTC)** refers to the last date that the user posted, read, or liked a message. 
    
  - **Posted** is the number of messages the user posted during the time period you specified. 
    
  - **Read** is the number of conversations that the user read during the time period you specified. 
    
  - **Liked** is the number of messages that the user liked during the time period you specified. 
    
  - **Product assigned** is the Office 365 products that are assigned to this user. 
    
    If your organization's policies prevents you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **How do I hide user level details?** section in the [Activity Reports in the Office 365 Admin Center](activity-reports.md).
    
- You can also export the report data into an Excel .csv file, by clicking or tapping the **Export**![Office 365 reports - export your data to an Excel file](../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) link. This exports data of all users and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 users, you can sort and filter within the table in the report itself. If you have more than 2000 users, in order to filter and sort, you will need to export the data. 
    
## What data is in these reports?

- **All clients** These reports aggregate data across all clients, including using Yammer in a browser or on an iOS or Android app. 
    
- **No external network data** External network data is not included in these reports. 
    
- **Activated networks** These reports show data for the Yammer network that is part of your Office 365 subscription. The chart aggregates usage of all users who logged into the Yammer network, irrespective of whether they used Office 365 or Yammer to log in. 
    


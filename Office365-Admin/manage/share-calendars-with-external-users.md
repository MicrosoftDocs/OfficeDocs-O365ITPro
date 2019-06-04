---
title: "Share calendars with external users"
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_ShareCal'
- 'O365M_ShareCal'
- 'O365E_ShareCal'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_SPO
- SharePoint_Online
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: "Learn how to let your users share their calendars with external users for meetings and appointments. "
---

# Share calendars with external users

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end

It's often necessary to schedule meetings with people outside your organization. To simplify the process of finding mutually agreeable meeting times, Office 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Office 365 environment.
  
Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant. Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization. People inside the organization can view the shared calendar side-by-side with their own. People outside the organization will be sent a URL that they can use to view the calendar. Users decide when to share, how much to share, and when to keep their calendars private.
  
> [!NOTE]
> If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/en-us/library/dd638083%28v=exchg.150%29.aspx) for more information. 
  
## Enable calendar sharing using the Microsoft 365 admin center

1. Sign in to Office 365 with your work or school account. 
    
2. Select the app launcher icon ![App launcher icon in Office 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) and choose **Admin**.
    
3. Navigate to **Settings** \> **Services &amp; add-ins**.
  
4. On the **Services &amp; add-ins** page, click **Calendar**.
  
5. On the **Calendar** page that opens, do one of the following: 
    
  - For **Let your users share their calendars with external users who have Office 365 or Exchange**, move the slider to **On** to enable calendar sharing. 
    
  - For **Let your users share their calendars with external users who have Office 365 or Exchange**, move the slider to **Off** to disable calendar sharing. 
    
6. If you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation, select the **Allow anonymous users to access calendars with an email invitation** check box. Then choose what type of calendar information to make available to users. You can allow all information, or limit it. These choices specify the amount of information that your users can show on a case-by-case basis. Select one of the following:
    
  - **Calendar free/busy information with time only**
    
  - **Calendar free/busy information with time, subject and location**
    
  - **All calendar appointment information**
    
## Invite people to access calendars

Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions. 
  


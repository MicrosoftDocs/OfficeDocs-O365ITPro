---
title: "Enable Microsoft 365 usage analytics"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: "Learn how to start collecting data for your tenant by using the Office 365 content pack in Power BI."
---

# Enable Microsoft 365 usage analytics

Microsoft 365 usage analytics is also available for Office 365 US Government Community.
  
## Steps to enable Microsoft 365 usage analytics

To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the content pack in Power BI.
  
### Get Power BI

If you don't already have Power BI, you can [sign up for the free Power BI service](https://go.microsoft.com/fwlink/p/?linkid=845347). Select **Get started free** to get the free version. 
  
![Select Get started free to get Power Bi](../media/7916b7ac-c1c8-40c0-b076-9a96ef5e0eb7.png)
  
You can also expand **Products** to buy a version of Power BI. 
  
### Enable the content pack

To enable the content pack, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**. 
  
See [About admin roles](../add-users/about-admin-roles.md) for more information. 
  
1. In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page. 
    
2. On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.
    
3. On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**. 
  
This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant. The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete. 
    
### Initiate the content pack

To initiate the content pack, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**. 
  
1. Copy the tenant Id and select **Go to Power BI**.
    
2. When you get to Power BI, sign in. Select **Get Data**, then under **More ways to create your own content**, select **Service Content Packs**. 
    
    ![Under Content Pack Library, in Services, select Get.](../media/3c73b515-beec-474c-b9fb-2b0a1145f689.png)
  
3. In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.
    
4. On the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id you copied in step (1) \> **Next**.
    
5. On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**. If you choose any other authentication method, the connection to the content pack will fail.
    
    ![Choose oAuth2 as authentication method](../media/634ff4bd-06db-4633-b9c2-6258b09a1d2e.PNG)
  
6. Once the content pack is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web. The initial loading of the dashboard will take between 2 to 30 minutes.
  
Tenant level aggregates will be available in all reports. **User-level details will only become available after the 1st or 15th day of the calendar month after opting in**. This will impact the following reports - which will show tiles without data - until that point: 
    
    See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports. 
    
  - Exchange - User activity
    
  - Skype for Business - User activity
    
  - Teams - User activity
    
  - Yammer - User activity
    
  - OneDrive - User activity
    
  - SharePoint - User activity
    
  - Adoption by department
    
  - Adoption by product
    
  - Adoption by region
    
  - Yammer usage
    
## Make the collected data anonymous

To make the data that is collected for all reports anonymous, you have to be a global administrator. This will hide identifiable information such as user, group and site names in reports and in the content pack .
  
1. In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services &amp; add-ins</a> page.
    
2. Select **Reports**, and then choose to **Display anonymous identifiers**. This setting gets applied both to the usage reports as well as to the content pack.
  
3. Select **Save changes**.
    


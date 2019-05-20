---
title: "Office 365 Reports in the admin center - SharePoint site usage"
ms.author: kaarins
author: kaarins
manager: pamgreen
audience: Admin
ms.topic: overview
f1_keywords:
- 'O365M_ReportsSPSiteUsage'
- 'O365E_ReportsSPSiteUsage'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_UI_Elements
- SharePoint_Online
- Strat_SP_admin
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- Strat_SP_admin
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: "Get the SharePoint site usage report to know how many files users store in SharePoint sites, how many are actively used, and the total storage consumed. "
---

# Office 365 Reports in the admin center - SharePoint site usage

As an Office 365 admin, the **Reports** dashboard shows you the activity overview across various products in your organization. It enables you to drill in to get more granular insight about the activities specific to each product. For example, you can get a high level view of the value you are getting from SharePoint in terms of the total number of files that users store in SharePoint sites, how many files are actively being used, and the storage consumed across all these sites. Then, you can drill into the SharePoint site usage report to understand the trends and per site level details for all sites. 
  
> [!NOTE]
> You must be a global administrator in Office 365 or an Exchange, SharePoint, Skype for Business administrator, or reports reader to see reports. 
  
## How to get to the SharePoint site usage report

1. In the Microsoft 365 admin center, select **Reports** from the left menu or click on the **Reports** widget. <br/>![Check out new activity reports](../media/2554deff-b840-4aa5-b2b2-83683996fedc.png)
  
2. Use the **Select a report** drop-drop at the top left and select **SharePoint site usage**. <br/>![Select a report](../media/fb7bb8ea-eeb7-48c9-b739-601f41ddee16.png)
  
## Interpreting the SharePoint site usage report

![SharePoint Site Usage Report](../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |The **SharePoint Site usage** report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days. However, if you click into a particular day in the report, the table (7) will show data for up to 28 days from the current date (not the date the report was generated).  <br/> |
|2.  <br/> |Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.  <br/> NOTE: At times there may be unpredictable delays in data collection and processing which may delay report generation. The displayed report date is always reflective of the current date for which the system has processed report data. We strive to keep these within 24-48 hours from the time of activity.           |
|3.  <br/> |The **Sites** chart shows the number of total and active sites. Any site in which users had viewed, modified, uploaded, downloaded, shared, or synced a file or viewed a page within the reporting period.  <br/> |
|4.  <br/> |The **Files** chart shows the total number of files across all sites and the number of active files. The number of total files includes both user files and system files. A file is considered active if it has been saved, synced, modified or shared within the specific time period.  <br/> NOTE: A file activity can occur multiple times for a single file, but will count only as one active file. For example, you can save and sync the same file multiple times over a specified time period, but it will count only as one single active file and one single synced file in the data.           |
|5.  <br/> |The **Storage** chart shows the trend of storage allocated and consumed during the reporting period.  <br/> |
|6.  <br/> |The **Pages** chart shows the number of pages viewed across all sites.  <br/> |
|7.  <br/> |You can filter charts you see by clicking on an item in the legend. For example, on the **Files** chart, click or tap **Files** or **Active Files**. On the **Sites** chart, you can click or tap **Total sites** or **Active sites**. On the **Storage** chart, you can click **Storage allocated** or **Storage consumed.** Changing this selection doesn't change the information in the grid table.  <br/> |
|8.  <br/> | The table shows you a breakdown of the activities at the per-site level.  <br/> ![Column options for usage report](../media/sharepointsite-usage.png)           <br/> **Site URL** is the full URL of the site.  <br/> **Deleted** is the deletion status of the site. It takes at least 7 days for sites to be marked as deleted.  <br/> **Site owner** is the username of the primary owner of the site.  <br/>**Site owner principal name** is the email address of the owner of the site.  <br/> **Last activity date (UTC)** refers to the date of the last time file activity was detected or a page was viewed on the site.  <br/> **Files** is the number of files on the site.  <br/> **Active Files** is the number of active files on the site. A file is considered active if it has been saved, synced, modified or shared within the specific time period.  <br/> NOTE: A file activity can occur multiple times for a single file, but will count only as one active file. For example, you can save and sync the same file multiple times over a specified time period, but it will count only as one single active file and one single synced file in the data. >  If files were removed during the specified time period for the report, the number of active files shown in the report may be larger than the current number of files on the site.<br/>**Storage used (MB)** is the amount of storage currently being used on the site.  <br/> **Storage allocated (MB)** is the maximum amount of storage allocated for the site.  <br/> **Page views** is the number of times pages were viewed on the site.  <br/> **Pages visited** is the number of unique pages that were visited on the site.  <br/> **Root Web Template** is the template used for creating the site.  <br/> NOTE: If you wan to filter the data by different site types, then export the data and use the Root Web Template column. <br/>If your organization's policies prevent you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **How do I hide user level details?** section in the [Activity Reports in the Microsoft 365 admin center](activity-reports.md).  <br/> |
|9.  <br/> |Click or tap  **Manage columns**  ![Manage Columns](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) to add or remove columns from the report.  <br/> |
|10.  <br/> |You can also export the report data into an Excel .csv file, by clicking or tapping the **Export** ![Export](../media/4dc548cc-8061-48d5-9240-6793affca43a.png) link. This exports data for all sites and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 sites, you can sort and filter within the table in the report itself. If you have more than 2000 sites, in order to filter and sort, you will need to export the data.  <br/> > [!NOTE]> When the data is exported to an Excel file, note that the date the content report was generated in reflected in the file in the **Data as of** column.      <br/>   |
|||
   


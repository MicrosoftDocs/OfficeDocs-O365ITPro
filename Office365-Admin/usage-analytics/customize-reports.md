---
title: "Customize the reports in Microsoft 365 usage analytics"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv

ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: "Learn to customize reports in the browser and Power BI Desktop."
---

# Customize the reports in Microsoft 365 usage analytics

Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Office 365. The dashboard is just a starting point to interact with the usage data. The reports can be customized for more personalized insights.
  
You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.
  
## Customizing reports in the browser

The following two examples show how to modify an existing visual and how to create a new visual.
  
### Modify an existing visual

This example shows how to modify the **Adoption overview** report. 
  
1. At the top of the dashboard, in the **Understanding adoption** area, point to the Adoption overview card, and then click it. 
    
2. In the top navigation, click **Edit report**.
    
    ![Click Edit report on the top right navigation](../media/a1ac1826-7f3a-420b-9b25-aeb84e3eaf27.png)
  
3. At the top right, click **Duplicate this page**.
    
    ![Choose Duplicate this page](../media/0a9b6ff7-7f15-4764-ae71-7c9adaf7ecbe.png)
  
4. At the top right of the report, click the title bar of the **Adoption overview** graph. 
    
5. In the **Visualizations** area to the right, for the **FirstTimeUsers** column, click the ** X ** to the right to remove it. 
    
6. At the top right of the **Adoption overview** visual, click the Pin visual icon and in the dialog, click **Pin** \> **Existing dashboard**.
    
7. At the top of the browser, in the breadcrumb, click the **Office 365 Adoption** link to return to the dashboard. 
    
8. If prompted to save changes to the report, click **Don't save**.
    
9. Scroll to the bottom of the dashboard to locate the visual you just saved.
    
10. Drag it to the top of the dashboard.
    
11. You can optionally delete the original **Adoption overview** card, by clicking the ellipsis on the top right of the card, and then choosing **Delete**.
    
### Create a new visual

The following example shows how to create a new visual to track new Yammer users on monthly basis.
  
1. In the **Communication** area of the dashboard, click the **Yammer - Any Active Users** card and in the top navigation click **Edit report**.
    
2. At the bottom, click the **new page** icon ![The add page button in Power BI](../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) to create a new page. 
    
3. In the **Visualizations** area to the right, click the **Stacked column chart** (top row, second from left). 
    
    ![Choose Stacked bar chart in Visualizations in Power BI](../media/c87cc597-a615-4b92-b20f-8bb355eb741d.png)
  
4. Click the bottom right of that visualization and drag to make it larger.
    
5. In the ** Fields ** area to the right, expand the **Calendar** table. 
    
6. Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area. 
    
7. In the **Fields** area to the right, expand the **TenantProductUsage** table. 
    
8. Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading. 
    
    ![Screenshot that shows the customized visualizations values](../media/bcc3599e-ee9e-4ac6-968a-5a7858b4a4f0.png)
  
9. Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading. 
    
10. In the **Filter Type** area that appears, select the **Yammer** check box. 
    
11. Just below the list of visualizations, click the **Format** icon. ![Format icon in Power BI Visualizaions](../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)
  
12. Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.
    
13. Change the **Text Size** value to **12**.
    
14. At the top right of the visual, click the Pin visual icon and in the dialog, click **Pin** \> **Existing dashboard**.
    
15. At the top of the browser, in the breadcrumb, click the **Office 365 Adoption** link to return to the dashboard. 
    
16. Scroll to the bottom of the dashboard to locate the visual you just saved.
    
## Customizing the reports in Power BI Desktop

For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free. 
  
### Use the reporting APIs

You can start by connecting directly to the ODATA reporting APIs from Office 365 that power these reports.
  
1. Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.
    
2. In the URL window enter https://reports.office.com/pbi/v1.0/\<tenantid\>
    
    > [!NOTE]
    > The reporting APIs are in preview and are subject to change until they go into production. 
  
![OData feed URL for Power BI desktop](../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. Enter your Office 365 (organization or school) admin credentials to authenticate to Office 365 when prompted.
    
    See [FAQ](usage-analytics.md#bkmk_faq) for more information about who is allowed to access the Office 365 Adoption content pack reports. 
    
4. Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.
    
    Select all and click on **Load**.
    
    This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.
    
    ![ODATA values available in the reporting API](../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### Use the Microsoft 365 usage analytics template

You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.
  
You can download the Power BI template file from the Microsoft download center [here](https://download.microsoft.com/download/1/7/0/170A5A35-9E0D-478D-828C-4CA2D9A9F092/Microsoft 365 Usage Analytics.pbit). After you have downloaded the Power BI template file follow these steps to get started:
  
1. Open the pbit file.
    
2. Enter your tenant id value in the dialog.
    
    ![Enter your tenant ID to open the pbit file](../media/6b700a33-1701-404e-8f46-ddb1d6c8d9ca.png)
  
3. Enter your admin credentials to authenticate to Office 365 when prompted.
    
    See [FAQ](usage-analytics.md#bkmk_faq) for more information about who is allowed to access the Microsoft 365 usage analytics reports. 
    
    Once authorized, the data will be refreshed in the Power BI file.
    
    Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.
    
4. Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details. 
    
## Related Topics

[Microsoft 365 usage analytics](usage-analytics.md)
  
[Enable Microsoft 365 usage analytics](enable-usage-analytics.md)
  
[Navigating and utilizing the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md)
  
[Active user in Office 365 usage reports](active-user-in-usage-reports.md)
  
[Troubleshooting Microsoft 365 usage analytics](usage-analytics-errors.md)
  
[Microsoft 365 usage analytics data model](usage-analytics-data-model.md)
  


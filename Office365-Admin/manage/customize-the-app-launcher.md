---
title: "Add custom tiles to the app launcher"
ms.author: twerner
author: twernermsft
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_CustomTiles'
- 'O365M_CustomTiles'
- 'O365E_CustomTiles'
- 'CustomTiles'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: "Create quick links to your email, documents, apps, SharePoint sites, external sites, and other resources by adding custom tiles to the app launcher. "
---

# Add custom tiles to the app launcher

In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/en-us/office/office365/howto/connect-your-app-to-o365-app-launcher).
  
You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site. 
  
![Office 365 app launcher](../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## Add a custom tile to the app launcher

1. [Where to sign in to Office 365 for business](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account. 
    
2. Select the app launcher icon ![App launcher](../media/9f0af1b1-86e6-43d0-8cee-90132efd4131.png) and choose **Admin**. 
    
3. In the Office 365 admin center, search for **tiles** or use the left navigation pane by choosing **Settings** \> **Organization profile** \> **Add custom tiles for your organization**.<br/>![Add custom tiles for your organization](../media/a0d86f6f-0283-4df1-8d81-4c9e0efdc91d.png)<br/>NOTE: If you don't see the Custom tiles link, verify you have an Exchange Online mailbox assigned to you and you've successfully signed into your mailbox. Both are required for this feature. 
  
4. Choose ![Add](../media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png) **Add a custom tile**. <br/>![Add a custom tile details](../media/e9361337-3009-41c7-89a9-fd642e8c5f07.png)
  
5. Enter a **Tile name** for the new tile. The name will appear in the tile. 
    
6. Enter a **URL** for the tile. This is the location where you want your users to go when they click the tile on the app launcher. Use HTTPS in the URL.<br/>TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here. The URL of your default team site looks like this: `https://<company_name>.sharepoint.com` 
  
7. Enter a **Description** for the tile. You see this when you select the tile on the My apps page and choose App details. 
    
8. Enter an **Image URL** for the tile. The image appears on the My apps page and app launcher.<br/>TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.
  
9. Choose **Save** to create the custom tile. 
    
Your custom tile now appears in the app launcher on the **All** tab for you and your users. 
  
## Promote the tile to the Home tab

1. Select the app launcher icon ![App launcher](../media/9f0af1b1-86e6-43d0-8cee-90132efd4131.png) and select the **Home** tab. 
    
2. Locate the new tile for your app, select the ellipsis, and choose **Pin to home**. <br/>![Pin tile to app launcher](../media/211492b3-5b66-4e83-8c70-c4c3604831d8.png)
  
    > [!NOTE]
    > If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365. 
  
> [!IMPORTANT]
> Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher. 
  
## Edit or delete a custom tile

1. In the Office 365 admin center, search for **tiles** or use the left navigation pane by choosing **Settings** \> **Organization profile** \> **Add custom tiles for your organization** and click ![Edit](../media/41e7590d-1114-490c-9b0d-33fd602a7bb9.png)<br/>![Add custom tiles for your organization](../media/a0d86f6f-0283-4df1-8d81-4c9e0efdc91d.png)
  
2. Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).
    
3. Click **Update** \> **Close**. 
    
To delete a custom tile, from the **Custom tiles** window, select the tile, click **Remove tile** and then click **Delete**. 
  
![Edit or delete a custom tile](../media/cc8a36f9-00d8-48ed-b520-4b3540bfea1d.png)
  
## What's next?

In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).
  


---
title: "Back up data before switching O365 for business plans"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.date: 7/6/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: "Backup Outlook, OneDrive, Yammer, and SharePoint content before switching Office 365 subscriptions or if a user leaves the organization."
---

# Back up data before switching O365 for business plans

If a user will be switched to another subscription that has fewer data-related services or a user leaves the organization, a copy of their data that's stored in Office 365 can be downloaded before they are switched to the new subscription.
  
## Save a copy of Outlook information
<a name="BKMK_Outlook"> </a>

If users have Outlook, they can [export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) before their plan is switched. 
  
After the switch to the new plan is finished, users can [Import email, contacts, and calendar from an Outlook .pst file](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx).
  
## Save files stored in OneDrive for Business
<a name="BKMK_OneDrive"> </a>

Before being switched to a different subscription, users can [download files and folders from OneDrive or SharePoint](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05.aspx) to a different location, such as a folder on their computer's hard drive, or a file share on the organization's network. 
  
## Save Yammer information
<a name="BKMK_Yammer"> </a>

Admins can export all messages, notes, files, topics, users, and groups to a .zip file. For more information, see [Export data](https://support.office.com/article/8c4651fa-12c2-4ced-b4ea-2200c0a630ed.aspx#ExportData). Developers can use the [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) to do this, as well. 
  
## How to save SharePoint information
<a name="BKMK_SharePoint"> </a>

If a user is switched from a subscription that has SharePoint Online to one that doesn't have it, the **SharePoint** tile will no longer appear in their Office 365 menu. 
  
However, as long as the new subscription is within the same organization as the one they are switched from, users will still be able to access the SharePoint team site. They can view and update notebooks, documents, tasks, and calendars by using the direct URL to the team site.
  
> [!TIP]
> We recommend that users go to the team site before their subscription is switched and save the URL as a favorite or bookmark in their browser. 
  
By default, the URL of the team website is in this form:
  
```
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

where  _\<orgDomain\>_ is the organization's URL. 
  
For example, if the domain of the organization is contoso.onmicrosoft.com, then the direct URL to the team site would be https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Of course, users can also download SharePoint Online documents from the SharePoint team site to their local computer or to another location at any time.
  
## Still need help? Contact support.
<a name="BKMK_ContactSupport"> </a>

As an admin for Office 365 for business, you get free access to our knowledgeable support agents for pre-sales, account, and billing support, as well as for help resolving technical issues. You can also [contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322) on behalf of Office 365 users in your organization. 
  
[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## See also
<a name="BKMK_ContactSupport"> </a>

[Billing in Office 365 for business - Admin Help](subscriptions-and-billing.md)


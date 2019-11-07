---
title: "Share your Office 365 sites with external users"
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_ShareSites'
- 'O365E_ShareSites'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: "Learn how to share your Office 365 sites and documents with external users. "
---

# Share your Office 365 sites with external users

People who need to see or work with your site content but don't have user accounts for your SharePoint Online or Office 365 environment are called "external users." You can share your sites and documents with external users either globally, that is, for all sites in the tenant, or for each site collection individually. 
  
After sharing is enabled for the tenant and individual site collections, site collection admins can extend invitations to specific users. See [Share SharePoint files or folders in Office 365](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c.aspx) for instructions. 
  
## Deciding how to share your content

When considering if and how you want to share content externally, think about the following:
  
- To whom do you want to grant access to content on your Team site and any sub-sites, and what do you want them to be able to do?
    
- To whom in your organization do you want to grant permission to share content externally? 
    
- Is there content you want to ensure is never available to be viewed by people external to your organization?
    
The answers to these questions will help you plan your strategy for content sharing.
  
|**Try this:**|**If you need to…**|
|:-----|:-----|
|Share a site. If you want to share a site but you also want to restrict external users from gaining access to some of your organization's internal content, consider creating a subsite with unique permissions that you use exclusively for the purpose of external sharing.  <br/> |Provide someone outside your organization with ongoing access to information and content on a site. They need the ability to perform like a full user of your site and create, edit, and view content.  <br/> |
|Share a document and require sign-in.  <br/> |Provide one or several people outside your organization with secure access to a specific document for review or collaboration, but these people do not require ongoing access to other content on your internal site.  <br/> |
|Share a document, but don't require sign-in.  <br/> |Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback. These people do not require ongoing access to content on your internal site.  <br/> |
   
> [!IMPORTANT]
> When you deactivate external sharing, any external users who had access to the site at the time the feature was deactivated are denied access to the site and no future invitations can be sent. If the feature is reactivated with external user names in the SharePoint permissions groups, then those users will automatically be able to access the site again. To permanently prevent a user from accessing the SharePoint site, you can remove them from the list of external users. 

If external sharing is turned off globally, any shared guest links will also stop working. If the feature is later reactivated, these links will resume working. 
  
## Enable external sharing for all SharePoint sites in the Microsoft 365 admin center

The ability to invite external users to SharePoint sites is enabled by default, so site owners and site collection administrators can share team sites and sub-sites with external users at any time. 
  
1. In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.
  
2. On the page that opens, choose whether users can share guest links with existing external users, new and existing external users, or anyone, including anonymous users. 
    
6. Select **Save**.
    
## Fine tune settings for individual sites

When you enable sharing on SharePoint sites, sharing is enabled for all sites in the tenant. But from the admin center you can fine tune the sharing settings to disallow sharing on those sites where more stringent control is necessary or to revoke individual user access to specific sites. 
  
> [!NOTE]
>  If external sharing is turned off for the entire SharePoint Online environment, you will not be able to turn it on for specific site collections. 
  
On the sites page of the sharing settings (admin center) you can see a list of all the site collections currently active in your tenant along with the sharing settings for each site collection. 
  
## Edit the sharing settings of a particular site collection in the admin center

1. In the admin center, go to the **Resources** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2099222" target="_blank">Sites</a> page.
  
2. Select the external sharing status next to the desired site collection.
  
3. In the sharing dialog box, next to **Sharing status**, select **Edit**.
  
4. Next to **Let users share SharePoint Online and OneDrive for Business content with people outside the organization**, slide the slider to **On** to turn on external sharing.
  
5. Choose whether users can share with existing guests, new and existing guests, or anyone.
    
6. Select **Save**.
    
## Revoke site access for individual users in the admin center

1. In the admin center, go to the **Resources** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2099222" target="_blank">Sites</a> page.

2. Select the sharing status next to the desired site collection.
    
3. In the sharing dialog box, next to **External users**, select **Edit**.
    
4. Under **Remove external members**, search for the members to remove.
  
5. Next to the member's name, select **Remove**.
    
6. Select **Save** to confirm the deletion. Note that once you save, the user(s) will no longer have access to the selected site. Any guest links that were provided will be disabled.
    


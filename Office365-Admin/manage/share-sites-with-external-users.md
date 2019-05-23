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
- Adm_SPO
- Adm_UI_Elements
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
  
1. Sign in to Office 365 with your work or school account. 
    
2. Go to the [Microsoft 365 admin center](../admin-overview/about-the-admin-center.md).<br/>![Office 365 app launcher with the Admin app](../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
3. In the Microsoft 365 admin center, type external in the search box on the Home page, and choose **Sites external sharing**.<br/>![Type external sharing in the Search box](../media/ff7ae7ef-91e3-4ed0-bb39-d2a7cf75b4db.png)
  
4. Next to **Let people outside your organization access your sites**, slide the slider to **On** to turn on external sharing.<br/>![External Sharing dialog box](../media/848bff81-63a3-464c-a9f4-135c04800c7a.png)
  
5. To **Allow your users to send guest links for access to your organization's sites and documents**, slide the slider for this option to **On**.<br/>![External sharing turned on in the admin center](../media/4f5dd6a4-f1b6-44e8-b553-eba6231c2b8d.png)<br/>Change the slider to **Off** if you want to require users to sign in using a username and password. (For more information about user IDs for work or school accounts, see [What is my user ID and why do I need it?](https://support.office.com/article/37da662b-5da6-4b56-a091-2731b2ecc8b4.aspx))
    
6. Choose **Save**.
    
## Fine tune settings for individual sites

When you enable sharing on SharePoint sites, sharing is enabled for all sites in the tenant. But from the Microsoft 365 admin center you can fine tune the sharing settings to disallow sharing on those sites where more stringent control is necessary or to revoke individual user access to specific sites. 
  
> [!NOTE]
>  If external sharing is turned off for the entire SharePoint Online environment, you will not be able to turn it on for specific site collections. 
  
On the sites page of the sharing settings (Microsoft 365 admin center) you can see a list of all the site collections currently active in your tenant along with the sharing settings for each site collection. 
  
## Edit the sharing settings of a particular site collection in the Microsoft 365 admin center

1. Sign in to Office 365 with your work or school account. 
    
2. Go to the [Microsoft 365 admin center](../admin-overview/about-the-admin-center.md).

3. Navigate to **Resources** \> **Sites**.<br/>![Resources menu in Microsoft 365 admin center](../media/8bd379ed-d3d1-4061-9127-159d7b142c22.png)
  
4. Select the sharing status ( **Share links and invitations** or **Not allowed**) next to the desired site collection.<br/>![SharePoint site collections with sharing status](../media/d48dc3b2-f26b-4e76-b32d-4c7ff9a0b2ae.png)
  
5. In the sharing dialog box, next to **Sharing status**, click **Edit**.<br/>![Sharing status dialog box for a site collection](../media/a357ff16-6e62-434a-9ae5-7e9e60348c5e.png)
  
6. Next to **Let people outside your organization access your sites**, slide the slider to **On** to turn on external sharing.<br/>![External Sharing dialog box](../media/848bff81-63a3-464c-a9f4-135c04800c7a.png)
  
7. To **Allow your users to send guest links for access to your organization's sites and documents**, slide the slider for this option to **On**.<br/>![External sharing turned on in the admin center](../media/4f5dd6a4-f1b6-44e8-b553-eba6231c2b8d.png)<br/>Change the slider to **Off** if you want to require users to sign in using a username and password. (For more information about user IDs for work or school accounts, see [What is my user ID and why do I need it?](https://support.office.com/article/37da662b-5da6-4b56-a091-2731b2ecc8b4.aspx))
    
8. Click **Save**.
    
## Revoke site access for individual users in the Microsoft 365 admin center

1. If you're not already in the External Sharing Sites screen, do steps 1-4 shown in [Edit the sharing settings of a particular site collection in the Microsoft 365 admin center](#edit-the-sharing-settings-of-a-particular-site-collection-in-the-office-365-admin-center). 
    
2. Select the sharing status ( **Share links and invitations** or **Not allowed**) next to the desired site collection.
    
3. In the sharing dialog box, next to **External members**, click **Edit**.
    
4. Under **Remove external members**, search for the members to remove.<br/>![Remove external members from a site collection](../media/89b166c7-c337-4430-9009-19db89270b77.png)
  
5. Next to the member's name, select **Remove**.
    
6. Click **Save** to confirm the deletion. Note that once you **Save**, the user(s) will no longer have access to the selected site. Any guest links that were provided will be disabled.
    


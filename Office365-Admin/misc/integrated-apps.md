---
title: "Turning Integrated Apps on or off"
ms.author: kwekua
author: kwekua
manager: scotv

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_ServiceSettings_IntegratedApps_FL512425'
- 'O365P_integratedAppsLearMoreLink'
- 'O365M_integratedAppsLearMoreLink'
- 'O365E_integratedAppsLearMoreLink'
- 'IntegratedApplicationsInfo'
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: "Learn about Integrated Apps and how to turn them on to allow third-party apps to access users' Office 365 information."
---

# Turning Integrated Apps on or off

When Integrated Apps is turned on, users in your organization can allow third-party apps to access their Office 365 information. For example, when someone uses a third-party app, that app might ask for permission to access their calendar and to edit files that are in a OneDrive folder.
  
## Turning Integrated Apps on or off
<a name="__toc379982114"> </a>

Here's how to turn Integrated Apps on or off.
  
1. Log on to Office 365 using your work or school account.
    
2. Go to the Office 365 admin center, and from the left navigation bar, click **Settings** \> **Services &amp; add-ins**
    
3. On the **Integrated apps** page, use the toggle to turn Integrated Apps on or off. 
    
## More info on Integrated Apps
<a name="__toc379982114"> </a>

An integrated app can be created from within your own organization, or it can come from another Office 365 organization or a third-party. 
  
When Integrated Apps is turned on and an app is used, the app asks for permission to set the level of access it needs when it accesses the user's information. A user can give access only to apps they own that access their Office 365 information. They can't give an app access to any other user's information.
  
There are two kinds of permissions that are used when using Integrated Apps in Office 365: user permissions and admin permissions. For example, when your organization is enabled for Integrated Apps and a user uses a third-party app, the app might ask for the user's permission to read their user profile details, edit or delete their files, read items contained in site collections, and send email as that user.
  
![Integrated Apps User Permissions](../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)
  
If an admin registers an app for all users in their organization, he or she is asked for permission to let that app access information and resources in their organization. After this, when other users in the organization use that app, they won't be asked for permission. When an admin registers an app, that admin must make sure that they trust that app's publisher. For details on registering an app, see [Adding, Updating and Removing an Application](http://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).
  
![Integrated Apps Admin Permissions](../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)
  
If Integrated Apps is turned off, apps that have already been installed and have permission to access information won't be uninstalled, and the permissions won't be removed. Even though Integrated Apps is turned off, admins can still register apps to make them available to their users and allow those apps access to the users' information. For details on removing a registered application and it's permissions, see [Adding, Updating and Removing an Application](http://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).
  


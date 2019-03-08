---
title: "Remove a domain from Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_Remove_RemoveDomain'
- 'O365M_Setup_RemoveDomain'
- 'O365E_Setup_RemoveDomain'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365_Domain_Core
- Adm_O365_Setup
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365_FullSet
- Adm_O365_Setup
- Adm_O365_Top
- Core_O365Admin_Migration
- MiniMaven
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: "Learn how to remove an old domain from Office 365 and move users and groups to another domain. "
---

# Remove a domain from Office 365

Contributors: [![Peter Baumgartner](../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/?linkid=847121)
  
 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Are you removing your domain because you want to add it to a different Office 365 subscription plan? Or do you just want to cancel your subscription? You can [change your plan or subscription](../subscriptions-and-billing/switch-to-a-different-plan.md) or [cancel your subscription](../subscriptions-and-billing/cancel-your-subscription.md).
  
### Step 1: Move users to another domain


::: moniker range="o365-worldwide"

Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. Choose **Users** \> **Active Users**.
    
3. Select the boxes next to the names of the users who you want to move.
    
4. In the **Bulk actions** pane, choose **Edit domains**.
    
5. In the **Edit domains** pane, choose a different domain. 
    
6. Choose **Set as primary**, then choose **Save**.
    
7. You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.
    
    For example, if you're logged in as  *dave@contoso.onmicrosoft.com*  : 
    
1. Go to **Users** \> **Active Users**, select your account from the list, and then choose **Edit** in the **Username** row in the left pane. 
    
2. Choosea different domain:  *contoso.com* 
    
3. Choose **Set as primary**, choose **Save**, and then **Close**.
    
4. At the top, choose your account name, then choose **Sign Out**.
    
5. Sign in with the new domain and your same password:  *dave@contoso.com* 
    
You can also use PowerShell to move users to another domain. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
### Step 2: Move groups to another domain


::: moniker range="o365-worldwide"

Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. Choose **Groups** \> **Groups**. 
    
3. Select the box for any group or distribution list associated with the domain that you want to remove.
    
4. In the right pane, next to the group name, choose **Edit**.
    
5. Under **Group Id**, use the drop-down to choose another domain.
    
6. Choose **Save**, then **Close**. Repeat this process for any groups or distribution lists associated with the domain that you want to remove.
    
### Step 3: Remove the old domain

::: moniker range="o365-worldwide"

Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. Choose **Setup** \> **Domains**.
    
3. On the **Domains** page, choose the domain that you want to remove. 
    
4. In the right pane, choose **Remove**.
    
5. Follow any additional prompts, and then choose **Close**.
    
## How long does it take for a domain to be removed?

It can take as little as 5 minutes for Office 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Office 365 groups. If there are many references that use the domain it can take several hours (a day) for the domain to be removed.
  
If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## Still need help?

::: moniker range="o365-worldwide"

> [!NOTE]
> You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account. 
  
Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it! 
  
::: moniker-end



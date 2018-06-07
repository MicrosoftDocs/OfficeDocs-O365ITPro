---
title: "Remove a domain from Office 365"
ms.author: pebaum
author: pebaum
manager: scotv
ms.date: 5/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_Remove_RemoveDomain'
- 'O365M_Setup_RemoveDomain'
- 'O365E_Setup_RemoveDomain'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365_Setup
- Adm_O365_Top
search.appverid:
- MET150
- MOP150
- MOE150
- MEW150
- MED150
- GEU150
- GMU150
- GMA150
- MBS150
- GPA150
- GPU150
- GEA150
- BCS160
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c

description: "Find steps to remove a domain from Office 365, and use this checklist to make sure you're ready to remove the domain first. You can't remove the initial domain that came with Office 365. "
---

# Remove a domain from Office 365

Contributors: [![Peter Baumgartner](../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/?linkid=847121)
  
 **[Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a)** if you don't find what you're looking for. 
  
Are you removing your domain because you want to add it to a different Office 365 subscription plan? Or do you just want to cancel your subscription? You can [change your plan or subscription](../billing/switch-to-a-different-plan.md) or [Cancel Office 365 for business](https://support.office.com/article/b1bc0bef-4608-4601-813a-cdd9f746709a).
  
::: moniker range="o365-worldwide"

## [Step 1](#tab/)
  
### Move users to another domain

1. Go to the [![Click here to go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).
    
    Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).
    
    Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).
    
2. Choose **Users** > **Active Users**.
    
3. Select the boxes next to the names of the users who you want to move.
    
4. In the **Bulk actions** pane, choose **Edit domains**.
    
5. In the **Edit domains** pane, choose a different domain. 
    
6. Choose **Set as primary**, then choose **Save**.
    
7. You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.
    
    For example, if you're logged in as  *dave@contoso.onmicrosoft.com*  : 
    
1. Go to **Users** > **Active Users**, select your account from the list, and then choose **Edit** in the **Username** row in the left pane. 
    
2. Choosea different domain:  *contoso.com* 
    
3. Choose **Set as primary**, choose **Save**, and then **Close**.
    
4. At the top, choose your account name, then choose **Sign Out**.
    
5. Sign in with the new domain and your same password:  *dave@contoso.com* 
    
You can also use PowerShell to move users to another domain. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## [Step 2](#tab/)
  
### Move groups to another domain

1. Go to the [![Click here to go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).
    
    Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).
    
    Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).
    
2. Choose **Groups** > Groups. 
    
3. Select the box for any group or distribution listassociated with the domain that you want to remove.
    
4. In the right pane, next to the group name, choose **Edit**.
    
5. Under **Group Id**, use the drop-down to choose another domain.
    
6. Choose **Save**, then **Close**. Repeat this process for any groups or distribution lists associated with the domain that you want to remove.
    
## [Step 3](#tab/)
  
### Remove the old domain

1. Go to the [![Click here to go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).
    
    Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).
    
    Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).
    
2. Choose **Setup** > **Domains**.
    
3. On the **Domains** page, choose the domain that you want to remove. 
    
4. In the right pane, choose **Remove**.
    
5. Follow any additional prompts, and then choose **Close**.
    
## [Step 4](#tab/)
  
---

::: moniker-end

## How long does it take for a domain to be removed?

It can as little as 5 minutes for Office 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Office 365 groups. If there are many references that use the domain it can take several hours (a day) for the domain to be removed.
  
If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/en-us/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
||
|:-----|
|![The short icon for LinkedIn Learning.](../media/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **New to Office 365?**         Discover free video courses for [Office 365 admins and IT pros](68cc9b95-0bdc-491e-a81f-ee70b3ec63c5.md), brought to you by LinkedIn Learning. |
   
## Still need help?

::: moniker range="o365-worldwide"

> [!NOTE]
> You can't remove the [About your initial onmicrosoft.com domain in Office 365](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a) domain from your account. 
  
Still not working? Your domain might need to be manually removed. [Give us a call](../support/contact-support-for-business-products.md) and we'll help you take care of it! 
  
::: moniker-end


---
title: "Assign licenses to users in Office 365 for business"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_ManageLicenses'
- 'O365P_AssignRemoveLicense'
- 'O365M_ManageLicenses'
- 'O365M_AssignRemoveLicense'
- 'O365E_ManageLicenses'
- 'O365E_AssignRemoveLicense'
- 'ms.exch.owap.LicenseAssign'
- 'ms.exch.owab.LicenseAssign'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_Top
search.appverid:
- MOW150
- MOE150
- MED150
- GMA150
- MBS150
- GPA150
- GEA150
- OWB150
- MOW160
- BEA160
ms.assetid: 997596b5-4173-4627-b915-36abac6786dc

description: "Learn how to assigns licenses to users in Office 365 for business."
---

# Assign licenses to users in Office 365 for business

## [To one user](#tab/)
  
1. In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page, or choose **Users** > **Active users**.
    
    In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=847686) page, or choose **Users** > **Active users**.
    
    In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=850628) page, or choose **Users** > **Active users**.
    
2. Select the box next to the name of the user to whom you want to assign a license.
    
3. On the right, in the **Product licenses** row, choose **Edit**.
    
4. In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user. 
    
    By default, all services associated with that license are automatically assigned to the user. To limit which services are available to the user, switch the toggles to the **Off** position for the services that you don't want that user to have. 
    
5. At the bottom of the **Product licenses** pane, choose **Save** > **Close** > **Close**.
    
**The Product licenses pane showing which licenses the user has.**

![The product licenses pane showing which licenses the user has.](../media/fbab37fe-bcd5-4a5e-86bf-921879c963f7.png)
  
## [To multiple users](#tab/)
  
1. In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page, or choose **Users** > **Active users**.
    
    In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=847686) page, or choose **Users** > **Active users**.
    
    In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=850628) page, or choose **Users** > **Active users**.
    
2. Select the boxes next to the names of the users who you want to assign licenses to.
    
3. In the **Bulk actions** pane, choose **Edit product licenses**.
    
4. In the **Assign products** pane, select **Add to existing product license assignments** > **Next**.
    
5. Switch the toggle to the **On** position for the license that you want the selected users to have. 
    
    By default, all services associated with that license are automatically assigned to the user. To limit which services are available to the user, switch to toggles to the **Off** position for the services that you don't want the user to have. 
    
6. At the bottom of the **Add to existing products** pane, choose **Add** > **Close** > **Close**.
    
**The Product licenses pane showing which licenses the users have.**

![The product licenses pane showing which licenses the user has.](../media/fbab37fe-bcd5-4a5e-86bf-921879c963f7.png)
  
---

## Move users to a different subscription

If you have more than one subscription, and you have users who already have a license for one subscription, but you want to move them to another subscription, you can replace their existing license with a different one.
  
1. In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page, or choose **Users** > **Active users**.
    
    In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=847686) page, or choose **Users** > **Active users**.
    
    In the Office 365 admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=850628) page, or choose **Users** > **Active users**.
    
2. Select the boxes next to the names of the users who you want to replace existing licenses for.
    
3. In the **Bulk actions** pane, choose **Edit product licenses**.
    
4. In the **Assign products** pane, select **Replace existing product license assignments** > **Next**.
    
5. Switch the toggle to the **On** position for the licenses you want to assign to these users. 
    
    To limit which services are available to the user, switch the toggles to the **Off** position for the services that you don't want that user to have. Any previous license assignments for the selected users will be removed. 
    
6. At the bottom of the **Replace existing products** pane, select **Replace** > **Close** > **Close**.
    
**The "Replace existing product license assignments" option in the Assign products pane.**

![The replace existing product license assignments option in the assign products pane.](../media/69125d1e-603d-41ac-bd12-edfef62d744f.png)
  
## Remove or reassign unused Office 365 licenses

> [!VIDEO https://www.microsoft.com/videoplayer/embed/68578ae6-5249-44d5-9d1c-fc73d5d1543c?autoplay=false]
  
## What you need to know about assigning licenses to users in Office 365 for business

- You need to be either a Global admin or a User management admin. For more information, see [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).
    
- You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).
    
- Use these steps to add a license to an existing user account. [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)
    
    If you're using Office 365 operated by 21Vianet in China, see [Add, edit, delete or restore user accounts in Office 365 operated by 21Vianet - Admin Help](https://support.office.com/article/39772f78-1df9-4b82-a3e5-f8ad41e66807).
    
- Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.
    
## Articles about managing licenses for Office 365 for business

::: moniker range="o365-worldwide"

- [Understand subscriptions and licenses in Office 365 for business](https://support.office.com/article/7ac93507-0e38-4398-8bfe-9c1d123cb387)
    
- [Remove licenses from users in Office 365 for business](https://support.office.com/article/9b497c85-d0a4-4735-80fa-d3565bc05bd1)
    
- [Remove licenses from your Office 365 for business subscription](https://support.office.com/article/9c64d127-e2dd-4ecc-81f5-2f87e5a74803)
    
- [Buy licenses for your Office 365 for business subscription](https://support.office.com/article/36081d8d-b3fa-4948-8c34-e217bba825e1)
    
- [Buy another Office 365 for business subscription](https://support.office.com/article/fab3b86c-3359-4042-8692-5d4dc7550b7c)
    
- [Buy or edit an add-on for Office 365 for business](buy-or-edit-an-add-on-for-office-365-for-business.md)
    
- [Manage Yammer user licenses in Office 365](https://support.office.com/article/34a67e3a-3fd8-4e54-bffb-dd5ad0e48590)
    
::: moniker-end

## Articles about managing licenses for Office 365 for business

::: moniker range="o365-germany"

- [Understand subscriptions and licenses in Office 365 for business](https://support.office.com/article/7ac93507-0e38-4398-8bfe-9c1d123cb387)
    
- [Remove licenses from users in Office 365 for business](https://support.office.com/article/9b497c85-d0a4-4735-80fa-d3565bc05bd1)
    
- [Remove licenses from your Office 365 for business subscription](https://support.office.com/article/9c64d127-e2dd-4ecc-81f5-2f87e5a74803)
    
- [Buy licenses for your Office 365 for business subscription](https://support.office.com/article/36081d8d-b3fa-4948-8c34-e217bba825e1)
    
- [Buy another Office 365 for business subscription](https://support.office.com/article/fab3b86c-3359-4042-8692-5d4dc7550b7c)
    
- [Buy or edit an add-on for Office 365 for business](buy-or-edit-an-add-on-for-office-365-for-business.md)
    
- [Manage Yammer user licenses in Office 365](https://support.office.com/article/34a67e3a-3fd8-4e54-bffb-dd5ad0e48590)
    
::: moniker-end

::: moniker range="o365-worldwide"

||
|:-----|
|**Looking for [Share your Office 365 Home subscription with up to four people](https://support.office.com/article/b389b9ce-3ae3-4a82-9017-39d79972fcba)?**|
   
::: moniker-end

::: moniker range="o365-germany"

||
|:-----|
|**Looking for [Share your Office 365 Home subscription with up to four people](https://support.office.com/article/b389b9ce-3ae3-4a82-9017-39d79972fcba)?**|
   
::: moniker-end

||
|:-----|
|![The short icon for LinkedIn Learning.](../media/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **New to Office 365?**         Discover free video courses for [Office 365 admins and IT pros](68cc9b95-0bdc-491e-a81f-ee70b3ec63c5.md), brought to you by LinkedIn Learning. |
   
## Still need help?

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
If you're using Office 365 operated by 21Vianet in China, please [contact the 21Vianet support team](https://go.microsoft.com/fwlink/p/?linkid=847978).
  
## See Also

[Cancel Office 365 for business](https://support.office.com/article/b1bc0bef-4608-4601-813a-cdd9f746709a)
  


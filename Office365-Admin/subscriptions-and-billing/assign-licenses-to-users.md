---
title: "Assign licenses to users in Office 365 for business"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 997596b5-4173-4627-b915-36abac6786dc
description: "Learn how to assign licenses to one or multiple users in Office 365 for business, move users to a new subscription, or remove or reassign unused Office 365 licenses."
---

# Assign licenses to users in Office 365 for business

## [To one user](#tab/One)
  
1. In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page, or choose **Users** \> **Active users**.
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page. 
    
    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page. 
    
2. Select the box next to the name of the user to whom you want to assign a license.
    
3. On the right, in the **Product licenses** row, choose **Edit**.
    
4. In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user. 
    
    By default, all services associated with that license are automatically assigned to the user. To limit which services are available to the user, switch the toggles to the **Off** position for the services that you don't want that user to have. 
    
5. At the bottom of the **Product licenses** pane, choose **Save** \> **Close** \> **Close**.
    
**The Product licenses pane showing which licenses the user has.**

![The product licenses pane showing which licenses the user has.](../media/fbab37fe-bcd5-4a5e-86bf-921879c963f7.png)
  
## [To multiple users](#tab/Multiple)
  
1. In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page, or choose **Users** \> **Active users**.
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page. 
    
    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page. 
    
2. Select the boxes next to the names of the users who you want to assign licenses to.
    
3. In the **Bulk actions** pane, choose **Edit product licenses**.
    
4. In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.
    
5. Switch the toggle to the **On** position for the license that you want the selected users to have. 
    
    By default, all services associated with that license are automatically assigned to the user. To limit which services are available to the user, switch to toggles to the **Off** position for the services that you don't want the user to have. 
    
6. At the bottom of the **Add to existing products** pane, choose **Add** \> **Close** \> **Close**.
    
**The Product licenses pane showing which licenses the users have.**

![The product licenses pane showing which licenses the user has.](../media/fbab37fe-bcd5-4a5e-86bf-921879c963f7.png)
  
---

## Move users to a different subscription

If you have more than one subscription, and you have users who already have a license for one subscription, but you want to move them to another subscription, you can replace their existing license with a different one.
  
1. In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page, or choose **Users** \> **Active users**.
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page. 
    
    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page. 
    
2. Select the boxes next to the names of the users who you want to replace existing licenses for.
    
3. In the **Bulk actions** pane, choose **Edit product licenses**.
    
4. In the **Assign products** pane, select **Replace existing product license assignments** \> **Next**.
    
5. Switch the toggle to the **On** position for the licenses you want to assign to these users. 
    
    To limit which services are available to the user, switch the toggles to the **Off** position for the services that you don't want that user to have. Any previous license assignments for the selected users will be removed. 
    
6. At the bottom of the **Replace existing products** pane, select **Replace** \> **Close** \> **Close**.
    
**The "Replace existing product license assignments" option in the Assign products pane.**

![The replace existing product license assignments option in the assign products pane.](../media/69125d1e-603d-41ac-bd12-edfef62d744f.png)
  
## Remove or reassign unused licenses

> [!VIDEO https://www.microsoft.com/videoplayer/embed/68578ae6-5249-44d5-9d1c-fc73d5d1543c?autoplay=false]
  
## What you need to know about assigning licenses to users

- You need to be either a Global admin or a User management admin. For more information, see [About Office 365 admin roles](../add-users/about-admin-roles.md).
    
- You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).
    
- Use these steps to add a license to an existing user account. [Learn how to add a user account and assign a license at the same time](../add-users/add-users.md)
    
- Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.
    
## Articles about managing licenses

- [Understand subscriptions and licenses](subscriptions-and-licenses.md)
    
- [Remove licenses from users](remove-licenses-from-users.md)
    
- [Remove licenses from your subscription](remove-licenses-from-subscription.md)
    
- [Buy licenses for your subscription](buy-licenses.md)
    
- [Buy another subscription](buy-another-subscription.md)
    
- [Buy or edit an add-on](buy-or-edit-an-add-on.md)
    
- [Manage Yammer user licenses](https://docs.microsoft.com/en-us/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## Related topics

[Cancel your subscription](cancel-your-subscription.md)
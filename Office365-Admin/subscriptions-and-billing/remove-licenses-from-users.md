---
title: "Remove licenses from users in Office 365 for business"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_RemoveEXOLicense'
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9b497c85-d0a4-4735-80fa-d3565bc05bd1
description: "Learn how to remove licenses from user accounts in Office 365 for business subscription. "
---

# Remove licenses from users in Office 365 for business

## [From one user](#tab/One)
  
1. In the Admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page, or choose **Users** \> **Active users**.
    
    If you're using Office 365 Germany, go to this [Active users](https://go.microsoft.com/fwlink/p/?linkid=847686) page. 
    
    If you're using Office 365 operated by 21Vianet, go to this [Active users](https://go.microsoft.com/fwlink/p/?linkid=850628) page. 
    
2. Select the user that you want to remove the license from.
    
3. On the right, in the **Product licenses** row, choose **Edit**.
    
4. In the **Product licenses** pane, switch the toggle to the **Off** position for the license you want to remove from the user. For example, switching off Office 365 Enterprise E3 license will remove that license from the user and all of the services under that license. 
    
5. At the bottom of the **Product licenses** pane, choose **Save** \> **Close** \> **Close**.
    
**The user's product licenses pane showing the Office 365 Enterprise E3 license toggle.**

![The product licenses pane showing which licenses the user has.](../media/fbab37fe-bcd5-4a5e-86bf-921879c963f7.png)
  
## [From multiple users](#tab/Multiple)
  
1. In the Admin center, go to the [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page, or choose **Users** \> **Active users**.
    
    If you're using Office 365 Germany, go to this [Active users](https://go.microsoft.com/fwlink/p/?linkid=847686) page. 
    
    If you're using Office 365 operated by 21Vianet, go to this [Active users](https://go.microsoft.com/fwlink/p/?linkid=850628) page. 
    
2. Select the boxes next to the names of the users from whom you want to remove all licenses.
    
3. In the **Bulk actions** pane, choose **Edit product licenses**.
    
4. In the **Replace existing products** pane, select **Replace existing product license assignments** \> **Next**.
    
5. At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users.** check box, then choose **Replace** \> **Close** \> **Close**.
    
**The "Replace existing product license assignments" option in the Assign products pane.**

![The replace existing product license assignments option in the assign products pane.](../media/69125d1e-603d-41ac-bd12-edfef62d744f.png)
  
.
**The "Remove all product licenses from the selected users" check-box in the Assign products pane.**

![Select the check-box to remove all licenses from the selected users accounts.](../media/e0a7af28-0fef-4e66-9fd6-9c7174cb942c.png)
  
---

## What you need to know about removing licenses from users in Office 365 for business

- You need to be either a Global admin or a User management admin. For more information, see [About Office 365 admin roles](../add-users-2/about-admin-roles.md).
    
- You can [remove licenses from user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848428).
    
- You can also [delete user accounts](../add-users-2/delete-a-user.md) that have been assigned a license to make their license available to other users. When you delete a user account, their license is immediately available to be assigned to someone else. 

- When a user's license is removed, data that is associated with that user account is held for 30 days. After the 30 day grace period, the data is deleted and can't be recovered. Files that are saved in OneDrive or SharePoint Online are not deleted.
    
- If you have an Enterprise subscription, like Office 365 Enterprise E3, Exchange Online lets you preserve the mailbox data of a deleted Office 365 user account by using inactive mailboxes. For more information, see [Manage inactive mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=848214).
    
- For information about how to block a user's access to Office 365 data after their license has been removed and how to get access to the data afterwards, see [Remove a former employee from Office 365](../add-users-2/remove-former-employee.md).
    
- If you remove a user's Office license and they still have Office installed, they'll see [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) when they use Office. 
    
## Articles about managing licenses for Office 365 for business

- [Understand subscriptions and licenses](subscriptions-and-licenses.md)
    
- [Remove licenses from your subscription](remove-licenses-from-subscription.md)
    
- [Assign licenses to users](assign-licenses-to-users.md)
    
- [Buy licenses for your subscription](buy-licenses.md)
    
- [Buy another subscription](buy-another-subscription.md)
    
- [Buy or edit an add-on for Office 365 for business](buy-or-edit-an-add-on.md)
    
- [Manage Yammer user licenses in Office 365](https://support.office.com/article/34a67e3a-3fd8-4e54-bffb-dd5ad0e48590.aspx)

## Related Topics

[Cancel Office 365 for business](cancel-your-subscription.md)
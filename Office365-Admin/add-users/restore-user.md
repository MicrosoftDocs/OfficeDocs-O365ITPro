---
title: "Restore a user in Office 365"
ms.author: dianef
author: dianef77
manager: mnirkhe

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_DeleteRestoreUsers'
- 'O365E_DeleteRestoreUsers'
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_Top
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: "Learn how to restore deleted Office 365 user accounts and all associated data."
---

# Restore a user in Office 365

   
When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).
  
Here are a couple of tips:
  
- Make sure there are Office 365 licenses available that you can assign to the account.
    
- If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account. 
    
## Restore one or more user accounts
<a name="__toc336346186"> </a>

You must have [admin permissions](about-admin-roles.md) in Office 365 to do this. 
  
 
::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Admin center, go to **Users** \> **Deleted users**.
    
    ![Choose Users \> Deleted users.](../media/bd041355-906e-440b-b1ce-00cabf12d490.png)
  
3. On the **Deleted users** page, choose the names of the users that you want to restore, and then select **Restore**.
    
    ![Restore a user in Office 365.](../media/ab9119f4-b5a4-4f29-8397-67734ed86165.png)
  
4. Follow the prompts to set the password.
    
5. If the user is successfully restored, click **Send email and close**. If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.
    
After you've restored a user, make sure you reset the user's password; see [Reset a user's password](reset-passwords.md).
  
## Restore a user that has a user name conflict
<a name="RestoreUserNameConflict"> </a>

A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.
  
To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.
  

::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Admin center, go to **Users** \> **Deleted users**.
    
    ![Choose Users \> Deleted users.](../media/bd041355-906e-440b-b1ce-00cabf12d490.png)
  
3. On the **Deleted users** page, choose the names of the users that you want to restore, and then select **Restore**.
    
    > [!NOTE]
    > If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time. 
  
4. Follow the prompts to set the password.
    
5. Click **Restore**.
    
6. A message pops up that says there was a problem restoring the account. Do one of the following:
    
  - Cancel the restore and rename the current active user. Then attempt the restore again.
    
  - OR, type a new primary email address for the user and click **Restore**.
    
7. Review the results, and then select **Close**.
    
## Restore a user that has a proxy address conflict
<a name="RestoreUserProxyConflict"> </a>

A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.
  
You must have [admin permissions](about-admin-roles.md) in Office 365 to do this. 
  

::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Admin center, go to **Users** \> **Deleted users**.
    
    ![Choose Users \> Deleted users.](../media/bd041355-906e-440b-b1ce-00cabf12d490.png)
  
3. On the **Deleted users** page, select the user that you want to restore, and then select **Restore**. 
    
4. On the **Restore** page, follow the instructions to set the password
    
5. Click **Restore**. Any conflicting proxy addresses are automatically removed from the user you are restoring.
    
6. Review the results, and then select **Close**.

## Related Topics
<a name="RestoreUserProxyConflict"> </a>

[Delete a user](delete-a-user.md)
  


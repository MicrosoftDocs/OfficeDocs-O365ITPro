---
title: "Convert a user mailbox to a shared mailbox"
ms.author: dianef
author: dianef77
manager: mnirkhe

ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: "Learn to convert a private mailbox to a shared mailbox that can be accessed by multiple users. "
---

# Convert a user mailbox to a shared mailbox
  
When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.
  
 **Here are some really important things to you need to know:**
  
- The user mailbox you're converting needs an Office 365 license assigned to it before you convert it to a shared mailbox. Otherwise, you won't see the option to convert the mailbox. If you've removed the license, add it back so you can convert the mailbox. After converting the mailbox to a shared one, you can remove the license from the user's account.
    
- Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.
    
- Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](convert-user-mailbox-to-shared-mailbox.md#bkmk_deleted).
    
Here's how you convert a mailbox to a shared mailbox:
  
1. 
::: moniker range="o365-worldwide"

Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. On the **Active users** page, select the user whose mailbox you want to convert. 
    
3. On the user's page, expand **Mail Settings** and click **Convert to shared mailbox**. You won't see this option if the user doesn't have an Office 365 license assigned to them. Go assign them a license then come back to this step. 
    
    ![Convert user mailbox to shared mailbox](../media/ab36c282-c689-4b3d-82eb-5912a8a33a20.png)
  
4. Click **Convert** to complete the conversion. 
    
    ![Click Convert to convert user mailbox to shared mailbox](../media/b705fff8-9b87-48cc-9cd4-bcc989a8c569.png)
  
5. If the mailbox is smaller than 50GB, you can remove the [license from the user](../subscriptions-and-billing/remove-licenses-from-users.md), and stop paying for it. Don't delete the user's old mailbox. The shared mailbox needs it there as an anchor. The user won't be able to sign in using the old account.
    
6. For everything else you need to know about shared mailboxes, please see [Create a shared mailbox](create-a-shared-mailbox.md).
    
## Convert the mailbox of a deleted user
<a name="bkmk_deleted"> </a>

Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:
  
1. [Restore the user's account](../add-users/restore-user.md) . 
    
2. Make sure an Office 365 license is assigned to it.
    
3. Wait 20-30 minutes for their mailbox to be recreated.
    
4. Now follow the instructions on this page to convert their mailbox to a shared mailbox.
    
5. After that's done, you can remove the Office 365 license from the user's mailbox. Don't delete the user's old mailbox. The shared mailbox needs it there as an anchor. The user won't be able to sign in using the old account.
    
6. Add members to the shared mailbox.
    
## Convert a shared mailbox back to a user's (private) mailbox
<a name="bkmk_deleted"> </a>

1. In the Office 365 Admin center, expand **Admin centers** \> **Exchange**.
    
2. Choose **Recipients** \> **Shared**.
    
3. Choose the shared mailbox. Under **Convert to Regular Mailbox**, click **Convert**.
    
4. Go back to the Office 365 Admin Center. Under **Users**, choose the user account associated with the old shared mailbox. Assign a license to the account, and reset the password.
    
    It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.
    
## Convert a user's mailbox in a hybrid environment
<a name="bkmk_deleted"> </a>

If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud. 
  
Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.
  
Usually this is not a problem, but there are some scenarios where the attributes on-premises (which think that the mailbox is the user mailbox) can overwrite the new cloud version of those attributes, and as a result the mailbox might convert back. This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days** ! 
  
We've addressed most of the reasons why this happens but it still CAN happen, although infrequently. It's best to be safe and move the mailbox back to on-premises. 
  
## Related Topics
<a name="bkmk_deleted"> </a>

[Create a shared mailbox](create-a-shared-mailbox.md)
  


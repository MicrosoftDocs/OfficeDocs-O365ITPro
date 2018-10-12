---
title: "Remove license from shared mailbox"
ms.author: anfowler
author: anfowler
manager: scotv

ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: "Remove Office 365 license from a shared mailbox to assign it to another user. "
---

# Remove license from shared mailbox

Shared mailboxes don't need a license unless the mailbox has over 50GB of data. Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.
  
## Remove the license

1. In the Office 365 admin center, go to **Users** \> **Active users**.
    
    > [!NOTE]
    > You'll need to remove the license from the Active users page. You can't remove the license from the Shared mailbox page because licenses are user settings. 
  
2. Select the shared mailbox to view the user details.
    
3. Next to **Product licenses**, select **Edit**.
    
4. Toggle the license **Off**, and then select **Save**.
    
5. When you return to the **Active users**' page, it may take a few minutes for the user's status to refresh to **Unlicensed**. 
    
## Next steps

After you've removed the license, you can do the following:
  
[Remove licenses from your Office 365 for business subscription](../subscriptions-and-billing/remove-licenses-from-subscription.md)
  
[Assign licenses to users in Office 365 for business](../subscriptions-and-billing/assign-licenses-to-users.md)
  


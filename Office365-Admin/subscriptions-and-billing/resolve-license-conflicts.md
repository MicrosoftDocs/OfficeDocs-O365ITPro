---
title: "Resolve license conflicts in Office 365 for business"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: "Learn how to remove a license from your Office 365 for business subscription when the license is already assigned to someone."
---

# Resolve license conflicts in Office 365 for business

We recommend that you buy the licenses that you need for your subscription before you create new users. That way, a license can be assigned to new users as user accounts are created. If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts. For more information, see [Remove licenses from your subscription](remove-licenses-from-subscription.md).
  
## How do I view license conflicts?

1. In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, or choose **Billing** \> **Licenses**.
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page. 
    
    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page. 
    
2. Check the **Status** column for information about the conflict. If there's a conflict, you'll see a warning message, like in the following screenshot, that says one or more users need a valid license. 
    
    > [!NOTE]
    > You won't see the **Status** column if there are no conflicts. 
  
![Status column on the Liceses page.](../media/c58c8b04-9c61-48fa-a1ae-6f072feac36a.png)
  
## How do I resolve license conflicts?

You can resolve license conflicts by either buying more licenses or by removing licenses from users who no longer need them.
  
### Buy more licenses

1. In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, or choose **Billing** \> **Licenses**.
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page. 
    
    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page. 
    
2. In the **Status** column, choose **Buy more** to buy more licenses. 
    
    > [!NOTE]
    > You won't see the **Status** column if there are no conflicts. 
  
![Status column on the Licenses page.](../media/c58c8b04-9c61-48fa-a1ae-6f072feac36a.png)
  
3. On the subscriptions page, if you have multiple subscriptions, select the subscription that you need to purchase licenses for.
    
4. Choose **Add/Remove licenses**.
    
    ![Add/Remove licenses link on the Subscriptions page.](../media/311304a6-7384-43c6-82dc-087764488be7.png)
  
5. In the **Total licenses** box, enter the total number of licenses that you need for this subscription and then choose **Submit**. For example, if you had 100 licenses and you need to add 5 more, you would enter 105.
    
6. Review your new monthly cost and then choose **Close**.
    
For more information about buying more licenses, see [Buy licenses for your subscription](buy-licenses.md).
  
> [!NOTE]
> You can also renew your organization's subscription if it has expired. If **Recurring billing** is turned off, when the subscription expires you'll have a license conflict for every user and every service in that subscription. You can resolve these conflicts by [renewing your company's subscription](renew-your-subscription.md). 
  
### Remove licenses from users who don't need them

Complete the following steps to remove licenses from users who don't need them. You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).
  
> [!IMPORTANT]
> When you remove licenses, any user data associated with those licenses is deleted. 
  
1. In the Admin center, go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, or choose **Billing** \> **Licenses**.
    
    If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page. 
    
    If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page. 
    
2. In the **Status** column, choose **Unassign** to remove licenses from users who no longer need them. 
    
    > [!NOTE]
    > You won't see the **Status** column if there are no conflicts. 
  
![Status column on the Licenses page.](../media/c58c8b04-9c61-48fa-a1ae-6f072feac36a.png)
  
3. You'll see a list of users who are assigned this license.
    
    Select one or more users that you want to remove the license from. The users appear in the **Selected users** list. After you've selected the users, choose **Next**.
    
    ![Select users in which to remove licenses.](../media/e65bde53-f5c8-4f01-ba3d-bdd88764e1ad.png)
  
4. Choose **Remove licenses** \> **Yes** \> **Finish**.
    
## Related topics

[Assign licenses to users](assign-licenses-to-users.md)
  
[Remove licenses from users](remove-licenses-from-users.md)
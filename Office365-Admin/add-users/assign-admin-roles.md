---
title: "Assign admin roles in Office 365 for business"
ms.author: kwekua
author: kwekua
manager: scotv
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_AssignAdminPermissions'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Top
- Adm_UI_Elements
- EU_O365_UI_Elements
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Top
- Core_O365Admin_Migration
- MiniMaven
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: "Learn how to assign administrator roles to a user or multiple users in your business so that they can perform specific tasks in the Office 365 admin center."
---

# Assign admin roles in Office 365 for business

 
As the person who purchased your Office 365 business subscription, you are the global administrator. This means you have complete control over the Office 365 suite of products. To help you manage Office 365 for your business, you can assign users to administrator roles so they can perform tasks in the Office 365 admin center. For example, if you want help resetting passwords, you can assign someone to the Password administrator role.
  
![Users](../media/a022e5e8-0b11-47b6-bac8-7527c4f6a202.png) For a list of customized admin roles and a description of what they can do in Office 365, see [About Office 365 admin roles](about-admin-roles.md).
  
## Assign admin roles to a user in your business

::: moniker range="o365-worldwide"
1.  Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Admin center, select **Users**.
    
3. On the **Active users** page, choose the user whose administrator role you want to change. The properties page for the user opens. 
    
4. Next to **Roles**, choose **Edit**. If you don't see the **Edit** button, then you don't have global admin permissions and can't assign admin roles to other people. Ask a global admin in your business to assign roles for you. In a small business, the business owner (the person who purchased Office 365) is a global admin. In a large business, key people in the IT department are global admins. 
    
    ![Choose the Edit button next to Roles.](../media/f6256997-9ac2-4b78-95fa-564c6b715f3b.png)
  
5. Choose **Customized administrator** to see a list of roles we've customized for you. For a description of each role, see [About Office 365 admin roles.](about-admin-roles.md)

::: moniker range="o365-worldwide"

Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue.

Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end
    
## More info about admin role settings

1. In the **Alternative email address** box, type an email address that is not connected to Office 365. This email address is used for important notifications, including resetting the password for your Office 365 admin account, so the person must be able to access this email account whether they can access Office 365 or not. 
    
    > [!NOTE]
    > If you don't want to receive product-related communications at this alternate email address, change your contact preferences on the **About me** page. For more information, see [Change your contact preferences](../manage/change-contact-preferences.md). 
  
2. Choose **Save** \> **Close**.
    
3. Next to **Office phone**, select **Edit**.
    
4. In the **Mobile phone** box, type the number of a mobile phone—including the country code if the user has one—that can receive a text (SMS) message. This phone number is also used when you reset your password for your Office 365 admin account. 
    
    You need a mobile phone that's capable of receiving text messages for password reset only if one or both of the following applies to you:
    
  - Your organization has a custom domain that you've set up to use with Office 365.
    
  - Your Office 365 subscription is synchronized through directory synchronization.
    
5. When you have finished, choose **Save**.
    
## Assign admin roles to multiple users


If you know PowerShell, see [Assign roles to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/?linkid=854257). It's ideal for assigning roles to hundreds of users.
  
Use the following instructions to assign roles to tens of users.
  
::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. Go to **Users** \> **Active Users**.
    
3. On the **Active users** page, check the box next to the names of the users whose admin roles you want to change, and then click **Edit**![Edit](../media/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
4. Under **Bulk actions**, choose **Edit user roles**.
    
5. Choose the roles you want to assign, and the click **Save**.
    
## Didn't work for you?


Here are the top issues customers encounter when assigning admin roles:
  
- You are not part of the global admin group and so you don't have permissions to assign admin roles to other users. Ask another admin to assign roles for you.
    
- You're using Office 365 Small Business, a version that's no longer available for purchase. These instructions apply to current Office 365 for business plans.
    
## Related Topics


[Assign roles to user accounts with Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[Authorize or remove partner relationships](https://support.office.com/article/201ccb3b-6011-4bf1-a6b2-84e7cc1ee2d0.aspx)
  
[About the Office 365 admin center](../admin-overview/about-the-admin-center.md)
  


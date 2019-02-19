---
title: "Set the password expiration policy for your organization"
ms.author: kwekua
author: kwekua
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_PasswordExp'
- 'O365E_PasswordExp'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_O365_Top
- Adm_UI_Elements
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
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: "Learn how to set a password expiration policy for your organization in Office 365 admin center. "
---

# Set the password expiration policy for your organization

This article is for people who set password expiration policy for a business, school, or nonprofit.  

If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.
   
As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire. By default, passwords are set to never expire.
  
> [!IMPORTANT]
> Only [Office 365 global admins](../add-users/about-admin-roles.md) can perform these steps. 
  
1. Go to the [![Go to the Office 365 admin center](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

2. In the Office 365 admin center, go to **Settings** \> **Security and privacy**. If you aren't an Office 365 global admin, you won't see the Security and privacy option. <br/> ![Navigate to Security and Privacy](../media/5f474a03-38a4-4833-9f4c-db769de8b8d9.png)
  
3. Click **Edit**. <br/>![Choose Edit](../media/85ecde71-ecd2-4e02-ac1c-f27790c1869a.png)
  
4. If you don't want users to have to change passwords, set **Passwords never expire** to **On**.<br/> ![Set to On](../media/a12c3844-d951-4484-8d2b-4120b059ea37.png)
  
5. If you want user passwords to expire, in the first box type how often passwords should expire. Choose a number of days from 14 to 730.<br/>![Enter how often passwords should expire](../media/eaca5b33-c8b5-4d8b-b7ac-4712a9d0500e.png)
  
6. In the second box type when users are notified that their password will expire, and then click **Save**. Choose a number of days from 1 to 30. 
    
7. When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.<br/>![Notification the user sees](../media/a9809116-305c-4300-99c5-a3703dd65c30.png)
  
## Important things you need to know about the password expiration feature

Here are some things to know about how this feature currently works as of January 2018:
  
- **Bug**: We're currently investigating a bug that's preventing this feature from working consistently. Your users may not get a notification before their password expires. This means when they sign in to Office 365 and their password has expired, they'll be prompted to change their password at that time without any advance notice. 
    
- People who only use the Outlook app won't be forced to reset their Office 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.
    
- Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## Prevent last password from being used again

If you want to prevent your users from recycling old passwords, you can do so in Azure AD. See [Password policies and restrictions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=860842).
  
## Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Office 365)

This article is for setting the expiration policy for cloud-only users (Azure AD). It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.
  
To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).
  


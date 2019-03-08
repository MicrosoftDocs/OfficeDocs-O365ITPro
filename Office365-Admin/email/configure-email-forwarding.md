---
title: "Configure email forwarding in Office 365"
ms.author: dianef
author: dianef77
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: "Set up email forwarding to one or more email accounts using Office365."
---

# Configure email forwarding in Office 365
  
As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox. Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.
  
## Configure email forwarding

 **Tips:**
  
- **To forward to multiple email addresses**, [create a distribution list](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.
    
- Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded. 
    
- Email forwarding requires that the  *from*  account has a license. If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md). This way several people can access it. However, a shared mailbox cannot exceed 50GB. 
    
You must have [admin permissions](../add-users/about-admin-roles.md) in Office 365 to do this. 

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end
  
1. [Sign in to Office 365](https://go.microsoft.com/fwlink/p/?LinkID=402333).
    
2. Go to the [Microsoft 365 admin center](../admin-overview/about-the-admin-center.md).
    
3. Select **Users**.
    
    ![Click on User.](../media/1596dc50-1d06-4b3a-83c3-2791d0856d6f.png)
  
4. On the **Active users** page, choose the user who's email you want to forward. 
    
    ![Choose a user.](../media/e103733a-dd8d-44e6-b36b-3ad5b2582140.png)
  
5. Scroll down to **Mail Settings** and expand using the drop-down. Click or tap **Edit**
    
    ![Chose Edit to configure email forwarding](../media/2e74ec77-681e-422f-905f-ffe15a1b80f1.png)
  
6. On the Email forwarding page, select **Forward all email sent to this mailbox** toggle, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails. If you don't see this option, make sure a license is assigned to the user account. Choose **Save**.
    
    **To forward to multiple email addresses**, [create a distribution list](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.
    
    ![Enter forwarding email address](../media/9aa97b22-3951-4a9f-8483-231400d8821a.png)
  
7. Remember, don't delete the account of the user who's email you're forwarding or remove the license! 
    
All email sent to this mailbox will now be forwarded to Albellew@contoso.com.

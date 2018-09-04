---
title: "Office 365 sign-in for Yammer"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 9/4/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: b1745e3c-d4d7-4e20-a155-ebf85106b998
description: "Choose the authentication method to use for Office 365 and Yammer: directory sync, single sign-on (SSO), or Office 365 sign-in for Yammer. Add Yammer to the Office 365 navigation bar."
---

# Office 365 sign-in for Yammer

Office 365 sign-in for Yammer lets users access Yammer with their Office 365 identity. This is the preferred authentication model for Yammer because when you use the same identity: 
  
- You can easily manage the Yammer service in Office 365. For example, you can [Manage Yammer users across their life cycle from Office 365](manage-users-across-their-lifecycle.md), and you can manage Yammer administrators in Office 365.
    
- Users can seamlessly use Yammer from Office 365. They can use Yammer without having to log in with a separate username and password, and they can quickly switch back and forth between Yammer and other Office 365 services including Outlook, SharePoint Online sites, and OneDrive for Business by using the Office 365 app launcher.
    
Here's a screenshot of the Office 365 app launcher that shows Yammer.
  
![The Office 365 app launcher with the Yammer app highlighted](../media/2a9e4707-3671-411d-81c1-723fcdd2b483.png)
  
Until January 31, 2019, Yammer Enterprise continues to support legacy Yammer identity (login with email, password) for those users who have not yet been added to Office 365. We strongly recommend you add all Yammer users to Office 365. After January 31, 2019, users will be required to use their Azure Active Directory (AAD)credentials. For more information including how to identify users that don't yet have AAD credentials, see [AAD credentials will be required for Yammer Enterprise log in](aad-account-required.md).
  
## How it works

When Office 365 users visit Yammer for the first time from Office 365, Yammer tries to connect their Office 365 account to their existing Yammer account, if available. For this to happen, the email address of the Office 365 user account must match the existing Yammer account email address. When a user signs in with Office 365, Yammer first tries to map the Office 365 user's primary email, then proxy emails, and then the user principal name (UPN). If there are no matches, a new Yammer user is created.
  
If the user is visiting Yammer through www.yammer.com, Yammer checks that the user has successfully logged in to Office 365 at least once. This check is used to ensure that Office 365 credentials have been provided to the user and avoid users from being locked out of an existing Yammer network while the Office 365 deployment is under way. If the user has not logged in to Office 365, then they will continue to use their legacy Yammer identity to access Yammer. There is a delay of a few hours between the time the user successfully logged in, and the time Yammer can detect it. If you want to instantly use Office 365 sign-in for Yammer, have users log in to Office 365 first, and then access Yammer using the Yammer tile on the app launcher.
  
The following flowchart shows how this works:
  
![Flowchart diagram that shows a decision tree for whether a user can be logged in with their Office 65 identity, will be logged in with their Yammer identity, or whether a a new Yammer user will be created.](../media/31216e5e-721c-4227-9d0d-a050e3359823.png)
  
After a user is connected and using Office 365 sign-in for Yammer, the user can no longer use their previous legacy Yammer identity to log in and you will now manage the lifecycle of this user from Office 365.
  
## How do I enable Office 365 sign-in for Yammer?

No action is needed to enable Office 365 sign-in for Yammer.
  
## Enforce Office 365 sign-in for all users in the network

You can choose to enforce Office 365 sign-in for Yammer for all users in the network, effectively disabling the legacy Yammer identity ( where users log in with email, password). After this is enforced, all users in the network will need to use Office 365 accounts for login. For more information, see [Enforce office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md).
  
## Use Yammer with other Office 365 services

Yammer integrates seamlessly with other services in Office 365. For example, you can share [Stream or Office 365 Video](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) and [Group and share documents in Office Delve](https://support.office.com/article/da0c5804-01ef-4edd-8b87-e576b19bef3e#BKMK_WorkTogetherByUsingYammer) with other users using Yammer. 
  
## Make Yammer the default enterprise social network in SharePoint

By default, when users select **Conversations** in SharePoint, they see their the SharePoint newsfeed (Outlook groups), rather than Yammer conversations. You can make Yammer the default enterprise social network in SharePoint. With this, when users select **Conversations** in SharePoint, they see their Yammer conversations, rather than the SharePoint newsfeed (Outlook groups). 
  
> [!NOTE]
> You must be an Office 365 global administrator to make this change. For more information about permissions levels, see [About Office 365 admin roles](https://support.office.com/article/DA585EEA-F576-4F55-A1E0-87090B6AAA9D). 
  
1. In Office 365, go to **Admin** \> **SharePoint**.
    
2. Click **Settings**.
    
3. Under **Enterprise Social Collaboration**, choose **Use Yammer.com service**.
    
    ![SharePoint admin center, Enterprise Social Collaboration options](../media/c89f672f-be20-4b71-9719-7acfa03162b8.png)
  
4. Select **Save**.
    
    > [!NOTE]
    > This change can take up to 30 minutes to complete. 
  
## Support for users without email

While legacy Yammer username and password required a valid email address, users without email addresses are supported with Office 365 sign-in. Ensure the UPN assigned to the user is in an email address format (for example: user@contoso.com) and the domain associated with the email address is part of the Yammer network.
  
## Frequently asked questions

**Q: Can I access Office 365 and Yammer on my phone with just one sign-in account?**
    
A: Yes! Office 365 identity can be used to access Yammer from any device or app. You can use it to access Yammer from the browser, from Yammer Embed, from third party Yammer apps and the Yammer apps for your phone/tablet. And you will use the same Office 365 identity to access other Office 365 services such as OneDrive for Business or Outlook.
    
**Q: Do users have to do anything to make this work?**

A: Your network users should access Yammer once with their Office 365 identity (this action connects the Office 365 identity to Yammer). After this, users should sign in to Yammer again on all of their devices and apps.
    
**Q: I'm using Office 365 SSO and the Office 365 sign-in for Yammer, so what happens if Office 365 is federated with an on-premises environment?**

A: The Office 365 sign-in for Yammer will respect any Office 365 federation setting automatically.
    
**Q: Can I combine Yammer networks in order to take advantage of Office 365 sign-in for Yammer?**

A: Yes, this is required as of October 26, 2018. For more information, see [Network migration: Consolidate multiple Yammer networks](../configure-your-yammer-network/consolidate-multiple-yammer-networks.md).
    
## See also

[SharePoint enterprise social experience: Yammer and Outlook groups](../integrate-yammer-with-other-apps/yammer-and-newsfeed.md)
    
[Enforce office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md)
    
[Manage Yammer users across their life cycle from Office 365](manage-users-across-their-lifecycle.md)
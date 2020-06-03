---
title: "All Company will work like other Yammer communities"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 03/31/2020
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 
description: "Learn how All Company will work like other communities in Yammer."
---

# All Company will work like other Yammer communities

All Company now leverages the Yammer community architecture so that you can get all the new community experiences and features as they roll out. This includes bringing community customization options like cover photos, naming, and much more to All Company.

## What will be the changes to All company?

After this change, these features will be available to network admins:

- You will be able to edit the name, description, avatar, and cover photo for All Company.
- Pinned resources actions (add, delete, reposition) will be restricted to network admins.
- Previous All Company Resources will be moved to Pinned resources.  
- Searching for the All Company community name (even if it has been renamed) will be possible.

These settings will still not be available for network admins:

- Related communities will not be available for All Company.
- Post to this community by email will not be available for All Company.
- Admins cannot promote others as admin of the All Company community.
- All Company cannot be deleted from Yammer UI.  
- All Company privacy and data classification cannot be changed in Yammer settings.

## Is my All Company community Office 365-connected, and what does being connected mean?

Today, networks can have communities that are either all connected, all unconnected, or a mix of connected and unconnected.

Having an All Company that is connected means that an Office 365 Group is created.

## What is the benefit of All Company backed by an Office 365 Group?

The differences between an All Company that is connected to an Office 365 Group and an unconnected All Company are:

- A connected All Company community creates an Office 365 Group.
- A connected All Company can have Live Events.
- A connected All Company has [Office 365 Resources](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups?redirectSourcePath=%252farticle%252fd8c239dc-a48b-47ab-b85e-6b4b8191a869
).

The process for confirming that All Company is connected will work the same as it does for any community. To do so, select the following settings in the Network Admin Settings.  

In network admins settings, if you select **Enforce Office 365 Identity**, then your network will have an All Company community that is connected to an Office 365 Group. If you do not select this, then All Company will still not be connected to an Office 365 Group after this change.

![Office 365 Identity Enforcement](../media/710d82b4-a6fa-43bf-b609-8f2fc80fab52.png)

## If the All Company community is connected, what should I be aware of?

- All Company can be deleted in AAD. It will go through soft-delete and then hard-delete like other communities.
- The Office 365 Expiration policy is now enabled for All Company when connected.
- Privacy and Data Classification for All Company can be changed in AAD but nothing will happen to the user experience because all users in the organization are members of All Company.

## Related articles

[Is my Yammer community or group connected to Office 365?](https://support.office.com/en-us/article/is-my-community-or-group-connected-to-microsoft-365-f592296f-4158-43d8-b711-d77c35db826e)

[Yammer and Office 365 Groups](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups?redirectSourcePath=%252farticle%252fd8c239dc-a48b-47ab-b85e-6b4b8191a869)

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

## Is my All Company community connected?

Today, networks can have communities that are either all connected, all unconnected, or a mix of connected and unconnected.

## What is the benefit of a connected All Company?

The differences between a connected and unconnected All Company are:

- A connected All Company can have Live Events.
- A connected All Company has [Office 365 Resources](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups?redirectSourcePath=%252farticle%252fd8c239dc-a48b-47ab-b85e-6b4b8191a869
).

The process for confirming that All Company is connected will work the same as it does for any community. To do so, select the following settings in the Network Admin Settings.  

In network admins settings, if you select **Enforce Office 365 Identity** then your network will have an All Company community that is connected. If you do not select this, then All Company will still not be connected after this change.

! [Office 365 Identity Enforcement](../media/710d82b4-a6fa-43bf-b609-8f2fc80fab52.png)

## If the All Company community is connected, what should I be aware of?

- All Company can be deleted in AAD. It will go through soft-delete and then hard-delete like other communities.
- The Office 365 Expiration policy is now enabled for All Company when connected.
- Privacy and Data Classification for All Company can be changed in AAD but nothing will happen to the user experience because all users in the organization are members of All Company.

## Related topics

[Is my group in Yammer connected to Office 365](https://support.office.com/article/is-my-group-in-yammer-connected-to-office-365-02f1c157-d2f8-4197-a5f8-2d670bba29e6?ui=en-US&rs=en-US&ad=US
)

[Yammer and Office 365 Groups](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups?redirectSourcePath=%252farticle%252fd8c239dc-a48b-47ab-b85e-6b4b8191a869
)

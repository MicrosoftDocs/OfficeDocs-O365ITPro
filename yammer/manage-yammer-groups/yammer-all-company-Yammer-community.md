---
title: "All Company now works like other Yammer communities"
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
description: "Learn how All Company now works like other communities in Yammer."
---

# All Company now works like other Yammer communities

All Company now leverages the Yammer community architecture in both native mode and non-native mode tenants so that you can get all the new community experiences and features as they roll out. This integration includes bringing community customization options like cover photos, naming, and much more to All Company.

## What are the changes to All Company?

Now that All Company works like other communities, these features are available to network admins:

- You can edit the name, description, avatar, and cover photo for All Company.
  >[!IMPORTANT]
    > Previously the All Company name locale would change based on the user’s locale, but now that you can fully customize the name, the default All Company name is set in the network’s locale.  While an admin can change the name now that All Company is a regular community, the name will persist for that network. The name will not adjust to the language of the user's locale if it differs from the network.
- Pinned resources actions (add, delete, reposition) are restricted to network admins.
- You can now [restrict posts to All Company](https://support.office.com/article/3219d2ae-db15-4c9f-9dd2-28559ae39a97), if you want to better control the types of conversations that take place in the All Company feed. When this setting is enabled, only admins can post in All Company but employees can reply to a conversation starter or react to it.
- Previous All Company Resources are moved to Pinned resources.
- Searching for the All Company community name (even if it has been renamed) is possible.
- Community insights are now the insights for just the All Company community. Previously the insights found under the All Company page were for the entire network and not specific to the community.
  >[!NOTE]
  >If you need access to previous insights for All Company, you can access them through the following URL: https://www.yammer.com/*domain-name*/#/groups/company/insights. Substitute your organization’s domain name in the address.
- You can now promote other users as admins of All Company to better manage this community.
- All Company is now sorted like other communities, but users can favorite the All Company community to have it at the top of their communities list. 

These settings will still not be available for network admins:

- Related communities will not be available for All Company.
- Post to this community by email will not be available for All Company.
- All Company cannot be deleted from Yammer UI.  
- All Company privacy and data classification cannot be changed in Yammer settings.

## Is my All Company community Office 365-connected, and what does being connected mean?

Today, networks can have communities that are either all connected, all unconnected, or a mix of connected and unconnected.

Having an All Company that is connected means that an Office 365 Group is created. In native mode, All Company will always be a connected community.

## What is the benefit of All Company backed by an Office 365 Group?

The differences between an All Company that is connected to an Office 365 Group and an unconnected All Company are:

- A connected All Company community creates an Office 365 Group.
- A connected All Company can have Live Events.
- A connected All Company has [Office 365 Resources](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups?redirectSourcePath=%252farticle%252fd8c239dc-a48b-47ab-b85e-6b4b8191a869).

The process for confirming that All Company is connected works the same as it does for any community. To do so, select the following settings in the Network Admin Settings.

In network admins settings, if you select **Enforce Office 365 Identity**, then your network will have an All Company community that is connected to an Office 365 Group. If you do not select this, then All Company will still not be connected to an Office 365 Group after this change.

![Office 365 Identity Enforcement](../media/710d82b4-a6fa-43bf-b609-8f2fc80fab52.png)

## If the All Company community is connected, what should I be aware of?

- All Company can be deleted in AAD. It will go through soft-delete and then hard-delete like other communities.
- The Office 365 Expiration policy is now enabled for All Company when connected.
- Privacy and Data Classification for All Company can be changed in AAD but if the privacy is set to private for All Company, users will no longer be able to post or view the All Company group.

## How do these changes to All Company affect my existing SharePoint web part and embed scenarios? 

Now that we have made All Company like other Yammer communities, if you are currently using All Company in a SharePoint web part or embed scenario, you will now see an empty All Company feed. All you must do to start seeing your All Company feed again is to re-add the All Company community.  

For more information about the various SharePoint web parts and embed features, see [Use a Yammer web part in SharePoint Online](https://support.microsoft.com/office/a53cfa0c-3d09-42c8-a286-1038a81c59da). 

## Related articles

[Is my Yammer community or group connected to Office 365?](https://support.office.com/article/is-my-community-or-group-connected-to-microsoft-365-f592296f-4158-43d8-b711-d77c35db826e)

[Yammer and Office 365 Groups](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups?redirectSourcePath=%252farticle%252fd8c239dc-a48b-47ab-b85e-6b4b8191a869)

[Restrict All Company posts in Yammer](https://support.office.com/article/3219d2ae-db15-4c9f-9dd2-28559ae39a97)

[Use a Yammer web part in SharePoint Online](https://support.microsoft.com/office/a53cfa0c-3d09-42c8-a286-1038a81c59da)



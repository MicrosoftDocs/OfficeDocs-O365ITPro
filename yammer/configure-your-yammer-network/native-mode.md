---
title: "Prepare a Yammer network for Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 12/19/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn the steps required to prepare your Yammer network for Native Mode for Microsoft 365."
ROBOTS: NOINDEX, NOFOLLOW 
---

# Configure your Yammer network for Native Mode for Microsoft 365

## Requirements for Native Mode

Native Mode has the following requirements:

- There can only be one Yammer network on the tenant.

- Office 365 identity must be enforced on the Yammer network.

- All domains on the tenant are associated with the Yammer network, and there are no domains on the Yammer network that are not on the tenant.

- All Yammer files must be [stored in SharePoint](https://go.microsoft.com/fwlink/?linkid=2111253).

- Retention mode in Yammer is set to Archive.

- All users must be in Azure Active Directory ("AAD"). AAD enforces Office 365 identity and, any users who are not mapped to the network, must be deleted.

- There cannot be any unlisted private groups.

- All existing groups must be Office 365 connected.

- There cannot be any external groups. Support for external groups is planned but is not available with the initial release of Native Mode.

- There cannot be any network-level or thread-level guests.

## How does the Tool work with your network?

The Tool prepares your network for Native Mode by disabling some features and mitigating previously created instances of those features. Those changes include:

- Any unlisted private groups in your network will be changed to private listed groups. Users will no longer be able to create unlisted private groups.

- External groups in Yammer will no longer be supported, all external groups will be made internal only, and any external users in those groups will no longer have access to the group or its contents. Support for Azure B2B-based external groups is expected at a later date.

- Adds the Global admin to unconnected groups that either have no owners at all or that have no owner with Office 365 Group creation rights. It does not add them to unconnected groups if the owner does have Office 365 Group creation rights.

- Connects all unconnected Yammer groups after applying the changes mentioned in the previous three bulleted items above.

- Prevents files from being uploaded in Yammer Private messages, and deletes all files previously uploaded in Yammer Private messages.

- Deletes all internal users (and their associated files and Private messages) in the network who are not mapped to an Office 365 identity in AAD.

- Disables support for guests in the network, and removes existing guests from the network, along with their associated Private messages and files.

- Disables support for adding an external user to an individual thread. External users who were previously added to individual threads will no longer have access.

- Deletes all group messages and files for previously deleted groups. Going forward, group messages will be deleted consistent with your network's retention policy.

- Locks your network into Native Mode.

- Begins ingesting your data into the Security & Compliance Center to support eDiscovery.

>[!CAUTION]
> Once you have started alignment through the Tool, the change is **irreversible**.
> Notify users *before* you run the Alignment Tool about the above changes so that they are prepared and not surprised.

## While the tool is running

- Group updates will not work on unconnected groups.

## Related articles

[Overview of Native Mode](overview-native-mode.md)

[Yammer files in Native Mode for Microsoft 365](files-in-native-mode.md)

[Troubleshoot problems with Native Mode for Microsoft 365](../troubleshoot-problems/troubleshoot-native-mode.md)

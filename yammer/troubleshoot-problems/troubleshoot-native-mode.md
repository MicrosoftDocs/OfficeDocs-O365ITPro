---
title: "Troubleshoot your Yammer network for Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 11/15/2019
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

# Troubleshoot problems with Native Mode for Microsoft 365

## What end users can expect during migration

We recommend you communicate the change to Native Mode to your end users. Early communication will prevent surprises, such as the inability to invite guests, add files to private messages, or create non-connected groups.

### Some ideas to include in your communications

We are getting our Yammer network ready to support required compliance and security policies for our organization. Here are some changes you will see rolling out over the next few weeks:

- All unlisted private groups will be listed on __/__/__. Non-members will be able to see the group in search results and other areas, but only members can access the content. If you don't want your group listed, delete it before that date. You can also change the name of the group if the concern is that people will identify the purpose of the group based on the name.

- All network, group, and conversation-level guests from our Yammer network will be removed on __/__/__. We will send each guest an explanation.

- All Yammer group files will be stored in SharePoint on __/__/__.

- All files that were previously uploaded on Yammer private messages will be deleted on __/__/__. No new files will be uploaded in Yammer private messages. This change does not impact file uploads in Teams chats.

#### During the migration

Users can create new files from Yammer, edit existing Yammer files that are stored in SharePoint, and upload new versions of files that are already stored in SharePoint.

#### After migration

- All files will be stored inside of SharePoint [How do I tell where my Yammer files are being stored](https://go.microsoft.com/fwlink/?linkid=2111253), providing a consistent file management experience.

- File search can happen from SharePoint as well as Yammer. Yammer search searches the first 5000 characters of files in Azure cloud storage as well as the title and author, but only searches the title and author of files stored in SharePoint.

## Questions and answers about general issues

### How does a network enter Native Mode for Microsoft 365

**New Networks**
After December 2019, all new networks will begin in Native Mode. This means they will have a different feature set than existing customers as there are some existing features that cannot be supported by Azure Active Directory (AAD).

**Existing Networks**
Existing networks will be able to lock themselves in to Native Mode by using the Microsoft 365 Alignment Tool to mitigate any areas where their network is incompatible with the feature set of Native Mode.

### Is it possible for a Native Mode network to revert back to its previous state

No. Once an IT admin commits their Yammer Enterprise network to Microsoft 365 Native Mode, it will stay that way permanently.

### What is the main difference between Native Mode and eDiscovery

- *Native Mode* - A state where all the users, groups, and content from your network are compatible with (and mapped to) their counterparts in AAD/Office 365.

- *eDiscovery* - A feature Microsoft provides to customers through the [Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321).  

Yammer can offer eDiscovery to customers once all their Users, Groups, and Content can be discoverable through the Security and Compliance Center. To facilitate this process, Yammer must ensure that all Groups are Office 365 connected because eDiscoverable content must be saved in the group mailbox. Similarly, Users must have a mailbox so we can store their private conversations, and Files must be saved in SharePoint, so they can be accessed by the eDiscovery tools.

### What are the main features of a Native Mode network

A network must be able to synchronize its full domain with AAD, which means . . .

- There can only be one home network on the Office 365 tenant.
- All domains on the tenant are associated with the Yammer network.
- All domains on the Yammer network are associated with the tenant.

All users must be in AAD, which means . . .

- Office 365 Identity must be enforced in the home network.
- No Network Level Guests in the network.
- No Group Level Guests in the network because those users do not currently map to users in AAD.
- No (flexternal) Thread-level Guests.
- No inactive unmapped users (for example, a user with Yammer authentication who was not deleted when they left the organization).

All groups must be connected, which means . . .

- Only users with Office 365 Group Creation Rights can create groups in Yammer.
- No Yammer group can be created until we can ensure the group is connected.
- No Unlisted (or secret) Groups or External Groups, because those groups are not currently connectable.

### What are the flags associated with Native Mode for Microsoft 365

- Microsoft 365 native flag - An umbrella flag that will set all the rest of the flags in this list. Best practice is for IT admins to control changes in a specific feature area rather than using this all-purpose flag.
- All new groups must be connected - When this flag is set:
  - Users who do not have Office 365 Group Creation Rights should not see any features in the product to create a new group.
  - Groups in networks should not create the Yammer group before confirming the Office 365 group can be (or has been) created.
  - Groups outside of or not connected to networks will not experience any change.
- All Company group is connected - When this flag is set, All Company group will be eligible for features such as, Town Hall and Files in SharePoint.
- No difference between membership and adminship - When this flag is set, both Yammer and AAD will have the same membership and adminship capabilities for the group with respect to users who have AAD accounts.
- No secret groups - When this flag is set, new secret groups cannot be created. This is true whether creating a new group or making an existing unconnected group secret. There will be no change to existing secret groups.
- No external groups in the network - When this flag is set, new external groups cannot be created. There will be no change to existing external groups.
- No network-level guests - When this flag is set, new Network Level Guests (NLGs) cannot be added to or invited to join a network. There will be no change to existing NLGs.
- No Block Files in private messages - When this flag is set, it blocks any communication with these users for group or private messages.
- No uploads in private messages - When this flag is set, users will not be able to upload new files in private messages in Yammer. This flag will not prevent users from adding links to cloud files. There will be no impact on files that were previously uploaded in private messages on Yammer, which is controlled by a separate flag (below).
- No access to previously uploaded files in private messages - When this flag is set, user cannot access files previously attached in private messages.

### How are M365 Native Mode flags expected to behave

The flags associated with Microsoft 365 Native mode are intended to be independent and to control individual features. They should not have any dependencies with other flags. The flags are also intended to prevent new occurrences of an issue; they are not intended to eliminate pre-existing issues. For example, the flag for secret groups will not eliminate existing Secret Groups, though it will prevent someone from creating new Secret Groups. IT admins can use the Microsoft 365 Alignment Tool to address previously existing issues.

### Why are there separate flags for each feature

As IT admins mitigate an issue, we wanted to provide them with a way to "lock down" an area of the network so they can move on to the next issue without fear that the first issue will resurface as users once again create Secret Groups, External Groups, etc.

### Does every Yammer user need a SharePoint license

No. Only one person in your organization needs a SharePoint license.

### File metadata

When files are moved to the SharePoint document library:

- Only the latest version is moved over, and the version history is not copied.

- Users can no longer mark a file as official.

- Files are marked as having been migrated to SharePoint.

### File name conflicts

When migration completes, the IT admin gets a report of any file name conflicts, and how they were handled.

You won't be able to take your network to Native Mode for Microsoft 365 until you resolve any files left behind.

## Related articles

[Overview of Native Mode](../configure-your-yammer-network/overview-native-mode.md)

[Configure your Yammer network for Native Mode for Microsoft 365](../configure-your-yammer-network/native-mode.md)

[Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321)

[Manage Yammer data compliance](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md)

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

## End-user experience during migration

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

- All files will be stored inside of SharePoint [How do I tell where my Yammer files are being stored](https://support.office.com/en-us/article/how-do-i-tell-where-my-yammer-files-are-being-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443), providing a consistent file management experience.
- File search can happen from SharePoint as well as Yammer. Yammer search searches the first 5000 characters of files in Azure cloud storage as well as the title and author, but only searches the title and author of files stored in SharePoint.

#### Does every Yammer user need a SharePoint license

No. Only one person in your organization needs a SharePoint license.

#### File metadata

When files are moved to the SharePoint document library:

- Only the latest version is moved over, and the version history is not copied.
- Users can no longer mark a file as official.
- Files are marked as having been migrated to SharePoint.

#### File name conflicts

When migration completes, the admin gets a report of any file name conflicts, and how they were handled.

You won't be able to take your network to Native Mode for Microsoft 365 until you resolve any files left behind.

## Related articles

[Overview of Native Mode for Microsoft 365](overview-native-mode.md)
[Configure your Yammer network for Native Mode](native-mode.md)
[Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321)
[Manage data compliance in Yammer](manage-data-compliance.md)
[Enforce Office 365 identity](enforce-office-365-identity.md)

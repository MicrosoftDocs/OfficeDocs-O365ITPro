---
title: "Prepare a Yammer network for Native Mode for Microsoft 365"
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
# Configure your Yammer network for Native Mode for Microsoft 365

## Requirements for Native Mode

The Microsoft 365 Alignment Tool (“Tool”) will make sure your network meets the following requirements:

- There can only be one Yammer network on the tenant.
- Office 365 identity must be enforced on the Yammer network.
- All domains on the tenant are associated with the Yammer network, and there are no domains on the Yammer network that are not on the tenant.
- All Yammer files must be [stored in SharePoint](https://go.microsoft.com/fwlink/?linkid=2111253).
- Soft delete must be turned on in Yammer.
- All users must be in Azure Active Directory (AAD). AAD enforces Office 365 identity and, any users who are not mapped to the network must be deleted.
- You must not have any unlisted private groups.
- All existing groups must be Office 365 connected.
- You must not have any external groups. Support for external groups is planned but is not available with the initial release of Native Mode.
- You must not have any network-level or thread-level guests.

## How does the Tool work with your network

The Tool prepares your network for Native Mode by disabling some features and mitigating previously created instances of those features. Those changes include:

- Any unlisted private groups in your network will be changed to private listed groups. Users will no longer be able to create unlisted private groups.
- External groups in Yammer will no longer be supported, all external groups will be made internal only, and any external users in those groups will no longer have access to the group or its contents. Support for Azure B2B-based external groups is expected to be supported at a later date.
- Adds the Global admin who runs the Tool as a group owner in any unconnected groups, so that those groups can become Office 365 connected groups.
- Connects all unconnected Yammer groups after applying the changes mentioned in the previous three bulleted items above.
- Prevents files from being uploaded in Yammer private messages, and deletes all files previously uploaded in Yammer Private messages.
- Deletes all internal users and their associated files and private messages in the network who are not mapped to an Office 365 identity in AAD.
- Disables support for guests in the network, and removes existing guests from the network, along with their associated private messages and files.
- Disables support for adding an external user to an individual thread. External users who were previously added to individual threads will no longer have access.
- Deletes all group messages for deleted groups and begins deleting all group messages whenever a group is deleted.
- Locks your network into Native Mode.
- Begins transferring your data into the Security & Compliance Center.

>[!IMPORTANT]
> Once you are in Native Mode, or have started the file migration process, you can't go back.
> Notify users that files will be deleted and files in private messages might disappear.

## What happens when you start the Tool

In Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having one consistent location for files makes them easier to access for both end users and admins.

1. Export files stored in Azure. Make sure you export and verify all files stored in Azure before starting the Tool.
2. Download the User and Group Activity Report, which provides a list of all files that will be migrated to SharePoint from Azure and automatically deleted from Azure cloud storage files within 30 days after the Tool completes its work.

>[!NOTE]
> Only the latest version of the file is migrated to SharePoint from Azure, and the version history is not copied.
> The follower count is not copied.
> Users can no longer mark files as official.

## To prepare files for migration

To use Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having files in SharePoint makes admins and end user usage and management easier.

As part of this migration:

- Files in Azure will be deleted, including files in Private messages.
- Users will no longer be able to upload files to Private messages. Link sharing will still be available.

### Before migration
Because migration deletes files and the process is irreversible, you need to decide how to handle these files. We recommend you:

- Export the files before migration and save them in case anyone asks for them.
- [Update to the latest versions](https://go.microsoft.com/fwlink/?linkid=2111082) of Yammer Android, Yammer iOS, and Yammer Desktop apps, as older versions will have issues uploading files to SharePoint.
- Use new APIs to upload files. The previous versions will be blocked and the file upload won’t work.
- Notify users that this migration is going to happen.
- Notify users that they may notice files in Private messages might disappear during this process.

### During migration

#### Admin experience



#### End user experience
|
### After migration*
You can learn more about what happens after the files have been migrated (see [How do I tell where my Yammer files are being stored](https://go.microsoft.com/fwlink/?linkid=2111253).

## To configure your network to Native Mode:*

1. In the Yammer admin center, go to **Network Admin** > **Configure** > **Microsoft 365 Alignment Tool**. You must be an Office 365 Global Admin and a Verified Admin in Yammer to run the Native Mode for Microsoft 365 Alignment Tool.
2. Start the Microsoft 365 Alignment Tool and export all files in Azure Data Storage.
3. Download the User and Group Activity Report to see how many files will be migrated and how many will be deleted.
4. When your export is complete, start the migration within the Tool.
  a. You can start migration while you export files, but the export data may be inaccurate.
5. Once the Tool has completed its work, review the reports and determine if other steps are necessary before your network can be in Native Mode for Microsoft 365.
  a. SLA – up to 30 days for networks with < 100,000 files
  b. SLA – up to 45 days for networks with > 100,000 files

## See also

[Overview of Native Mode](overview-native-mode.md)

[Troubleshooting your Yammer network in Native Mode](troubleshoot-native-mode.md)

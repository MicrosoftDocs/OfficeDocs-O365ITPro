---
title: "Prepare a Yammer network for Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 12/13/2019
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

**How does the Tool work with your network?**

The Tool prepares your network for Native Mode by disabling some features and mitigating previously created instances of those features. Those changes include:

- Any unlisted private groups in your network will be changed to private listed groups. Users will no longer be able to create unlisted private groups.

- External groups in Yammer will no longer be supported, all external groups will be made internal only, and any external users in those groups will no longer have access to the group or its contents. Support for Azure B2B-based external groups is expected at a later date.

- Adds the Global admin to unconnected groups that either have no owners at all or that have no owner with Office 365 Group Creation Rights. It does not add them to unconnected groups if the owner does have Office 365 Group creation rights.

- Connects all unconnected Yammer groups after applying the changes mentioned in the previous three bulleted items above.

- Prevents files from being uploaded in Yammer Private messages, and deletes all files previously uploaded in Yammer Private messages.

- Deletes all internal users (and their associated files and Private messages) in the network who are not mapped to an Office 365 identity in AAD.

- Disables support for guests in the network, and removes existing guests from the network, along with their associated Private messages and files.

- Disables support for adding an external user to an individual thread. External users who were previously added to individual threads will no longer have access.

- Deletes all group messages for deleted groups and begins deleting all group messages whenever a group is deleted. There are two separate things that happen. It hard deletes group messages from previously deleted groups. When groups are deleted after the network is in Native Mode, group messages are deleted, based on the Archive retention setting. This means it is deleted from the user experience, but it will be available through data export. This may lead you to ask, Why would we hard delete the messages from previously deleted groups, but then "archive" the one from newly-deleted groups? It is because there is no place for us to store the messages for eDiscovery if the group was deleted before Native Mode. If they are deleted after Native Mode, the Security and Compliance Center has a place to store and keep the messages.

- Locks your network into Native Mode.

- Begins transferring your data into the Security & Compliance Center.

>[!CAUTION]
> Once you are in Native Mode, or have started the file migration process, it is irreversible.
> Notify users *before* you run the Alignment Tool that files in Private messages in Yammer **will be deleted** and no longer accessible, so they should download any important files before the Tool is run.

## While the tool is running

- Group updates will not work on unconnected groups.
- File edits will not work on files not in SharePoint.

## What happens when you start the Tool

In Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having one consistent location for files makes them easier to access for both end users and admins.

1. Export files stored in Azure. Make sure you export and verify all files stored in Azure before starting the Tool.

2. Download the **User and Group Activity Report**, which provides a list of all files that will be migrated to SharePoint from Azure and automatically deleted from Azure cloud storage files within 30 days after the Tool completes its work. If a group has been deleted, all the files from that group will be deleted and not migrated over.

>[!NOTE]
> Only the latest version of a file is migrated to SharePoint from Azure, and the version history is not copied.
> The follower count is not copied.
> Users can no longer mark files as official.

### As a result of migration

- Private message files in Azure will be deleted. Azure group files from active groups are first copied to SharePoint, all references to files are updated to the SharePoint location, then we delete the Azure files.

- Users will no longer be able to upload files to Private messages. Link sharing will still be available.

- All files in Private messages will be deleted, group files will be copied to SharePoint, and then deleted from Azure *within 30 days of migration*.

### Before migration

Because migration deletes files and the process is irreversible, you need to decide how to handle these files. 

We recommend you:

- Export the files before migration and save them in case anyone asks for them.

- [Update to the latest versions](https://go.microsoft.com/fwlink/?linkid=2111082) of Yammer Android, Yammer iOS, and Yammer Desktop apps, as older versions will have issues uploading files to SharePoint.

- To use Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having files in SharePoint makes admins, and end user usage and management easier.

- Use new third-party APIs to upload files. The previous versions will be blocked and the file upload won’t work.

- Notify users that this migration is going to happen.

- Notify users before you run the Alignment Tool that files in Private messages in Yammer will be deleted, and no longer accessible.

### During migration

- Users can create new files from Yammer, edit existing Yammer files that are stored in SharePoint, and upload new versions of files that are already stored in SharePoint.

- If a group has been deleted, all the files from that group will be deleted and not migrated over.

#### Admin user experience

1. Start the **Microsoft 365 Alignment Tool** and export all files in Azure Data Storage.

2. Download the **User and Group Activity Report** to see how many files will be migrated and how many will be deleted. The report will indicate how many Private message files each user has and also how many Yammer files and SharePoint files each group has. All the[Private message files will be deleted, and we will move the Yammer files to SharePoint. Learn more about [Private message files](https://docs.microsoft.com/yammer/manage-security-and-compliance/monitor-private-content).

   - Identify if there needs to be action taken on any of the items.

3. When your export is complete, start the migration from the **Microsoft 365 Alignment Tool**.

   - You can start migration when export is running, but the export data may be inaccurate.

4. Once Microsoft 365 Alignment Tool has completed its work, review the  reports and determine if other steps are necessary before your network can be in Native Mode for Microsoft 365.

   - SLA - up to 30 days for networks with < 100K files

   - SLA - up to 45 days for networks with > 100K files

#### End user experience

The following is the expected behavior if a user performs these tasks while the Tool is running:

|Tasks|Office 365 Yammer Groups|Unconnected Yammer Groups|Private Messages|
|-----|------------------------|-------------------------|----------------|
|Delete files|User can delete files.|File will be deleted and not migrated to SharePoint.|Files will be deleted and users will no longer have access to these files.|
|Edit file|Edited files will be stored in SharePoint.|Only the latest file will be migrated to SharePoint. If a user edits a file during migration, there is a chance of data loss. Old versions are no longer accessible in SharePoint.|N/A|
|New file|New files are stored in SharePoint.|File will be in Azure, but migrated to SharePoint by the time the Tool has completed its work.|N/A|
||||

### After migration

- All group files will be [stored in SharePoint](https://go.microsoft.com/fwlink/?linkid=2111253),providing a consistent file management experience.

- File search can happen from SharePoint as well as Yammer. Yammer searches the first 5000 characters of files in Azure cloud storage as well as the title and author, but only searches the title and author of files stored in SharePoint.

## Related articles

[Overview of Native Mode](overview-native-mode.md)

[Troubleshoot problems with Native Mode for Microsoft 365](../troubleshoot-problems/troubleshoot-native-mode.md)

---
title: "Prepare files in Yammer for Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFloreanoGoertz
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn how to move all Yammer files to SharePoint, part of the requirements for using Native Mode for Microsoft 365."
ROBOTS: NOINDEX, NOFOLLOW 
---

# Prepare files in Yammer for Native Mode for Microsoft 365

To use Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having one consistent location for files makes usage easier for both end-users and admins:

- **End-users** follow the same processes with all files in all groups, including the ability to add conditional access policies on specific files.

- **Admins** can use the same security and compliance tools for Yammer as they do with the rest of Office 365 including eDiscovery, have a consistent way to export all files, and simplify complying with GDPR requests. 

The Microsoft 365 Alignment Wizard does the following file-related steps:

1. Provides a link to download the **User and Group Activity Report**, which lists the number of files to be moved for each group and the files to be deleted.

2. Copy all Yammer group files from Azure cloud storage to the SharePoint document library for the group, and automatically delete the Azure cloud storage files 30 days after the wizard completes.

3. Delete all Yammer files that were attached to private messages. 
 
>[!IMPORTANT]
> After migration has been started, it can't be stopped or reversed.

## Decisions needed

Because migration deletes all files from private messages, you need to decide how to handle these files. The options are to:

- Notify users that the files will be deleted. The wizard will delete the files, and they will no longer be available.

- Export the files before migration and save them in case anyone asks for them.

- Export the files before migration, and send the files to the person who posted them, letting them know the files are no longer available on Yammer. 

## Recommended process

1. Start the Microsoft 365 Alignment Wizard and download the User and Group Activity Report to see how many files will be moved and how many will be deleted.

2. Export files from private messages if these files need to be saved. For steps, see [Export data from Yammer Enterprise](../manage-security-and-compliance/export-yammer-enterprise-data.md).

3. Optional. Export all files from all groups that have been stored in Yammer to provide a backup of the files. 

4. When your backup is complete, start the migration from the Microsoft 365 Alignment Wizard. You can start migration when export is running, but the export data may indicate certain files are in SharePoint due to the migration.

5. Review the Microsoft 365 Alignment Wizard to determine if other steps are necessary before your network can be in Native Mode for Microsoft 365.

## Admin experience during migration

Migration status can be viewed on the Network Alignment Wizard page. You can track:

- How many groups where file migration was successful, partial, or unsuccessful.

- How many files where the filename was changed due to a file name conflict.

Most migrations complete within 72 hours.

## End-user experience during migration

During the migration, users can create new files from Yammer, edit existing Yammer files that are stored in SharePoint, and upload new versions of files that are already stored in SharePoint. Users won't be able to delete files stored in Azure cloud storage once migration has started.

After migration:

- All files will be stored in SharePoint, providing a consistent file management experience.

- If users want to search the content of files, they'll need to go to the SharePoint site or document library for an individual group and use the Search bar at the top of the page, or use content search from the organization's SharePoint site.

    Yammer search searches the first 5000 characters of files in Azure cloud storage as well as the title and author, but only searches the title and author of files stored in SharePoint. 

## File metadata

When files are copied to the SharePoint document library:

- Only the latest version is moved over, and the version history is not copied.

- The follower count is not copied.

- Users can no longer mark a file as official.

- Files are marked as having been migrated to SharePoint.
 
## File name conflicts

When migration completes, the admin gets a report of any file name conflicts, and how they were handled:

- If a file with the same name already exists in the SharePoint document library, we append \_*date* to the file name.

- If a filename includes invalid characters, we update the file name to remove the invalid characters.

- If a file can't be migrated for any reason, we retry once, and continue the migration. You won't be able to take your network to Native Mode for Microsoft 365 until you resolve any files left behind.

## FAQ

**Q: Does every Yammer user need a SharePoint license?**

A: No. Only one person in your organization needs a SharePoint license.

## See also

[Prepare a Yammer network for Native Mode for Microsoft 365](native-mode.md)

[Enforce Office 365 identity in Yammer](enforce-office-365-identity.md)


---
title: "Files in Native Mode"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 01/21/2020
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn the steps required to prepare your Yammer network for Native Mode for Microsoft 365."
---

# Yammer files in Native Mode for Microsoft 365

In Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having one consistent location for files makes them easier to access for both end users and admins.

## What happens to files in private messages when you run the Native Mode Alignment Tool ("Tool")?

- Users will no longer be able to upload files to Private messages. Link sharing will still be available.

- All files in Private messages will be deleted.

## What happens to Group files when you run the Native Mode Alignment Tool ("Tool")?

- Group files that are in Azure are copied to SharePoint Document Library (SDL) for the group.
- After group files are successfully copied to SharePoint, we delete the non-SharePoint version of the files.
- All files for groups that were previously deleted will be deleted.
- New files will always be uploaded to SharePoint.
- Non-SharePoint group files will deleted *within 30 days* after the migration is completed.
- For any group containing multiple files with the same name, the duplicate-named files will be appended with _X, where X is an increasing number for each duplicate named file (for example, file_1 file_2 file_3 and so on).

## File renaming rules

- Characters not supported in SharePoint will be replaced with an underscore '_'.
- Duplicate files or those with names that already exist in SharePoint will be renamed using the following format: filename_yammerFileID_extension.
- Files with a blank space as the first or last character as well as files that end with a period will have those characters removed.
- Unnamed files will be named according to the following format: "Yammer File", "Yammer File (2)", "Yammer File (3)", and so on.
- Files with names starting with \~$ will have the leading tilde removed, for example: "~$Yammer File" will be renamed to "$Yammer File".
- Files with names containing _vti_ anywhere in the name will have it replaced with - vti-, for example: "Yammer_vti_File" will be renamed to "Yammer-vti-File".
- Files named .lock, CON, PRN, AUX, NUL, COM0 - COM9, LPTO - LPT9, or desktop.ini will have "__file" appended to the name, for example: "COM0" will be renamed to "COM0_file". 

## Before running the tools

Because migration deletes files and the process is irreversible, we suggest you:

- Export the files before running the Tool and save them in case anyone asks for them.

- Update to the latest versions of Yammer Android, Yammer iOS, and Yammer Desktop apps, as older versions will have issues uploading files to SharePoint.

- If third-party APIs are used to upload files, use the [latest version of Upload files into Yammer groups](https://developer.yammer.com/v1.0/docs/upload-files-into-yammer-groups). The previous versions will be blocked and the file upload won’t work.

- Notify users that this migration is going to happen, and that files in Yammer private messages will be deleted, and no longer accessible. Only the latest version of the file is migrated to SharePoint, and the previous versions are not copied. The follower count is not copied. Users can no longer mark files as official.

## Admin step-by-step experience

1. Export all files. Learn more about how to [Export Yammer Enterprise data](../manage-security-and-compliance/export-yammer-enterprise-data.md#find-and-delete-specific-messages-or-files).

2. Start the **Microsoft 365 Alignment Tool**.

3. Download the **Alignment Report**, which provides details on the files that each user and group has.

   - Each user has a count for the total number of private message files. These files will be deleted after running the Tool.
   - Each group has a count of Yammer and SharePoint files. We will attempt to migrate all the Yammer files to SharePoint. There will be no impact to existing SharePoint files.

4. Authorize and run the Tool.

   - SLA - up to 30 days for networks with < 100K files
   - SLA - up to 45 days for networks with > 100K files

5. Once Microsoft 365 Alignment Tool has completed, review the Error Report and determine if other steps are necessary before your network can be in Native Mode for Microsoft 365.

### End user experience

The following is the expected end user experience for files while the Tool is running:

|Tasks|Microsoft 365 Yammer Groups|Unconnected Yammer Groups|Private Messages|
|-----|------------------------|-------------------------|----------------|
|Delete files|User can delete files|File will be deleted and not migrated to SharePoint.|Files will be deleted and users will no longer have access to these files.|
|Edit file|Edited files will be stored in SharePoint|Only the latest file will be migrated to SharePoint. If a user edits a file during migration, there is a chance of data loss. Old versions are no longer accessible in SharePoint.|N/A|
|New file|New files are stored in SharePoint|File will be in Azure, but migrated to SharePoint by the time the Tool has completed its work.|N/A|
||||

If a group has been deleted, all the files from that group will be deleted and not migrated over.

## After successfully entering Native Mode

- All group files will be [stored in SharePoint](https://go.microsoft.com/fwlink/?linkid=2111253), providing a consistent file management experience.

- File search can happen from SharePoint as well as Yammer. Yammer searches the first 5000 characters of files in Azure cloud storage as well as the title and author, but only searches the title and author of files stored in SharePoint.

> [!NOTE]
> If you receive an error code during the alignment process for Native Mode, you can refer to the [Error Codes section in the Troubleshooting Native Mode topic](../troubleshoot-problems/troubleshoot-native-mode.md#error-codes) for more information.

## Related articles

[Overview of Native Mode](overview-native-mode.md)

[Troubleshoot problems with Native Mode for Microsoft 365](../troubleshoot-problems/troubleshoot-native-mode.md)

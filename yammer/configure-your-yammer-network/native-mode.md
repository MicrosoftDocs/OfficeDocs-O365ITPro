---
title: "Prepare a Yammer network for Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 11/15/19
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

A Yammer network is in one of three modes:

- **Native Mode for Microsoft 365**. In this mode, the network only uses features that allow users, groups, and content to be compatible with and mapped to their counterparts in Azure Active Directory (AAD) and Office 365.

    This mode is required in order for Yammer content to be discoverable in the Office Security & Compliance Center.

    In this mode, users and admins can't add features which would take the network out of Native Mode.

- **Hybrid mode**. In this mode, a network is enabled to map users, groups, and content to their counterparts in AAD and Office 365, but that is not required. The network may be in process of meeting all requirements for Native Mode, but the admin hasn't committed the network to Native Mode.

- **Non-connected mode**. In this mode, one or more requirements for Native Mode are not met. For example, the network may not enforce Office 365 identity. All external networks and Yammer Basic networks are in this mode, as they can't be connected to Office 365.

All *new* Yammer Enterprise networks created after November 2019 will be created in Native Mode.

For *existing* Yammer networks created before November 2019, admins can choose the mode. The Microsoft 365 Alignment Wizard automates the process of converting your network to Native Mode and guides you through the rest of the steps.

The Microsoft 365 Alignment Wizard prepares your network for Native Mode by restricting what can be done in your network to only things that can be associated with Office 365 and Azure Active Directory, and then locking your network into Native Mode when that work has been successfully completed. It does this by both preventing new instances of the incompatible item, and by mitigating existing items to be compliant.

You can either allow the wizard to do all changes for you, or mitigate some issues yourself prior to running the second part of the wizard.

To start the wizard, in the Yammer admin center, go to **Network Admin > Configure > Microsoft 365 Alignment Tool**. You must be an Office 365 Global Admin and a Verified Admin in Yammer to run the Native Mode for Microsoft 365 Alignment Wizard.

## Requirements for Native Mode

The Microsoft 365 Alignment Tool (“Tool”) will make sure your network meets the following requirements:

- There can only be one Yammer network on the tenant.
- Office 365 identity must be enforced on the Yammer network.
- All domains on the tenant are associated with the Yammer network, and there are no domains on the Yammer network that are not on the tenant.
- All Yammer files must be stored in SharePoint.
- Soft delete must be turned on in Yammer.
- All users must be in Azure Active Directory (AAD). AAD enforces Office 365 identity and, any users who are not mapped to the network must be deleted.
- You must not have any unlisted private groups.
- All existing groups must be Office 365 connected.
- You must not have any external groups. Support for external groups is planned but is not available with the initial release of Native Mode.
- You must not have any network-level or thread-level guests.

## What the Tool does to your network

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

## To prepare files for migration

All new networks after November 2019 are Native Mode, and we are working to have all Yammer networks converted to Native Mode.

To use Native Mode for Microsoft 365, all Yammer files must be stored in SharePoint. Having one consistent location for files makes usage easier for both admins and end-users:

- Admins can use the same security and compliance tools for Yammer as they do with the rest of Office 365. The tools, including eDiscovery, have a consistent way to export all files and simplify complying with GDPR requests.
- End-users follow the same processes with all files in all groups, including the ability to add conditional access policies on specific files.

The Microsoft 365 Alignment Tool performs the following file-related steps:

1. In the Yammer admin center, go to Network Admin > Configure > Microsoft 365 Alignment Tool. You must be an Office 365 Global Admin and a Verified Admin in Yammer to run the Native Mode for Microsoft 365 Alignment Tool.
2. Download the User and Group Activity Report, which lists the number of files to be moved for each group and the files to be deleted.
3. Copy all Yammer group files from Azure cloud storage to the SharePoint document library for the group, and automatically delete the Azure cloud storage files 30 days after the Tool completes its work.
4. Delete all Yammer files that were attached to private messages.

Because migration deletes all files from private messages, you need to decide how to handle these files. Here are your options:

- Notify users that the files will be deleted. The Tool will delete the files, and they will no longer be available.
- Export the files before migration and save them in case anyone asks for them.
- Export the files before migration and send the files to the person who posted them, letting them know the files are no longer available on Yammer.
- Start the Microsoft 365 Alignment Tool and download the User and Group Activity Report to see how many files will be moved and how many will be deleted.
- Export files from private messages if these files need to be saved. For steps, see Export data from Yammer Enterprise.
- Optional. Export all files from all groups that have been stored in Yammer to provide a backup of the files.
- When your backup is complete, start the migration from the Tool. You can start migration when the export is running, but the export data may indicate certain files are in SharePoint due to the migration.
- Review the Tool to determine if other steps are necessary before your network can be in Native Mode for Microsoft 365.

## To configure your network to Native Mode

1. In the Yammer admin center, go to Network Admin > Configure > Microsoft 365 Alignment Tool. You must be an Office 365 Global Admin and a Verified Admin in Yammer to run the Native Mode for Microsoft 365 Alignment Tool.
2. Start the Microsoft 365 Alignment Tool, which will identify the areas to address to enter Native Mode for Microsoft 365.
3. Download the report to see more detail than is shown in the Tool.
4. For each issue that you don't want the default action taken, mitigate existing instances of the issue yourself. For example, there may be some unlisted private groups that you or the owner would prefer to have deleted rather than making them a private listed group.
5. When you're ready for the Tool to address each issue, click Next.
6. Refresh the Tool page to check the status of each issue. Some tasks will complete very quickly, while others, like file migration, may take more time, depending on the size and complexity of your network.
7. When the Tool completes configuring your network, on the Commitment screen, enter your user ID to commit to Native Mode.

## See also

[Overview of Native Mode](overview-native-mode.md)

[Troubleshooting your Yammer network in Native Mode](troubleshoot-native-mode.md)

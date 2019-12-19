---
title: "Overview of Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn about Native Mode for Microsoft 365."
---

# Overview of Native Mode

As of December 2019, all new Yammer Enterprise networks start in Native Mode.

For existing Yammer networks, they will be eligible to migrate to Native Mode (coming soon) and admins can choose which mode suits their network.

In Native Mode, all Yammer users are in Azure Active Directory (AAD), all groups are Office 365 Groups, and all files are stored in SharePoint Online.

A Yammer network must be in one of three modes:

- **Native Mode for Microsoft 365**. In this mode, the network only uses features that allow users, groups, and content to be compatible with and mapped to their counterparts in AAD and Office 365.

  When Yammer content is in Native Mode, you can search for it in the Office Security & Compliance Center.
  
  In this mode, users and admins can't add features that would take the network out of Native Mode.

- **Non-Native Mode**. In this mode, the network does not meet one or more requirements. For example, the network may not enforce Office 365 identity. All external networks and Yammer Basic networks are in this mode because they cannot connect to Office 365.

- **Hybrid Mode**. In this mode, users and groups may or may not be associated with their counterparts in AAD and Office 365, and files may or may not be stored in SharePoint. The network may be in the process of meeting all requirements for Native Mode, but the admin hasn't committed the network to Native Mode.

When you align your Yammer network in Native Mode, the Microsoft 365 Alignment Tool (“Tool”) automates the process and guides you through the steps to get there. The Tool prepares your network for Native Mode by:

- Restricting what can happen in your network to only things that can be associated with Office 365 and Azure Active Directory

- Locking your network into Native Mode when that work is complete. It does this by both preventing new instances of the incompatible item, and by mitigating existing items to be compliant.

 You can either allow the Tool to make all the changes or mitigate some issues yourself before running the second part of the Tool.

## Key differences between modes

### Native Mode

- No one can inadvertently take your network out of Native Mode
- (coming soon) eDiscovery through the [Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321) for your home network
- All Yammer groups and users are managed through Office 365
- Office 365 resources for each group
- All groups, including All Company, are Office 365-connected, which means they have access to Office 365 features, including live events
- Yammer honors Office 365 Group creation rights
- No external groups or network-level guests, but external networks are supported in the [US Geo](../manage-security-and-compliance/security-and-compliance.md)
- All files uploaded to groups will be stored in SharePoint
- Files cannot be uploaded to Yammer private messages
- Verified and Network Network Admins are required to have either Global Admin privileges or Group admin privileges from Microsoft 365 in order to administer changes to groups in which they are not a group owner

### Non-Native (not connected)

- External groups, network-level guests, and external networks are supported in the US Geo
- All Yammer users can create groups
- Files are not stored in SharePoint
- Files can be attached to Yammer private messages
- Verified and Network Network Admins are not required to have any additional admin privileges from Microsoft 365 in order to administer changes to groups

### Hybrid

- A step on the way to Native Mode that lets you understand how Native Mode will work.
- External groups, network-level guests, and external networks are supported in the US Geo
- All Yammer users can create groups
- New files uploaded to Office 365-connected groups are stored in SharePoint
- Files can be attached to Yammer private messages
- Verified and Network Network Admins are not required to have any additional admin privileges from Microsoft 365 in order to administer changes to groups

## Related articles

[Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321)

[Manage Yammer data compliance](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity for Yammer users](enforce-office-365-identity.md)

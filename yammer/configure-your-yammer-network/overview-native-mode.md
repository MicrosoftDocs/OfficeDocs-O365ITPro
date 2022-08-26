---
title: "Overview of Native Mode for Microsoft 365"
f1.keywords:
- NOCSH
ms.author: v-njeremy
author: djayneMSFT
manager: pamgreen
ms.date: 01/23/2020
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn about Native Mode for Microsoft 365."
---

# Overview of Native Mode

As of January 2020, all new Yammer Enterprise networks start in Native Mode.

Existing Yammer networks are eligible to migrate to Native Mode, and admins can choose which mode suits their network.

In Native Mode, all Yammer users are in Azure Active Directory (Azure AD), all groups are Microsoft 365 groups, and all files are stored in SharePoint Online.

> [!NOTE]Native Mode is strongly recommended for reasons of security, compliance, and M365 integration>

A Yammer network must be in one of three modes:

- **Native Mode for Microsoft 365**. In this mode, the network only uses features that allow users, groups, and content to be compatible with and mapped to their counterparts in Azure AD and Microsoft 365.

  When Yammer content is in Native Mode, you can search for it in the [Microsoft Purview compliance portal](https://go.microsoft.com/fwlink/?linkid=2132455).
  
  In this mode, users and admins can't add features that would take the network out of Native Mode.

- **Non-Native Mode**. In this mode, the network doesn't meet one or more requirements. For example, the network might not enforce Microsoft 365 identity. All external networks and Yammer Basic networks are in this mode because they can't connect to Microsoft 365 or Office 365.

- **Hybrid Mode**. In this mode, users and groups might not be associated with their counterparts in Azure AD and Microsoft 365 or Office 365, and files might not be stored in SharePoint. The network might be in the process of meeting all requirements for Native Mode, but the admin hasn't committed the network to Native Mode.

When you align your Yammer network in Native Mode, the [Native Mode Alignment Tool](./native-mode-step-by-step-guide.md) automates the process and guides you through the steps to get there. The Native Mode Alignment Tool prepares your network for Native Mode by:

- Restricting what can happen in your network to only things that can be associated with Microsoft 365 and Azure Active Directory

- Locking your network into Native Mode when that work is complete. It does this by preventing new instances of the incompatible item and by mitigating existing items to be compliant.

 You can either allow the Native Mode Alignment Tool to make all the changes or mitigate some issues yourself before running the second part of the Native Mode Alignment Tool.

 > [!NOTE]
> All Company now works like any other community in Native Mode. Admins can customize All Company and use advanced management features like restricting posts and promoting others as admins. See [All Company now works like other Yammer communities](../manage-yammer-groups/yammer-all-company-yammer-community.md) for more information.

## Key differences between modes

### Native Mode

- No one can inadvertently take your network out of Native Mode.
- eDiscovery through the [Microsoft Purview compliance portal](https://go.microsoft.com/fwlink/?linkid=2132455) for your home network.
- All Yammer groups, users, and group memberships are managed through Microsoft 365. Management should be done through the Microsoft 365 admin center, Azure AD admin portal, or other Azure AD management tools.
- Microsoft 365 resources for each group.
- All communities or groups, including All Company, are Microsoft 365-connected, which means they have access to Microsoft 365 features, including live events.
- Yammer honors Microsoft 365 group creation rights and enforces Microsoft 365 group creation restrictions.
- No external groups or network-level guests, but external networks are supported in the [US Geo](../manage-security-and-compliance/security-and-compliance.md).
- All files uploaded to groups will be stored in SharePoint.
- Files can't be uploaded to Yammer private messages.
- Verified and Network network admins are required to have either Global admin privileges or Group admin privileges from Microsoft 365 in order to administer changes to groups in which they aren't a group owner.

### Non-Native (not connected)

- External groups, network-level guests, and external networks are supported in the US Geo.
- All Yammer users can create groups.
- Files aren't stored in SharePoint.
- Files can be attached to Yammer private messages.
- Verified and Network network admins aren't required to have any additional admin privileges from Microsoft 365 in order to administer changes to groups.

### Hybrid

- A step on the way to Native Mode that lets you understand how Native Mode will work.
- External groups, network-level guests, and external networks are supported in the US Geo.
- All Yammer users can create groups.
- New files uploaded to Microsoft 365-connected groups are stored in SharePoint.
- Files can be attached to Yammer private messages.
- Verified and Network network admins aren't required to have any additional admin privileges from Microsoft 365 in order to administer changes to groups.

## Related articles

[Configure your Yammer network for Native Mode for Microsoft 365](native-mode.md)

[Yammer files in Native Mode for Microsoft 365](files-in-native-mode.md)

[Troubleshoot problems with Native Mode for Microsoft 365](../troubleshoot-problems/troubleshoot-native-mode.md)

[Microsoft Purview compliance portal](https://go.microsoft.com/fwlink/?linkid=2132455)

[Manage Yammer data compliance](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity for Yammer users](enforce-office-365-identity.md)

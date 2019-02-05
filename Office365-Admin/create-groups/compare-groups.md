---
title: "Compare groups"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_TypesOfGroups'
- 'O365P_ESTypesOfGroups'
- 'O365M_TypesOfGroups'
- 'O365M_ESTypesOfGroups'
- 'O365E_TypesOfGroups'
- 'O365E_ESTypesOfGroups'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
 - Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- EmptyState
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: "Create and manage Office 365 groups, shared mailboxes, security groups, and distribution lists."
---

# Compare groups

In the **Groups** section of the Office 365 admin center, you can create and manage these types of groups: 

- **Office 365 groups** are used for collaboration between users, both inside and outside your company.
- **Distribution lists** are used for sending notifications to a list of people.
- **Security groups** are used for granting access to SharePoint resources.
- **Mail-enabled security groups** are used for granting access to SharePoint resources, and emailing notifications to those users.
- **Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.

## Office 365 groups

Office 365 groups are used for collaboration between users, both inside and outside your company. With each Office 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planer.

You can add users external to your company to an Office 365 group as long as this has been enabled by the administrator. You can also allow external senders to send email to the group email address.

Office 365 groups can be configured for dynamic membership in Azure Active Directory, allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.

Office 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.

Group members can send as or send on behalf of the group email address if the administrator has enabled this.

## Distribution lists

Distribution lists are used for sending notifications to a list of people. They can recieve external email if enabled by the administrator.

Distribution lists are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."

## Security groups

Security groups are used for granting access to Office 365 resources, such as SharePoint. They can make administration easier because you need only administer the group rather than adding users to each resource individually.

Security groups can contain users or devices. Creating a security group for devices can be used with mobile device management, such as through Intune.

Security groups can be configured for dynamic membership in Azure Active Directory, allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.

## Mail-enabled security groups

Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.

They include the abilty to send mail to all the members of the group.

## Shared mailboxes

Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.

Shared mailboxes can recieve external emails if the administrator has enabled this.

Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that. This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."

Currently it's not possible to migrate a shared mailbox to an Office 365 Group. Is this something you want? Let us know. **[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**

## Related topics


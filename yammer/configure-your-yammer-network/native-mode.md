---
title: "Prepare a Yammer network for native mode for Microsoft 365"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 7/29/19
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn the steps required to prepare your Yammer network for native mode for Microsoft 365."
ROBOTS: NOINDEX, NOFOLLOW 
---
# Prepare a Yammer network for native mode for Microsoft 365

A Yammer network is in one of three modes:

- **Native mode for Microsoft 365**. In this mode, the network only uses features that allow users, groups, and content to be compatible with and mapped to their counterparts in Azure Active Directory (AAD) and Office 365. 
    
    This mode is required in order for Yammer content to be discoverable in the Office Security & Compliance Center. 

    In this mode, users and admins can't add features which would take the network out of native mode.

- **Connection-eligible mode**. In this mode, all requirements for native mode are met, but the admin hasn't committed the network to native mode. 

- **Non-connected mode**. In this mode, one or more requirements for native mode are not met. For example, the network may not enforce Office 365 identity or might have some files stored in Yammer rather than in SharePoint.

All *new* Yammer networks created after November 2019 will be created in native mode.

For *existing* Yammer networks created before November 2019, admins can choose the mode. The Microsoft 365 Alignment Wizard automates some parts of the process of converting your network to native mode and guides you through the rest of the steps.

To start the wizard, in the Yammer admin center, go to **Network Admin > Configure > Microsoft 365 Alignment Wizard**.

>[!IMPORTANT]
> Once you are in native mode, or have started the file migration process, you can't go back. 

## Requirements for native mode

You must be an Office 365 Global Admin to run the Microsoft 365 Alignment Wizard.

To be in native mode for your Yammer network:

- There can only be one Yammer network on the tenant.

- All domains on the tenant are associated with the Yammer network.

- All Yammer files must be stored in SharePoint.

- Soft delete must be turned on in Yammer on the **Content and Security** page in the Yammer admin center.

- All users must be in AAD. This means Office 365 identity is enforced.

- You must not have any unlisted private groups.

- All existing groups must be Office 365 connected, and must have an owner that has Office 365 group creation rights.

- You must not have any external networks. Support for external networks is planned, but is not available with initial release of native mode.

- You must not have any network-level, group-level or thread-level guests.

## Decisions

Decide which mode you want to use.

|Mode|Advantages|Disadvantages|
|----------|----------------------------|------------------|
|**Native**|No-one can inadvertently take network out of native mode<br><br>eDiscovery<br><br>Office 365 resources for each group<br><br>All groups, including **All Company** are Office 365 connected, which means they have access to Office 365 resources including live events<br><br>Only users with Office 365 creation rights can create new groups<br><br>Consistent file experience throughout Yammer|No files in private messages<br><br>No external collaboration<br><br>No guest users<br><br>No unlisted groups<br><br>No access to files in previous private messages|
|**Connection-eligible**|A step on the way to native mode that lets you understand how native mode will work<br><br>Admins can add flags to prevent users from taking actions that prevent the network from being connection-eligible. They can address each category separately as part of getting ready for native mode.<br><br>|If flags aren't set, users can add unlisted groups, groups that aren't Office 365 connected, attach files to private messages, or invite guests, preventing you from taking the network into native mode.|
|**Unconnected**|External collaboration<br><br>Allow guest users<br><br>All Yammer users can create groups<br><br>Files can be attached to private messages|Can't use eDiscovery<br><br>Doesn't provide Office 365 resources for groups|
|||

## Recommended process

1. Start the Microsoft 365 Alignment Wizard, which will identify the areas that need to be addressed to be able to be in native mode for Microsoft 365. 

2. Make a plan for working through the identified issues. Work through one at a time, following a process and timeframe that works for your organization. 

3. For each issue identified, mitigate the existing instances of the issue, for example changing all unlisted groups to listed groups, or running the file migration to store all Yammer files in SharePoint.

4. After an issue is mitigated, set the flag in the wizard to prevent users from creating the issue. For example, set the flag to prevent files from being added to private messages.

5. After you have mitigated all issues and set all flags, your network enters connection-eligible mode, where all features are compatible with AAD and Office 365.

6. When you're ready, lock in to native mode so that you can use eDiscovery.

## Admin experience 

Mitigation status for each issue can be viewed on the Microsoft 365 Alignment Wizard page. 

## End-user experience

You'll need to communicate each change you make to your end users so that they're not surprised when they stop being allowed to invite guests,add files to private messages, and create non-connected groups.

Here are some ideas to include in your communications:

We are getting our Yammer network ready to support required compliance and security policies for our organization. Here are some changes you will see rolling out over the next few weeks:
- We will be changing all unlisted private groups to be listed on \_\_/\_\_/\_\_. If you don't want your group to be listed, please delete it before that date.
- We will be removing all network, group, and conversation-level guests from our Yammer network on \_\_/\_\_/\_\_. We will send each guest an explanation.
- We will be moving all Yammer files to be stored in SharePoint on \_\_/\_\_/\_\_. 
- We will be making sure that all groups have an owner with Office 365 group creation rights. If we have to delete any groups, we will notify members first. 


## FAQ

**Q: After we commit our Yammer network to be in native mode, is it possible to revert to connection-eligible or non-connected mode?**

A: No. Native mode can't be reverted.

**Q: If in native or connection-eligible modes, what if my organization doesn't want to use SharePoint or Planner?**

A: Yammer will still display the links to Office 365 resources.

**Q: Does Yammer include any tools for eDiscovery?**

A: No. eDiscovery features are available from the [Office 365 Security & Compliance center](https://protection.office.com).

## See also

[Prepare files in Yammer for native mode for Microsoft 365](file-migration-native-mode.md)

[Office 365 Security & Compliance Center](https://protection.office.com)

[Manage data compliance in Yammer](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity](enforce-office-365-identity.md)
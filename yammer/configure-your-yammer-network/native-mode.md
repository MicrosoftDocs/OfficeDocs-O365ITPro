---
title: "Prepare a Yammer network for Native Mode for Microsoft 365"
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
description: "Learn the steps required to prepare your Yammer network for Native Mode for Microsoft 365."
ROBOTS: NOINDEX, NOFOLLOW 
---
# Prepare a Yammer network for Native Mode for Microsoft 365

A Yammer network is in one of three modes:

- **Native Mode for Microsoft 365**. In this mode, the network only uses features that allow users, groups, and content to be compatible with and mapped to their counterparts in Azure Active Directory (AAD) and Office 365. 
    
    This mode is required in order for Yammer content to be discoverable in the Office Security & Compliance Center. 

    In this mode, users and admins can't add features which would take the network out of Native Mode.

- **Hybrid mode**. In this mode, a network is enabled to map users, groups, and content to their counterparts in AAD and Office 365, but that is not required. The network may be in process of meeting all requirements for Native Mode, but the admin hasn't committed the network to Native Mode. 

- **Non-connected mode**. In this mode, one or more requirements for Native Mode are not met. For example, the network may not enforce Office 365 identity or might have some files stored in Yammer rather than in SharePoint. All external networks and Yammer Basic networks are in this mode, as they can't be connected to Office 365.

All *new* Yammer Enterprise networks created after November 2019 will be created in Native Mode.

For *existing* Yammer networks created before November 2019, admins can choose the mode. The Microsoft 365 Alignment Wizard automates some parts of the process of converting your network to Native Mode and guides you through the rest of the steps.

To start the wizard, in the Yammer admin center, go to **Network Admin > Configure > Microsoft 365 Alignment Wizard**. You must be an Office 365 Global Admin and a Verified Admin in Yammer to run the Native Mode for Microsoft 365 Alignment Wizard.

>[!IMPORTANT]
> Once you are in Native Mode, or have started the file migration process, you can't go back. 

## Requirements for Native Mode

The wizard helps you through the process of preparing your network into Native Mode, and then gives you the option to commit to Native Mode. To commit to Native mode:

- There can only be one Yammer network on the tenant.

- All domains on the tenant are associated with the Yammer network, and there are no domains on the Yammer network that are not on the tenant.

- All Yammer files must be stored in SharePoint.

- Soft delete must be turned on in Yammer on the **Content and Security** page in the Yammer admin center.

- All users must be in AAD. This requires Office 365 identity to be enforced, and any users who are not mapped must be deleted from the network.

- You must not have any unlisted private groups.

- All existing groups must be Office 365 connected.

- You must not have any external groups. Support for external groups is planned, but is not available with initial release of Native Mode.

- You must not have any network-level or thread-level guests.

## Key differences between modes

All new networks after November 2019 are Native Mode, and we are working to have all Yammer networks converted to Native Mode.

|Mode|Features|
|----------|----------------------------|
|**Native**|No-one can inadvertently take your network out of Native Mode<br><br>eDiscovery though the Security & Compliance center for your home network<br><br>All Yammer groups and users can be managed through Office 365<br><br>Office 365 resources for each group<br><br>All groups, including **All Company** are Office 365 connected, which means they have access to Office 365 resources including live events<br><br>Yammer honors Office 365 group creation rights<br><br>Consistent file experience throughout Yammer|
|**Hybrid**|A step on the way to Native Mode that lets you understand how Native Mode will work<br><br>Admins can add flags to prevent users from taking actions that prevent the network from being eligible for Native Mode. They can address each category separately as part of getting ready for Native Mode.|
|**Unconnected**|External collaboration<br><br>Allow guest users<br><br>All Yammer users can create groups<br><br>Files can be attached to private messages<br><br>eDiscovery and administration through Office 365 not available|
|||

## Recommended process

1. Start the Microsoft 365 Alignment Wizard, which will identify the areas that need to be addressed to be able to be in Native Mode for Microsoft 365. 

2. Make a plan for working through the identified issues. Work through one at a time, following a process and timeframe that works for your organization. 

3. For each issue identified, mitigate the existing instances of the issue, for example changing all unlisted groups to listed groups, or running the file migration to store all Yammer files in SharePoint.

4. After an issue is mitigated, set the flag in the wizard to prevent users from creating the issue. For example, set the flag to prevent files from being added to private messages.

5. After you have mitigated all issues and set all flags, your network enters connection-eligible mode, where all features are compatible with AAD and Office 365.

6. When you're ready, lock in to Native Mode so that you can use eDiscovery.

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

**Q: After we commit our Yammer network to be in Native Mode, is it possible to revert to connection-eligible or non-connected mode?**

A: No. Native Mode can't be reverted.

**Q: If in Native or connection-eligible modes, what if my organization doesn't want to use SharePoint or Planner?**

A: Yammer will still display the links to Office 365 resources.

**Q: Does Yammer include any tools for eDiscovery?**

A: No. eDiscovery features are available from the [Office 365 Security & Compliance center](https://protection.office.com).

## See also

[Prepare files in Yammer for Native Mode for Microsoft 365](file-migration-Native-mode.md)

[Office 365 Security & Compliance Center](https://protection.office.com)

[Manage data compliance in Yammer](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity](enforce-office-365-identity.md)
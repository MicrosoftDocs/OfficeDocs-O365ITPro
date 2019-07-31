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

2. Download the report to see more detail than is shown in the wizard.

2. For each issue that you don't want the default action taken, mitigate existing instances of the issue. For example, there may be some private unlisted groups that you or the owner would prefer to have deleted rather than making them a private listed group.  

3. When you are ready for the wizard to take default actions on each issue, click Next.
 
4. Refresh the wizard page to see the status of each job the wizard is working on. Some tasks will complete very quickly, while others, like file migration, may take more time depending on the size and complexity of your network.

6. When the wizard completes, on the Commitment screen, enter your user id to commit to Native Mode.

## End-user experience

We recommend communicating about changes you make to your end users so that they're not surprised when they stop being allowed to invite guests, add files to private messages, and create non-connected groups.

Here are some ideas to include in your communications:

We are getting our Yammer network ready to support required compliance and security policies for our organization. Here are some changes you will see rolling out over the next few weeks:

- We will begin changing all unlisted private groups to be listed on \_\_/\_\_/\_\_. This means that non-members can see the group in search results and other areas, but the content will still be restricted to members. If you don't want your group to be listed, please delete it before that date. You can also change the name of the group, if the concern is that people will identify the purpose of the group based on the name.

- We will begin removing all network, group, and conversation-level guests from our Yammer network on \_\_/\_\_/\_\_. We will send each guest an explanation.

- We will begin moving all Yammer group files to be stored in SharePoint on \_\_/\_\_/\_\_. 

## FAQ

**Q: After we commit our Yammer network to be in Native Mode, is it possible to revert to Hybrid Mode or Unconnected mode?**

A: No. Native Mode can't be reverted.

**Q: If in Native or Hybrid modes, what if my organization doesn't want to use SharePoint or Planner?**

A: Yammer will still display the links to Office 365 resources. In Native Mode this section will appear for all groups. In Hybrid Mode, the section will only be visible for connected groups. 

**Q: Does Yammer include any tools for eDiscovery?**

A: No. eDiscovery features are available from the [Office 365 Security & Compliance center](https://protection.office.com). However, when your home Yammer network is in Native mode, you will be able to perform eDiscoverty on that home network from the Security & Compliance Center.

**Q: Why doesn't Native Mode support all previously existing features?**

**A: Native Mode means that your network is 100% backed by AAD and Office 365 groups. The following features can't be supported in this configuration:

- Marking files official is only possible when files are stored in Azure cloud storage.

- Guests are not supported by AAD.

- Unlisted private groups are not supported by Office 365.

- Soft delete is required for eDiscovery.

**Q: Do I have to make my network be in Native Mode?**

A: Yammer networks in new tenants start out in Native Mode. Admins of existing networks can choose whether or not they want their Yammer network to be in Native Mode.

## See also

[Prepare files in Yammer for Native Mode for Microsoft 365](file-migration-Native-mode.md)

[Office 365 Security & Compliance Center](https://protection.office.com)

[Manage data compliance in Yammer](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity](enforce-office-365-identity.md)
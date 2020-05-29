---
title: "Troubleshoot your Yammer network for Native Mode for Microsoft 365"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 01/21/2020
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn the steps required to prepare your Yammer network for Native Mode for Microsoft 365."
---

# Troubleshoot problems with Native Mode for Microsoft 365

## What is Native Mode?

### What benefits are new to Native Mode?

Networks in Native Mode can [perform eDiscovery](../configure-your-yammer-network/overview-native-mode.md) on their home Yammer network through the Security & Compliance Center, just like they do for other Office 365 products. In addition, administrators and users both benefit by having an experience that is more consistent within Yammer and within the Microsoft 365 ecosystem.

### What are the main requirements for Native Mode?

A network must be able to synchronize all domains with AAD, which means . . .

- There can only be one home network on the Office 365 tenant.
- All domains on the tenant are associated with the Yammer network.
- All domains on the Yammer network are associated with the tenant.

All users must be in AAD, which means . . .

- Office 365 Identity must be enforced in the home network.
- No Network Level Guests in the network.
- No Group Level Guests in the network because those users do not currently map to users in AAD.
- No thread-level Guests.
- No inactive unmapped users (for example, a user with Yammer authentication who was not deleted when they left the organization).

All groups must be connected, which means . . .

- Only users with Microsoft 365 Group creation rights can create groups in Yammer.
- No Yammer group can be created until we can ensure the group is connected.
- No unlisted private groups or external groups, because those groups are not currently connectable.

> [!NOTE]
> If you receive an error code during the alignment process for Native Mode, you can refer to the [error codes](#error-codes) section below for more information.


### What is required for me to be in Native Mode for Microsoft 365 in Yammer?

While new networks will start out in Native Mode beginning in January 2020, existing networks will need to use our Alignment Tool ("Tool") to have their network enter Native Mode. To use the Tool, your network must enforce Office 365 Identity. There must also only be one (primary) home network on the Office 365 tenant. Once a network satisfies those two criteria, the Alignment Tool can be used to address any incompatibilities of your network with a Native Mode network.

#### Are there additional licensing requirements when moving to native mode?

Native Mode does not require to have any additional licensing requirements beyond those required for [Office 365 plans that include Groups](https://go.microsoft.com/fwlink/?linkid=2110822)

### What features aren't supported in Native Mode and why aren't they supported?

- *Native Mode does not support private unlisted groups*: As of January 2020, AAD and Microsoft 365 Groups don't support this feature, so it is not possible for us to offer it in Native Mode networks. The downloadable Alignment Tool report will provide you with information on the quantity and usage of private unlisted groups in your network.

- *Native Mode does not support external groups within its own network*: Yammer’s current external collaboration capabilities, including external groups, are not compatible with [Azure B2B](https://go.microsoft.com/fwlink/?linkid=2116001). As a result, Native Mode networks cannot host an external group. Users from Native Mode networks can, if allowed by your Yammer Security Settings, collaborate in external groups in other Yammer networks that are not in Native Mode. In addition, External Networks will continue to be supported for Native Mode Yammer networks in the US Geo. We are planning to support in Native Mode for Azure B2B in the future.

Azure Active Directory (Azure AD) business-to-business (B2B) collaboration lets you securely share your company's applications and services with guest users from any other organization, while maintaining control over your own corporate data.

The downloadable Alignment Report will provide you with information on the quantity and usage of external groups in your network.

- *Native Mode does not support (network) guests*: The (network) guests feature is not compatible with Azure B2B so, guests in Yammer cannot have their Yammer identity mapped to an associated AAD identity. As a result, we are unable to support the guest feature in Native Mode networks. The downloadable Alignment Report will provide you with information on the quantity and activity of guests in your network.

- *External participants*: Yammer currently allows users to add external participants to individual threads. This feature is not available for Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357). This feature is not currently compatible with the Azure B2B guest model, and so won't be supported in Native Mode networks.

- *File uploads in Yammer Private messages*: In order to be in Native Mode, all files uploaded in Yammer must be stored in SharePoint. Since Yammer private messages do not store files in SharePoint or OneDrive for Business, the Alignment Tool must delete any previously uploaded private message files. Users will no longer be able to upload files in private messages. The downloadable Alignment Report will provide you with information on the quantity of files previously uploaded in private messages.

### What is the main difference between Native Mode and eDiscovery

- *Native Mode* - A state where all the users, groups, and content from your network are compatible with (and mapped to) their counterparts in AAD/Office 365.

- *eDiscovery* - A Yammer feature Microsoft now provides to customers through the [Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321).  

Yammer can offer eDiscovery to customers once all their Users, Groups, and Content can be discoverable through the Security and Compliance Center. To facilitate this process, Yammer must ensure that all Groups are Microsoft 365 connected because eDiscoverable content must be saved in the group mailbox. Similarly, users must have an AAD account.

### What can you include in communications to your users?

Below is some content you can use as-is or modify to meet your needs when you're ready to communicate upcoming changes to your organization. For example, this is how you might draft an email to your users:

----------------EXAMPLE----------------

*Hello NAME OF EMPLOYEE,*

*We are getting our Yammer network ready to support required compliance and security policies for our organization.*

*Here are some changes you will see rolling out over the next few weeks:*

*- All unlisted private groups will become private listed groups on DATE. Non-members will be able to see the group in search results and other areas, but only members can access the content. If you don't want your group to be visible to non members, you must delete it before that date. You can also change the name of the group if the concern is that people will identify the purpose of the group based on the name.*

*- All network, group, and conversation-level guests from our Yammer network will be removed on DATE. If you're working with people outside of our Yammer network, you should figure out an alternate way to communicate with them.*

*- All Yammer group files will be stored in SharePoint beginning on DATE. This means previously uploaded group files will be migrated to SharePoint and all new group file uploads will be saved to SharePoint.*

*- All files that were previously uploaded on Yammer private messages will be deleted on DATE. No new files can be uploaded in Yammer private messages.*

*- Beginning DATE users will need to have Microsoft 365 Group creation rights in order to create a group in Yammer. If you do not currently have Microsoft 365 Group creation rights, you will no longer be able to create groups in Yammer. Please reach out to your manager if you do not have Microsoft 365 Group creation rights, but feel you need to do so to perform your job.*

*Your IT team*

## Migration

### What can end users expect during migration?

We recommend you communicate to your end users your plan to change to Native Mode. Early communication will prevent surprises, from changes such as, users requiring Microsoft 365 Group creation rights to create groups in Yammer, not being able to create external groups, and/or file attachments no longer being supported in Yammer private messages.

### How do I check the status of my network's migration to Native Mode?

Any Global Admin from your tenant can check the status of your network's alignment to Native Mode by logging in to Yammer and going to the Microsoft 365 Native Mode page within the Network Admin pages of Yammer

## Networks

### Should I align my network to be in Native Mode?

The answer to this question depends on the unique needs and situation of your organization. While Native Mode provides many benefits to users and administrators, there are some features that cannot currently be supported in Native Mode because the features are not supported by Microsoft 365 Groups or Azure Active Directory ("AAD"). On one hand, if it is particularly important for your organization to centralize administration and governance as much as possible, then being in Native Mode makes sense. On the other hand, if it is critical for your network to continue using Yammer features that are not supported in Native Mode, you may want to hold off in moving to Native Mode until later.

### Is it possible for a network that is in Native Mode to get out of Native Mode?

No. Once a network is in Native Mode, it is not possible for it to get out of Native Mode. We recommend administrators carefully review the documentation we provide on Native Mode before beginning the process because *it is irreversible*.  

### How does a network enter Native Mode for Microsoft 365?

**New Networks**
After January 2020, all new networks will begin in Native Mode. This means they will have a different feature set than existing customers as there are features that aren't available through Azure Active Directory (AAD), and so cannot be supported in Native Mode.

**Existing Networks**
Existing networks will be able to lock themselves in to Native Mode by using the Microsoft 365 Alignment Tool to mitigate any areas where their network is incompatible with the feature set of Native Mode.

## Files

### How does Yammer in Native Mode handle file migration?

Once a Yammer group is connected, the Alignment Tool migrates all files previously uploaded to Yammer to SharePoint. When files are moved to the SharePoint document library, only the latest version is moved over, and the version history is not copied.

### Why does the Alignment Tool delete messages and files from deleted groups and deleted users?

Deleted groups and deleted users do not typically have a mailbox, which means content associated with that group or user would not be available for eDiscovery. Therefore, we need to remove that content from Native Mode networks in order to offer an eDiscovery solution in the Compliance Center that includes all conversations and files in your Native Mode network.

### How does Yammer in Native Mode handle file name conflicts?

It is possible that files previously uploaded to Yammer will not comply with SharePoint filename restrictions. When migration completes, the IT admin gets a report of any file name conflicts. Please update the file names and make sure there are no file names with the following invalid characters before running the Tool again:

- "
- **
- :
- < >
- ?
- /
- \
- |

You won't be able to take your network to Native Mode for Microsoft 365 until you resolve any files left behind.

## Error Codes

If you receive errors in the report generated by the alignment tool, follow the steps in the table below to troubleshoot them. If you encounter an error code that isn't listed below, [contact the Microsoft support team](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online).

|**Code** |**Description** | **Migration** |
|:--------|:-------------- |:------------- |
|CannotOpenFile--2147024816 |Can't open a file |Remove file |
|FilealreadyExists--2130575257 |File is in SharePoint already |Remove/rename |
|FileNameCharactersNotPermitted—2130575245 |[Characters not permitted in SharePoint exist in file name](https://support.office.com/article/invalid-file-names-and-file-types-in-onedrive-onedrive-for-business-and-sharepoint-64883a5d-228e-48f5-b3d2-eb39e07630fa)|Rename/remove 
|InvalidCharactersInPath--2147024809|[Characters not permitted in SharePoint exist in file name](https://support.office.com/article/invalid-file-names-and-file-types-in-onedrive-onedrive-for-business-and-sharepoint-64883a5d-228e-48f5-b3d2-eb39e07630fa)|Rename/remove|
|PathTooLong---2147024690---2130575338|[Filepath is too long](https://support.office.com/article/invalid-file-names-and-file-types-in-onedrive-onedrive-for-business-and-sharepoint-64883a5d-228e-48f5-b3d2-eb39e07630fa)|Rename/remove|
|SpFileDeleted---2130575338|File deleted in SharePoint|Upload again to SharePoint/ delete file|
|Unknown||Remove file/ [contact  support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online)|
| 

> [!NOTE]
> If you have a large number of files with disallowed characters, you can [contact Microsoft support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products?view=o365-worldwide&tabs=online) to obtain a script that renames files in a bulk process.

### What happens to the conversations and files from deleted Microsoft 365 Groups that are within their 30-day recovery window?

When the Alignment Tool is run, it will remove the conversations and Yammer-hosted files for all deleted groups, whether the group is in a hard- or soft-deleted state. This means that if there are Yammer Microsoft 365 connected groups that were in the soft delete period when the Alignment Tool was run, those groups, if restored, would be restored without conversations and without any files that had been uploaded to Yammer. Group metadata and files that were uploaded to SharePoint would continue to be restored as they are in non Native Mode scenarios.

## Users and Guests

### Network guests

- *Why aren't network guests supported in Native Mode?*

  Network guests in Yammer are not currently Azure B2B guests, and so their userIDs are not associated with an account in Azure Active Directory for your Office 365 tenant. Since eDiscovery requires all users to be in AAD, Yammer's (network-level) guest feature cannot be supported in Native Mode. Yammer does expect to add support for group-level Azure B2B guests in Native Mode, but we do not expect to support adding (network-level) guest support into Native Mode networks.

- *What should I do about my existing network guests?*

  The vast majority of networks have never had any network guests. If your network has had network guests in the past, it is likely most of those guests no longer have access due to your network enforcing Office 365 Identity.

  The downloadable Alignment Report provides information about the network guests in your network and their activity within the network. We recommend you use the information in the report to help you decide whether these users should continue to have access to the network. If you do want these users to have access to the network when your network is in Native Mode, you will need to provide them with new credentials associated with an AAD account. Yammer does not currently support Azure B2B, so it must be a member user account that you provide on AAD, not a guest account. This new account will not be associated with their guest account, so the user will not have access to private messages, files, or groups of the previous account, unless the new account is added to that private content.

  If your company makes extensive use of network guests, you may consider delaying your move to Native Mode.

  Whatever path you choose, we recommend you communicate clearly to those guests what changes are coming.

### What happens to users who don’t have Microsoft 365 Group creation rights?

If your network enforces Microsoft 365 Group creation rights, users without those rights will no longer be able to create groups in Yammer. We recommend that all users be able to create Yammer groups so that your entire organization can enjoy the benefits of an open, collaborative network.

### What about users who are not in Azure Active Directory ("AAD")?

- *Why would I have users not in AAD in my network if I enforce Office 365 Identity?*
  Enforcing Office 365 Identity does not remove users from your network who left your organization prior to your organization enforcing Office 365 identity. Most customers who do have users in their Yammer network that are not in AAD, will find that these users have not been active in the network since Office 365 Identity was enforced for the network or, even further back.

- *Why would some of these users have recent activity?*
  At the time a network chooses to enforce Office 365 Identity, the administrator can choose whether or not to log out all logged in users to the network. If your network did not force all users to log out, it is possible that some of these users have remained active enough that they've remained logged in.

- *What should I do about users who are not in AAD?*
  The downloadable Alignment Report provides information about which users in your Yammer network are not in (or mapped to an account in) Azure Active Directory. We recommend you use the information in the report to help you decide whether these users should continue to have access to the network. You will need to create a new AAD account for a user if you want to provide continued Yammer access to users who don't currently have an AAD account. In some cases, these accounts may be service accounts or bots, rather than specific end users.

- *Why would a user not be in AAD?*
  There are multiple reasons why:

  - In some cases, the user was invited to the network, but has never logged into Yammer. These users are "pending" users.

  - The user has not needed to log in to Yammer since the network started enforcing Office 365 identity. That is, they are using Yammer regularly enough, and with the same client, that they have remained logged in since the network began enforcing identity.

  - The user could be a (network-level) guest in the network. Network level guests are not supported in AAD.

- *What does the Tool do for pending users?*
  The Tool will first try to associate the pending user with an account in AAD for your Office 365 tenant. If that association is successful, the user will remain in the network. If we are not able to associate the pending user with an AAD account on your tenant, then we will delete the user from Yammer.  

### Why aren't external participants in individual conversations supported in Native Mode?

Yammer currently allows users to add external participants to individual threads. This feature is not currently compatible with the Azure B2B guest model, and so won't be supported in Native Mode networks. This feature is not available for Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357).

## Groups

### What do I need to do to prepare my All Company group to be Microsoft 365 connected?

There is no preparation required to make your All Company group Microsoft 365-connected. The Tool will connect the group and make the Verified Admins for the network group owners of the All Company group in AAD. As group owners, they will be able to post announcements in the All Company group as they were able to do before All Company was Microsoft 365-connected.

- *How is All Company different than other Microsoft 365-connected groups?*
  The All Company group is different than other Yammer groups in that all users in the network are treated as members of the group without them needing to actually be a member of the group. Once All Company is connected, it is possible to add members to the group from AAD. However, we do not recommend that users be added as members because it won't change the behavior of the group within Yammer for those users.

- *Can I delete All Company once it is connected?*
  We don't recommend that you delete All Company, as it is an important way for your users to communicate broadly across your organization. Once All Company is Microsoft 365-connected, it is possible to delete the Microsoft 365 Group from the Microsoft 365 admin center or the Azure Active Directory admin center. If that is done, Yammer will honor the deletion and not show All Company in your network.

- *Can I make All Company private once it is connected?*
  A private All Company is an unsupported state in Yammer. In addition, we don't recommend that you make All Company private, as it is an important way for your users to communicate broadly across your organization. Once All Company is Microsoft 365-connected, it is possible to make it private from the Microsoft 365 admin center or the Azure Active Directory admin center. If that is done, Yammer will not show All Company in your network to anyone regardless of group membership.

### Why aren't external groups supported in Native Mode?

Because Yammer external groups are not compatible with Azure B2B, guests in external groups in Yammer are not associated with an account in Azure Active Directory for your Office 365 tenant. As a result, Yammer's current model of external groups cannot be supported in Native Mode. Yammer does expect to add support for Azure B2B guests in Native Mode, so we do expect to support adding guests to groups in Yammer in the future.

- *What should I do about my external groups?*
  The downloadable Alignment Report provides information about the use of external groups within your enterprise network so that you can determine the best path forward for your organization. Many organizations already block the ability to create external groups in their network—those companies will not be affected by this change. If your company makes extensive use of external groups, you may consider delaying your move to Native Mode.

  If your network does have external groups, we recommend you use the downloadable Alignment Report to see whether there are any external guests in the group, whether those guests have had any recent activity, as well as whether the group itself has had any recent activity. From this information, you can assess what actions to take on the group. On one hand, if the group has no external members, but has had recent activity by internal members, then you may opt to let the Tool make that group an internal only group. On the other hand, if you find the group has external members, but the group itself has not had any activity at all for some time, you may decide to delete the group before running the Tool.

  Whatever path you choose, we recommend you communicate clearly to the owners of these groups what changes are coming so that they can alert you. In some cases, these groups may be owned by senior leaders within your organization so, be sure to choose the appropriate communication channel when reaching out to group owners.

### How do unlisted private groups work?

- *Why can't I have unlisted private groups in Native Mode?*
  Azure Active Directory and Microsoft 365 Groups don't currently support having unlisted private groups. If Yammer continued to support this feature in a Native Mode network, groups would be unlisted in Yammer. However, these groups would be exposed through other Microsoft 365 products. The downloadable Alignment Report will provide you with information on the quantity and usage of private unlisted groups in your network.

- *What should I do about my unlisted private groups?*
  The downloadable Alignment Report provides information about the usage of private unlisted groups within your enterprise network so that you can determine the best path forward for your organization. If your company makes extensive use of unlisted private groups and you want to continue to offer this feature to your users, you may consider delaying your move to Native Node.

  If your network does have private unlisted groups, we recommend you use the downloadable Alignment Report to see whether there are any users or guests in the group, and whether those users or guests have had any recent activity in the group. From this information, you can assess what actions to take on the group. On one hand, if the group has had recent activity, but the group name does not contain any confidential or sensitive information, you may opt to let the Tool make that group an internal only group. On the other hand, if you find the group hasn't had any activity for some time, you may decide to delete the group before running the Tool.

  Whatever path you choose, we recommend you communicate clearly to the owners of these groups what changes are coming so that they can alert you. In some cases, these groups may be owned by senior leaders within your organization, so be sure to choose the appropriate communication channel when reaching out to group owners.  

### What happens to Groups without owners that have Microsoft 365 group creation rights?

- *Why do you need to add the global admin running the Alignment Tool as a group owner in groups that have no owner with Microsoft 365 group creation rights?*

  This change is done for either (1) groups without any owners, or (2) groups with owners, but none have Microsoft 365 Group creation rights. To make a Yammer group a Microsoft 365-connected group, it is necessary to have at least one group owner with Microsoft 365 Group creation rights. Because global admins have Microsoft 365 Group creation rights, adding the global admin as a group owner helps ensure that the group can become Microsoft 365-connected.

- *What should I do about my groups without owners with Microsoft 365 group creation rights?*

  The downloadable Alignment Report provides information about the groups within your enterprise network that don't have any group owners with group creation rights so that you can determine the best path forward for your organization. These group include:

  - groups that have no owners;
  - groups whose owners do not have Microsoft 365 group creation rights.

  If your network has many of these groups, you have a few options available to you.
  You can allow the Tool to add the global admin running the Tool to each group as an owner so that the group can become Microsoft 365-connected. Once a group is connected, you can, at your discretion, remove the global admin from having ownership of the group.
  
  You can also review the impacted groups from the downloadable Alignment Report and see if they have any recent activity or active group members. If they don't, you may elect to delete those groups before running the Tool. After those groups have been deleted, you can run the Tool. By deleting inactive groups before running the Tool, you'll reduce the number of groups to which you, as a global admin, need to be added to in order to achieve Native Mode.  

  You can grant Microsoft 365 Group creation rights to all users within your organization, or at least to the users that are owners of unconnected groups in Yammer, so that those groups can be connected without the global admin needing to be added as an owner. Once those groups are connected, you can choose whether to revoke group creation rights from some of those users who were granted access.

Whatever path you choose, we recommend you communicate clearly to the users in your network of the changes that are coming so that they can alert you of any concerns or potential issues.

### Will the features supported by Native Mode change over time?

Yammer will continue to improve the Native Mode offering, so you can expect to see new features and capabilities come to Native Mode in the future. For example, we plan to add external group capabilities by supporting Azure AD B2B in Yammer.

## Related articles

[Overview of Native Mode](../configure-your-yammer-network/overview-native-mode.md)

[Configure your Yammer network for Native Mode for Microsoft 365](../configure-your-yammer-network/native-mode.md)

[Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321)

[Manage Yammer data compliance](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md)

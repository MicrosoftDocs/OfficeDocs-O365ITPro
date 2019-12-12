---
title: "Troubleshoot your Yammer network for Native Mode for Microsoft 365"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 12/11/2019
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

# Troubleshoot problems with Native Mode for Microsoft 365

## What can end users expect during migration?**

We recommend you communicate the change to Native Mode to your end users. Early communication will prevent surprises, such as the inability to invite guests, add files to private messages, or create non-connected groups.

### What should I include in our communications to users?**

Below is some content you can use as-is or modify to meet your needs:

We are getting our Yammer network ready to support required compliance and security policies for our organization. Here are some changes you will see rolling out over the next few weeks:

- All unlisted private groups will be listed on __/__/__. Non-members will be able to see the group in search results and other areas, but only members can access the content. If you don't want your group listed, delete it before that date. You can also change the name of the group if the concern is that people will identify the purpose of the group based on the name.

- All network, group, and conversation-level guests from our Yammer network will be removed on __/__/__. We will send each guest an explanation.

- All Yammer group files will be stored in SharePoint on __/__/__.

- All files that were previously uploaded on Yammer private messages will be deleted on __/__/__. No new files will be uploaded in Yammer private messages. This change does not impact file uploads in Teams chats.

## Questions and answers about general issues

### What is required for me to be in Native Mode for Microsoft 365 in Yammer?**

While new networks will start out in Native Mode, existing networks will need to use our  Alignment Tool ("Tool") to have their network enter Native Mode. To use the Tool, your network must enforce Office 365 Identity. There must also only be one (primary) home network on the Office 365 tenant. Once a network satisfies those two criteria, they can use the Tool to address any incompatibilities of their network with a Native Mode network.

### Should I align my network to be in Native Mode?**

The answer to this question depends on the unique needs and situation of your organization. While Native Mode provides many benefits to users and administrators, there are some features that cannot currently be supported in Native Mode because the features are not supported by Office 365 Groups or Azure Active Directory ("AAD"). On one hand, if it is particularly important for you organization to be able to centralize administration and governance as much as possible, then being in Native Mode makes sense. On the other hand, if it is critical for your network to continue using Yammer features that are not supported in Native Mode, you may want to hold off in moving to Native Mode until later.

### Is it possible for an network that is in Native Mode to get out of Native Mode?**

No. Once a network is in Native Mode, it is not possible for it to get out of Native Mode. We recommend administrators carefully review the documentation we provide on Native Mode before beginning the process because *it is irreversible*.  

### What benefits are new to Native Mode?**

Networks in Native Mode can perform eDiscovery (coming soon) on their home Yammer network through the Security & Compliance Center, just like they do for other Office 365 products. In addition, administrators and users both benefit by having an experience that is more consistent within Yammer and within the Microsoft 365 ecosystem.

### What are the main features of a Native Mode network?**

A network must be able to synchronize its full domain with AAD, which means . . .

- There can only be one home network on the Office 365 tenant.
- All domains on the tenant are associated with the Yammer network.
- All domains on the Yammer network are associated with the tenant.

All users must be in AAD, which means . . .

- Office 365 Identity must be enforced in the home network.
- No Network Level Guests in the network.
- No Group Level Guests in the network because those users do not currently map to users in AAD.
- No (flexternal) Thread-level Guests.
- No inactive unmapped users (for example, a user with Yammer authentication who was not deleted when they left the organization).

All groups must be connected, which means . . .

- Only users with Office 365 Group Creation Rights can create groups in Yammer.
- No Yammer group can be created until we can ensure the group is connected.
- No Unlisted (or secret) Groups or External Groups, because those groups are not currently connectable.

### How does a network enter Native Mode for Microsoft 365?**

**New Networks**
After December 2019, all new networks will begin in Native Mode. This means they will have a different feature set than existing customers as there are some existing features that cannot be supported by Azure Active Directory (AAD).

**Existing Networks**
Existing networks will be able to lock themselves in to Native Mode by using the Microsoft 365 Alignment Tool to mitigate any areas where their network is incompatible with the feature set of Native Mode.

### What about users who are not in Azure Active Directory ("AAD")?**

- *Why would I have users not in AAD in my network if I enforce Office 365 Identity?*
  Enforcing Office 365 Identity does not remove users from your network; rather, it prevents users without Office 365 identity from logging on to your network. Most customers who do have users in their Yammer network that are not in AAD, will find that these users have not been active in the network since Office 365 Identity was enforced for the network or, even further back. if the users weren't removed from the network when they left your organization.

- *Why would some of these users have recent activity?*
  At the time a network chooses to enforce Office 365 Identity, the administrator can choose whether or not to log out all logged in users to the network. If your network did not force all users to log out, it is possible that some of these users have remained active enough that they've not needed to try to log in.

- *What should I do about users who are not in AAD?*
  The downloadable report provides information on what users in your Yammer network are not in (or mapped to an account in) Azure Active Directory. We recommend you use the information in the report to help you decide whether these users should continue to have access to the network. In some cases, you may need to create a new AAD account for a user if you do wish to provide continued Yammer access to these users. In some cases, these accounts may be service accounts or bots, rather than specific end users.

- *Why would a user not be in AAD?*
  There are multiple reasons why:

  - In some cases, the user was invited to the network, but has never logged into Yammer. These users are "pending" users.

  - The user has not needed to log in to Yammer since the network started enforcing Office 365 identity. That is, they are using Yammer regularly enough, and with the same client, that they have remained logged in since the network began enforcing identity.

  - The user could be a (network-level) guest in the network. Network level guests are not supported in AAD.  

- *What is a pending user?*
  A "pending user" is someone who has been invited to a Yammer network, but never logged in. Pending users can be added to groups even before they have used Yammer for the first time.

  Pending users receive announcement notification emails from group admins. If users don't want to receive announcements from a particular group, they can log into their Yammer account and leave the group or follow the unsubscribe link in the email to unsubscribe from all Yammer emails.

  From <https://docs.microsoft.com/en-us/yammer/manage-yammer-users/add-block-or-remove-users#manage-pending-users>  

- *What does the Tool do for pending users?*
  The Tool will first try to associate the pending user with an account in AAD for your Office 365 tenant. If that association is successful, the user will remain in the network. If we are not able to associate the pending user with an AAD account on your tenant, then we will delete the user.  

### Is it possible for a Native Mode network to revert back to its previous state?**

No. Once an IT admin commits their Yammer Enterprise network to Microsoft 365 Native Mode, it will stay that way permanently. *The state is irreversible.*

### What features aren't supported in Native Mode? Why aren't they supported?**

- *Native Mode does not support external groups*: Users from Native Mode networks can, if allowed by your Yammer Security Settings, collaborate in external groups in other Yammer networks that are not in Native Mode. In addition, External Networks will continue to be supported for Native Mode Yammer networks. We do plan to add support for external groups through Azure Active Directory B2B in Native Mode networks in the future. The downloadable report from the Tool will provide you with information on the quantity and usage of external groups in your network.

- *Native Mode does not support private unlisted groups*: As of December 2019, AAD and Office 365 Groups don't support this feature. If Yammer tried to offer this feature, groups would be unlisted in Yammer, but fully discoverable through other channels. The downloadable report from the Tool will provide you with information on the quantity and usage of private unlisted groups in your network.

- *Native Mode does not support network guests*: Network guests is a feature that is rarely used by most networks. Network guests in Yammer do not have an associated AAD identity that is mapped to their Yammer identity, so we are unable to support that feature in Native Mode. The downloadable report from the Tool will provide you with information on the quantity and activity of guests in your network.

- *File uploads in Yammer Private messages*: In order to be in Native Mode, all files uploaded in Yammer must be stored in SharePoint. Yammer Private messages do not store files in SharePoint, so Native Mode networks must delete any previously uploaded private message files through the Tool, and users will no longer be able to upload files in Private messages going forward. The downloadable report from the Tool will provide you with information on the quantity of files previously uploaded in Private messages.

- *External participants*: Yammer currently allows users to add external participants to individual threads. This feature is very rarely used, and few users know of its availability. This feature is not currently compatible with the Azure B2B guest model, and so won't be supported in Native Mode networks.

### What do I need to do to prepare my All Company group to be connected?**

There is no preparation required to make your All Company group Office 365-connected. The Tool will connect the group and make the Verified Admins for your network group owners in AAD. As group owners, they will be able to post announcements in the All Company group as they were able to do before All Company was Office 365-connected.

- *How is All Company different than other Office 365-connected groups?*
  The All Company group is different than other Yammer groups in that all users in the network are treated as members of the group without them needing to actually be a member of the group. Once All Company is connected, it is possible to add members to the group from AAD. However, we do not recommend that users be added as members because it won't change the behavior of the group within Yammer for those users.

- *Can I delete All Company once it is connected?*
  We don't recommend that you delete All Company, as it is an important way for your users to communicate broadly across your organization. Once All Company is Office 365-connected, it is possible to delete the Office 365 Group from the Microsoft 365 admin center or the Azure Active Directory admin center. If that is done, Yammer will honor the deletion and not show All Company in your network.

- *Can I make All Company private once it is connected?*
  A private All Company is an unsupported state in Yammer. In addition, we don't recommend that you make All Company private, as it is an important way for your users to communicate broadly across your organization. Once All Company is Office 365-connected, it is possible to make it private from the Microsoft 365 admin center or the Azure Active Directory admin center. If that is done, Yammer will honor the deletion and not show All Company in your network.

### Is the feature set / baked / locked in?**

Yammer will continue to improve the Native Mode offering, so you can expect to see new features and capabilities come to Native Mode in the future. For example, we plan to add external group capabilities by supporting Azure AD B2B in Yammer.

### Why aren't external groups supported in Native Mode?*

Guests in external groups in Yammer are not currently Azure B2B guests, and so their userIDs are not associated with an account in Azure Active Directory for your Office 365 tenant. Since eDiscovery (coming soon) requires all users to be in AAD, Yammer's current model of external groups cannot be supported in Native Mode. Yammer does expect to add support for Azure B2B guests in Native Mode, so we do expect to support adding guests to groups in Yammer in the future.

- *What should I do about my external groups?*
  The downloadable report provides information about the use of external groups within your enterprise network so that you can determine the best path forward for your organization. Many organizations already block the ability to create external groups in their network—those companies will not be affected by this change. If your company makes extensive use of external groups, you may consider delaying your move to Native Mode.

  If your network does have external groups, we recommend you use the downloadable report to see whether there are any external guests in the group, whether those guests have had any recent activity, as well as whether the group itself has had any recent activity. From this information, you can assess what actions to take on the group. On one hand, if the group has no external members, but has had recent activity by internal members, then you may opt to let the Tool make that group an internal only group. On the other hand, if you find the group has external members, but the group itself has not had any activity at all for some time, you may decide to delete the group before running the Tool.

  Whatever path you choose, we recommend you communicate clearly to the owners of these groups what changes are coming so that they can alert you. In some cases, these groups may be owned by senior leaders within your organization, so be sure to choose the appropriate communication channel when reaching out to group owners.

### Unlisted private groups

- *Why can't I have unlisted private groups in Native Mode?*
  Azure Active Directory and Office 365 Groups don't currently support having unlisted private groups. If Yammer continued to support this feature in a Native Mode network, groups would be unlisted in Yammer. However, these groups would be exposed through other Microsoft 365 products because the unlisted feature is not fully supported across Microsoft 365. The downloadable report from the Tool will provide you with information on the quantity and usage of private unlisted groups in your network.

- *What should I do about my unlisted private groups?*
  The downloadable report provides information about the usage of private unlisted groups within your enterprise network so that you can determine the best path forward for your organization. If your company makes extensive use of unlisted private groups and you want to continue to offer this feature to your users, you may consider delaying your move to Native Node.

  If your network does have private unlisted groups, we recommend you use the downloadable report to see whether there are any users or guests in the group, whether those users or guests have had any recent activity in the group. From this information you can assess what actions to take on the group. On one hand, if the group has had recent activity, but the group name does not contain any confidential or sensitive information, you may opt to let the Tool make that group an internal only group. On the other hand, if you find the group hasn't had any activity for some time, you may decide to delete the group before running the Tool.

  Whatever path you choose, we recommend you communicate clearly to the owners of these groups what changes are coming so that they can alert you. In some cases, these groups may be owned by senior leaders within your organization, so be sure to choose the appropriate communication channel when reaching out to group owners.  

### Groups without owners that have Office 365 group creation rights

#### Why do you need to add the global admin running the Alignment Tool as a group owner in groups that have no owner with Office 365 group creation rights?*

This change is done only in networks where all users do not have Office 365 group creation rights. In order to make a Yammer group an Office 365-connected group, it is necessary to have at least one group owner with Office 365 group creation rights. Because global admins have these group creation rights, adding the global admin as a group owner helps ensure that the group can become Office 365-connected.

#### What should I do about my groups without owners with Office 365 group creation rights?*

The downloadable report provides information about the groups within your enterprise network that don't have any group owners with group creation rights so that you can determine the best path forward for your organization. These group include:

- groups that have no owners;
- groups whose owners do not have Office 365 group creation rights.

If your network has a large number of these groups, you have a few options available to you.
You can allow the Tool to add you to each group as an owner so that the group can become Office 365-connected and your network is not blocked from being connected. Once a group is connected, you can, at your discretion, remove yourself from having ownership of the group  
You can review the impacted groups from the downloadable report and see if they have any recent activity or active group members. If they don't, you may elect to delete those groups before running the Tool. After those groups have been deleted, you can run the Tool. By deleting inactive groups before running the Tool, you'll reduce the number of groups that you, as a global admin, need to be added to in order to achieve Native Mode.  

You can grant Office 365 group creation rights to all users within your organization, or at least to the users that are owners of unconnected groups in Yammer, so that those groups can be connected without the global admin needing to be added as an owner. Once those groups are connected, you can choose whether or not to revoke group creation rights from some of those users who were granted access.

Whatever path you choose, we recommend you communicate clearly to the users in your network of the changes that are coming so that they can alert you of any concerns or potential issues.

### Why aren't external participants in individual conversations supported in Native Mode?*

Guests in external groups in Yammer are not currently Azure B2B guests, and so their userIDs are not associated with an account in Azure Active Directory for your Office 365 tenant. Since eDiscovery (coming soon) requires all users to be in AAD, Yammer's current model of external groups cannot be supported in Native Mode. Yammer does expect to add support for Azure B2B guests in Native Mode, so we do expect to support adding guests to groups in Yammer in the future.

## Network-level guests

### Why aren't (network level) guests supported in Native Mode?*

Network-level Guests in Yammer are not currently Azure B2B guests, and so their userIDs are not associated with an account in Azure Active Directory for your Office 365 tenant. Since eDiscovery (coming soon) requires all users to be in AAD, Yammer's (network-level) guest feature cannot be supported in Native Mode. Yammer does expect to add support for group-level Azure B2B guests in Native Mode, but we do not expect to support adding (network-level) guest support into Native Mode networks.

### What should I do about my Network-level Guests?*

The vast majority of networks have never had any Network-level Guests. If your network has had Network-level Guests in the past, it is likely those guests no longer have access due to your network enforcing Office 365 Identity.

The downloadable report provides information about the Network-level Guests in your network and their activity within the network. We recommend you use the information in the report to help you decide whether these users should continue to have access to the network. If you do want these users to have access to the network when your network is in Native Mode, you will need to provide them with new credentials associated with an AAD account. Yammer does not currently support Azure B2B, so it must be a member user account that you provide on AAD, not a guest account. This new account will not be associated with their guest account, so the user will not have access to private messages, files, or groups of the previous account, unless the new account is added to that private content.

If your company makes extensive use of Network-level Guests, you may consider delaying your move to Native Mode.

Whatever path you choose, we recommend you communicate clearly to the owners of these groups what changes are coming so that they can alert you. In some cases, these groups may be owned by senior leaders within your organization, so be sure to choose the appropriate communication channel when reaching out to group owners.

### How do I check the status of my network's migration to Native Mode?**

Any Global Admin from your tenant can check the status of your network's alignment to Native Mode by logging in to Yammer and going to the Microsoft 365 Native Mode.

### What is the main difference between Native Mode and eDiscovery?**

- *Native Mode* - A state where all the users, groups, and content from your network are compatible with (and mapped to) their counterparts in AAD/Office 365.

- *eDiscovery* - (coming soon) A new feature Microsoft will provide to customers through the [Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321).  

Yammer can offer eDiscovery to customers once all their Users, Groups, and Content can be discoverable through the Security and Compliance Center. To facilitate this process, Yammer must ensure that all Groups are Office 365 connected because eDiscoverable content must be saved in the group mailbox. Similarly, Users must have a mailbox so we can store their private conversations, and Files must be saved in SharePoint, so they can be accessed by the eDiscovery tools.

### How does Yammer in Native Mode handle file metadata?**

When files are moved to the SharePoint document library:

- Only the latest version is moved over, and the version history is not copied.

- Users can no longer mark a file as official.

- Files are marked as having been migrated to SharePoint.

### How does Yammer in Native Mode handle file name conflicts?**

When migration completes, the IT admin gets a report of any file name conflicts, and how they were handled.

You won't be able to take your network to Native Mode for Microsoft 365 until you resolve any files left behind.

### Does every Yammer user need a SharePoint license?**

No. Only one person in your organization needs a SharePoint license.

## Related articles

[Overview of Native Mode](../configure-your-yammer-network/overview-native-mode.md)

[Configure your Yammer network for Native Mode for Microsoft 365](../configure-your-yammer-network/native-mode.md)

[Office 365 Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=2111321)

[Manage Yammer data compliance](../manage-security-and-compliance/manage-data-compliance.md)

[Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md)

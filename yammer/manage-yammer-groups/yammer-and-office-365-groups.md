---
title: "Yammer and Microsoft 365 Groups"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 12/11/2019
audience: Admin
ms.topic: overview
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOP150
- MOE150
- MEW150
- MED150
ms.assetid: d8c239dc-a48b-47ab-b85e-6b4b8191a869
description: "If your network is eligible, groups in Yammer can have access to Microsoft 365 services, including a SharePoint Online team site and document library, a OneNote notebook, a plan in Planner, and a workspace in Power BI. This is called a Microsoft 365 connected group."
---

# Yammer and Microsoft 365 Groups

If your Yammer network is eligible, you can use Microsoft 365 connected groups in Yammer.

You can tell if a group in Yammer is a Microsoft 365 connected group when you see the **Microsoft 365 Resources** section in the right navigation of the Yammer group:
  
![Screenshot showing Microsoft 365 Resources](../media/195dd76c-6007-469e-9242-7889a3b217a9.png)

## Advantages of using Microsoft 365-connected groups

Microsoft 365 connected groups have many advantages over non-connected Yammer groups:

- Access Microsoft 365 services, including a SharePoint Online team site and document library, a OneNote notebook, a plan in Planner, from within Yammer. Also includes integration with Power BI and Stream.
- Create and host live events ([Live events in Yammer](../manage-yammer-groups/yammer-live-events.md))
- Use Office 365 connectors to add apps to classic Yammer ([Add apps to Yammer](https://support.office.com/article/Add-apps-to-Yammer-bbb77f10-8779-4f3d-8096-db256f8653b8))
- Manage who can create Microsoft 365 groups ([Manage who can create Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618))
- Use dynamic groups to automatically update group membership from Azure Active Directory ([Create a dynamic group](../manage-yammer-groups/create-a-dynamic-group.md))
- Edit group membership from various apps. Changes to membership made in one Microsoft 365 app apply to other Microsoft 365 apps.
- Use data classification to create your own classifications of Microsoft 365 groups, such as unclassified, corporate confidential, or top secret. ([Configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets))
- See the group in the Global Address List (GAL) in Outlook.
- Monitor group usage with the Microsoft 365 groups activity report. ([Microsoft 365 Groups activity report](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40))
- Create optional groups naming policies. ([Microsoft 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy))
- Use the optional group expiration policy to help clean up unused groups. See [Microsoft 365 Group Expiration Policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)
- Use planned additional features that will only be available with connected groups. This includes getting local data center residency for newly uploaded files that are stored in SharePoint. ([Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?LinkId=509914))
  
## Yammer configuration required to use Microsoft 365 connected groups

To use Microsoft 365 connected groups in Yammer, make sure your Yammer network meets the following requirements:

- You must [enforce Office 365 identity](../configure-your-yammer-network/enforce-office-365-identity.md) for Yammer users. When you first enforce Office 365 identity there is a seven-day trial period, after which the **Status** of your  **Office 365 Identity Enforcement** changes to **Committed**.

- Since October 16, 2018, all Yammer networks must be in a 1:1 network configuration. This means you have one Yammer network that is associated with one Office 365 tenant. This is required as of October 16, 2018. For more information, see [FAQ: Consolidating multiple Yammer networks](../configure-your-yammer-network/faq-consolidate-multiple-yammer-networks.md).

>[!NOTE]
> If you want to ensure that all of your groups are connected, please align your network to Native Mode.  To learn more about Yammer in Native Mode, see [Overview of Native Mode](../configure-your-yammer-network/overview-native-mode.md).

Here's how the process works after your network becomes eligible for connected groups:

- About 24 hours after the **Status** in **Office 365 Identity Enforcement** changes to **Committed**:
    - In the **Microsoft 365 (or Office 365) Connected Yammer Groups** section, the **Status** for your network will change to **Enabled**.

        ![Yammer admin center Security Settings showing network is set up for connected groups](../media/yam_eligible_connected_groups.png)

    - Any new groups created in Yammer that are eligible will automatically be created as Microsoft 365 connected groups.  

- After about one week, existing eligible groups will be converted to Microsoft 365 groups.

 For a group to be eligible, the following criteria must be met:

- The group owner must have Microsoft 365 group creation privileges. By default, all Microsoft 365 users have this privilege.

- The group must be a public or private internal group. Unlisted private groups and external groups can't be Microsoft 365 connected groups.

- The group must have an owner, and it must have members.

## What happens when you create a new Microsoft 365 connected Yammer group

When you create a Microsoft 365 connected group from Yammer, in addition to your regular Yammer group features, the new Microsoft 365 group is created, and a new SharePoint site and document library, OneNote notebook, and Planner are created for the group. These resources can be accessed from the Yammer group page in Yammer.

If your network has the Yammer files stored in SharePoint feature that began rollout in December 2018, new files added to the group are stored in SharePoint. To see where Yammer files are stored for your network, go to [How do I tell where my Yammer files are stored?](https://support.office.com/article/7a647cb4-6005-4350-a258-68f00a5f7b29)

>[!IMPORTANT]
> If you create a Microsoft 365 group from any other app such as Outlook, it will not include Yammer. To have the connected group include Yammer, you must create the group in Yammer.

## Yammer networks in Native Mode

When your group is a Microsoft 365 connected group, you can manage many aspects of your group through the Microsoft 365 admin center, in addition to managing them through Yammer as discussed above. All groups from Yammer networks that are in Native Mode will be manageable through these admin centers. Some of the management capabilities that can be done through the Microsoft 365 admin center include:

- Add or remove group members
- Manage group ownership
- Delete a group
- Restore a deleted group
- Rename the group
- Update the group description
- Change the group's privacy setting

## Email and Microsoft 365 connected groups

In a connected group set up from Yammer, you can have group conversations in Yammer or in Outlook. You can send an email to a group in Yammer and it will appear in the group's Yammer messages, or use the group's name from the Outlook global address list (GAL) to send email to the group that goes directly to Outlook.

Your company can continue to use groups in Yammer and groups in Outlook based on which group type better fits the scenario for a team.
  
Email notifications for Yammer messages may be sent to users depending on the preferences that they have set in their Yammer notification settings. This applies both to connected and non-connected groups.
  
## Plans for additional integration with Microsoft 365 groups

Yammer's integration with Microsoft 365 Groups started in 2017. Subsequent phases will address remaining groups types and deliver integration with Outlook calendar and enhancements for SharePoint and Planner. The best place to stay informed of change management is to follow the Yammer updates on the [Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?LinkId=509914).
  
## FAQ - Network eligibility

### Q: I'm an admin, how do I know if my Yammer network is configured correctly and eligible for Microsoft 365 connected Yammer groups?
  
A: In the Yammer admin center, go to **Network Admin** > **Security Settings**. In the **Microsoft 365 (or Office 365) Connected Yammer Groups** section, the status for your network will show as **Enabled**.
  
### Q: Can I disable Microsoft 365 Yammer connected groups?
  
A: No, but you can [Manage who can create Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups). These restrictions do not apply to tenant admins.

### Q: If I restrict who can create Microsoft 365 groups for my tenant, will the groups that restricted users create in Yammer be Microsoft 365 connected?
  
A: No. Groups created by people who you have restricted from creating Microsoft 365 groups will not be Microsoft 365 connected.
  
### Q: If I have multiple Yammer networks that are mapped to Microsoft 365, will the Microsoft 365 connected Yammer groups work?
  
A: No. The Microsoft 365 connected Yammer groups experience will work only for Office 365 tenant that is associated with a single Yammer network. See [Network migration: Consolidate multiple Yammer networks](../configure-your-yammer-network/consolidate-multiple-yammer-networks.md) for information on how to consolidate your Yammer networks. This  is required for all Yammer networks as of October 16, 2018.
  
### Q: I don't want my existing groups to get connected to Microsoft 365. Can I turn this off?
  
A: No, but you can [[Manage who can create Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups), which will also apply to the conversion of existing groups. Only groups with at least one admin with group creation privileges can be connected to Microsoft 365.

If you apply new a creation policy, this will not retroactively change groups that are already connected to Microsoft 365. This will only impact new groups moving forward.

### Q: I have an unconnected group. How can I get it to be connected?

A: When your network first becomes eligible for connected groups, all groups that meet the criteria are converted to connected groups. After that, if a group that wasn't eligible becomes eligible, for example if your network has Microsoft group creation policies applied and you add a group admin with group creation permission, the group is not automatically connected. To have a group connected, you can submit a support request to have all eligible groups in your network connected.

## FAQ - General

### Q: What kinds of Yammer groups can be Microsoft 365 connected Yammer groups?
  
A: Currently, only private and public internal groups can be connected groups. External groups and private-unlisted groups will be included in a later wave.
  
### Q: Can I make my Microsoft 365 connected Yammer group private and not list it in the Group Directory (secret)?
  
A: No. That setting is not available for Microsoft 365 connected Yammer groups.

### Q: Can I use an existing group or SharePoint site for a Microsoft 365 connected Yammer group?

A: No, a new group and resources specific to that new group are created when you create a Microsoft 365 connected group in Yammer. You can't connect a new Yammer group to an existing Microsoft 365 group, an existing SharePoint site or SharePoint document library, or an existing OneNote notebook.
  
### Q: Can I hide a Microsoft 365 connected group from the Global Address Book?

A: Yes. This requires using PowerShell. Use the following cmdlet:

```Set-UnifiedGroup -Identity [group_name] -HiddenFromAddressListsEnabled $true```

For more information about Set-UnifiedGroup, see [Set-UnifiedGroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx).

### Q: Where can I create Microsoft 365 connected Yammer groups?
  
A: Microsoft 365 connected Yammer groups can only be created in Yammer. Microsoft 365 groups created in other locations do not include a Yammer group.
  
### Q: Can I create a Microsoft 365 connected Yammer group from the Microsoft 365 admin center?
  
A: No, this will be added in later waves. However, for Microsoft 365 connected Yammer groups, you can manage members and delete groups from the Microsoft 365 admin center. Metadata updates can also be applied to groups from the admin center.
  
### Q: Can I add external users to Microsoft 365 connected Yammer groups?
  
A: No. This will cause a sync failure because external users are not managed by Azure AD.
  
### Q: How many members can my group have?
  
A: More than 1,000.
  
### Q: What happens if I delete a Microsoft 365 connected Yammer group?
  
A: All the associated Microsoft 365 content associated with the group is deleted. This includes the document library, OneNote notebook and Planner plans. These resources are soft-deleted, and can be restored by your administrator for up to 30 days.

For more information about deleting a community or group, see [Delete a community or group in Yammer](https://support.office.com/article/2a70a1f9-d081-488e-9fc7-0f7684e5a58b).

### Q: Does the Microsoft 365 group expiration policy apply to Microsoft 365 connected Yammer groups?

A: Yes. When a Microsoft 365 group is deleted because it expired, the Yammer group is deleted.

### Q: Can I have a Microsoft 365 connected Yammer group with dynamic membership

A: Yes. Any Microsoft 365 connected Yammer group can be converted to dynamic membership. See [Create a dynamic group](create-a-dynamic-group.md) for requirements and limitations.
  
### Q: In a connected group, I see there are Yammer Files and a SharePoint Online Doc Library, are these the same thing?
  
A: No, these are separate locations to store files but the members of the group have access to both locations. Files attached to Yammer messages or uploaded in a Yammer **Files** page are stored in Yammer cloud storage, and files uploaded directly to the groups SharePoint document library are stored in SharePoint.

We recommend storing content that needs the structure and management capabilities of SharePoint in the group document library. For easy, quick sharing of images and documents, or to stream videos in Yammer, we recommend continuing to use the default Yammer cloud storage.

>[!NOTE]
> As of December 2018, we are in process of rolling out Yammer files stored in SharePoint. When your network gets this new feature, new files uploaded to Yammer are stored in the group's SharePoint document library in the Apps/Yammer folder. Any files uploaded before your network gets this new feature remain in Yammer cloud storage. To see where Yammer files are stored for your network, go to [How do I tell where my Yammer files are stored?](https://support.office.com/article/7a647cb4-6005-4350-a258-68f00a5f7b29)
  
### Q: Do my Microsoft 365 connected Yammer groups follow my Microsoft 365 group naming policy?
  
A: Yes. Any new group created in Yammer will add the prefix and suffix from the group naming policy, and will not allow blocked words in the group name. For more information, see [Microsoft 365 Groups naming policy](https://support.office.com/article/6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

Note that Yammer group names can't contain the following characters: @, #, [, ], <, or >. If the naming policy includes any of these characters, regular Yammer users will not be able to create groups in Yammer. Microsoft 365 admins can still create groups in Yammer.

## FAQ - Troubleshooting

### Q: Only some of my groups were converted to Microsoft 365 groups. How do I get the rest of them converted?

When the automated conversion happened, it didn't convert groups that didn't meet the eligibility criteria. You can make the needed changes to make those groups eligible, and then [create a support ticket](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) to get them converted.

Before opening the support ticket:

- Make sure all groups have an owner, and the owners all have Microsoft 365 group creation privileges.

- Make sure all groups have members.

- If you have unlisted (secret) groups, change them to private or public groups.

To find this information, you can do a data export and look in the groups.csv file. You'll need to cross-reference the owner list with the list of people who have Microsoft 365 group creation privileges.
  
## Related articles

[Use and manage resources in my Yammer community or group](https://support.office.com/article/44af9221-503a-4736-9571-ef1353546077)

[Join and create a community or group in Yammer](https://support.office.com/article/60db6f14-fc5d-4ffb-8812-e3c0a4109e00)
  
[Manage a community or group in Yammer](https://support.office.com/article/12ce0216-0618-4576-b87a-a8c189cee0f8)

[Delete a community or group in Yammer](https://support.office.com/article/2a70a1f9-d081-488e-9fc7-0f7684e5a58b)

[Manage who can create Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)

[Export data from Yammer Enterprise](../manage-security-and-compliance/export-yammer-enterprise-data.md)

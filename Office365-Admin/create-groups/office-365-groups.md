---
title: "Overview of Office 365 Groups for administrators"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_O365GroupsAdmin'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: "Learn about Office 365 Groups."
---

# Overview of Office 365 Groups for administrators

With Office 365 Groups, you can give a group of people access to a collection of collaboration resources for those people to share. These resources include:

- A shared Outlook inbox
- A shared calendar
- A SharePoint document library
- A Planner
- Power BI
- Yammer (if the group was created from Yammer)
- A Team (if the group was created from Teams)
- Roadmap (if you have Project Online)

With an Office 365 group, you don’t have to manually assign permissions to each of these resources, because adding members to the group automatically gives them the permissions they need to the tools that the group provides.

Any Office 365 user can create a group unless you [limit group creation to a specific set of people](manage-creation-of-groups.md). Note that if you limit group creation, users who cannot create groups will not be able to create SharePoint sites, Planners, or teams. These services need to be able to create a group using the user context. Users can still participate in group activities, such as creating tasks in Planner or responding to conversations in Outlook, provided they are a member of the group.

Groups have the following roles:

- **Owners** - Group owners can add or remove members and have unique permissions like the ability to delete conversations from the shared inbox or change different settings about the group. Group owners can rename the group, update the description or picture and more.
- **Members** - Members can access everything in the group, but can't change group settings.
- **Guests** - Group guests are members who are from outside your organization. By default group members can invite guests to join your group, though you can [control that setting](manage-guest-access-in-groups.md).

People in the following Office 365 admin roles can create and manage groups in the admin center: global admin, Exchange admin, user management admin. You can't be a delegated admin (for example, a consultant who is an admin on behalf of).

As an administrator, you can:

- [Specify who can create groups](manage-creation-of-groups.md)
- [Create a naming policy for groups in your organization](groups-naming-policy.md)
- [Choose which domain to use when creating a group](choose-domain-to-create-groups.md)
- [Manage guest access to groups](manage-guest-access-in-groups.md)
- [Recover a deleted group](restore-deleted-group.md) (within 30 days of deletion)

If you prefer a more automated way to manage the lifecycle of your Office 365 Groups you can use expiration policies to expire groups at a specific time interval. The group's owners will get an email 30, 15 and 1 day before the group expiration that allows them to easily renew the group if it's still needed. See: [Office 365 Group Expiration Policy](office-365-groups-expiration-policy.md).

You can administer your groups from the Office 365 Admin Center or [by using PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

If you have a lot of users, such as in a large corporation or enterprise, you may have many users who create groups for various purposes. We highly recommend that you review [Plan for governance in Office 365 Groups](plan-for-groups-governance.md) for best practices.

## Group limits

The following limits apply to Office 365 Groups:

|Maximum...|Value|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Groups an admin can create|Up to default tenant limit of 500K|
|Number of members|More than 1,000, though only 1,000 can access the Group conversations concurrently. <br>Users might notice delays when accessing the calendar and conversations in very large groups in Outlook.|
|Number of Groups a user can be a member of|1,000|
|File storage|1 Terabyte + 10 GB per subscribed user + any additional storage purchased. You can purchase an unlimited amount of additional storage.|
|Group Mailbox size|50 GB|

The default maximum number of Office 365 Groups that an Office 365 organization can have is currently 500,000, but can be increased by request. For more information on Office 365 Groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

Managing your Office 365 Groups is more effective when you have actionable information about Groups usage. The Office 365 Admin Center has a reporting tool that can let you see things such as storage use, how many active Groups you have and even how your users are using the Groups. See: [Office 365 Reports in the admin center](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups) for more information.

## Which Office 365 plans include Groups?

Any Office 365 subscription that has Exchange Online and SharePoint Online will support groups. That includes the Business Essentials and Business Premium plans, and the Enterprise E1, E3 and E5 plans. Group users need an Exchange Online license at minimum. The Group takes on the licensing of the person who creates the Group (also known as the "organizer" of the Group). As long as the organizer has the proper license for whatever features you want the Group to have, that license will convey to the Group.

If you have an Exchange-only plan you can still get the shared Inbox and shared Calendar features of groups in Outlook but you won’t get the document library, Planner or any of the other capabilities. If you want to use advanced security or compliance features for the shared mailbox created with a group, you need to assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.

If you have a Yammer-only plan you will still have the conversations feed in the Yammer group but you won't get the document library, Planner, or any of the other capabilities.

Office 365 Groups works with Azure Active Directory (AAD). The Groups features you get depends on which Azure Active Directory subscription you have. While most group features are available with the Azure Acitve Directory license that comes with Office 365, the following groups features require group owners and members to have Azure Active Directory Premium P1:

- [Dynamic group membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)
- [Granular self-service group creation controls](manage-creation-of-groups.md)
- [Group Naming Policy](groups-naming-policy.md)
- [Group Expiry](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
- [Usage Guidelines](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Sensitivity labels](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)
- [Self-service group management via myapps.microsoft.com](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

> [!IMPORTANT]
> For all the Groups features, if you have an Azure AD Premium subscription, users can join the group whether or not they have an AAD P1 license assigned to them. Licensing isn't enforced.
> Periodically we will generate usage reports that tell you which users are missing a license, and need one assigned to them to be compliant with the licensing requirements. For example, let's say a user doesn't have a license and they are added to a group where the naming policy is enforced. The report will flag for you that they need a license.

## Related topics

[Learn about Office 365 Groups](https://support.office.com/en-us/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Upgrade distribution lists to Office 365 Groups](../manage/upgrade-distribution-lists.md)

[Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)

[SharePoint Online Limits](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

---
title: "Microsoft Planner for admins"
f1.keywords:
- CSH
ms.author: ryany
author: efrene
manager: pamgreen
ms.date: 08/14/2019
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: high
search.appverid:
- MET150
description: "This article shares information on how admins can control and manage access to Planner, as well as answers to some other frequently asked questions about the management of Planner."
---

# Microsoft Planner for admins

In this article:

- [How do I turn off Planner for my organization?](#how-do-i-turn-off-planner-for-my-organization)
- [How do I manage who can create a plan?](#how-do-i-manage-who-can-create-a-plan)
- [How do I change the domain that Planner email notifications come from?](#how-do-i-change-the-domain-that-planner-email-notifications-come-from)
- [Can people outside of my organization get invited to participate in a plan?](#can-people-outside-of-my-organization-get-invited-to-participate-in-a-plan)
- [Can people in my organization use Planner if they don't have an Exchange Online mailbox?](#can-people-in-my-organization-use-planner-if-they-dont-have-an-exchange-online-mailbox)
- [How do I make sure all my users can get emails for Planner?](#how-do-i-make-sure-all-my-users-can-get-emails-for-planner) 
- [How do I turn off Outlook calendar sync in Planner for my organization?](#how-do-i-turn-off-outlook-calendar-sync-in-planner-for-my-organization)
- [How do I turn off the Planner Loop component for my organization?](#how-do-i-turn-off-planner-for-my-organization)
- [How do I install or activate Planner for my organization?](#how-do-i-install-or-activate-planner-for-my-organization)
- [Can I see who is already using Planner, or see a list of all the Planner sites?](#can-i-see-who-is-already-using-planner-or-see-a-list-of-all-the-planner-sites)
- [How can I apply CA policies to the Planner iOS and Android apps?](#how-can-i-apply-ca-policies-to-the-planner-ios-and-android-apps)

## How do I turn off Planner for my organization?

When Microsoft Planner is included in your subscription, it's automatically turned on for everyone in your organization. If you want to control which people in your organization have licenses for Planner, for example, if your organization isn't ready to begin using Planner, you can remove or assign Planner licenses by using Office 365 PowerShell.

To control which users have Planner licenses, follow the instructions in [How to use Office 365 PowerShell to manage Microsoft Planner licenses](/office365/troubleshoot/licensing/how-to-use-office-365-powershell-to-manage-microsoft-planner-licenses). When running the scripts in Office 365 PowerShell, the DisabledPlans value for Microsoft Planner is PROJECTWORKMANAGEMENT.

To turn off just the Planner Loop component, see [How to turn off the Planner component for your organization](disable-planner-component.md).

> [!NOTE]
> Removing a user's Planner license only prevents them from navigating to Planner using the Planner tile. Users in your organization without licenses to Planner can still create and modify plans at the direct Planner URL: tasks.</span>office.</span>com. You can remove users' ability to create plans at tasks.office.com (see [How do I manage who can create a plan?](#how-do-i-manage-who-can-create-a-plan)), but you can't remove their ability to see and modify existing plans at tasks.</span>office.</span>com at this time.

## How do I manage who can create a plan?

Every time a person in your organization creates a plan in Planner, the plan's list of members automatically form a [Microsoft 365 group](https://support.office.com/en-us/article/learn-about-microsoft-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2). So to control who creates a plan, you need to control who can create Microsoft 365 Groups.

Admins can control who can create a Group by using Azure AD PowerShell. Follow the instructions in [Control who can create Microsoft 365 Groups](https://support.office.com/en-us/article/control-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618) to:

1. Disable Group creation for all users in your organization.
2. Allow specific users to create groups (for example, all Planner users) while group creation is disabled.

> [!IMPORTANT]
> 
> - Disabling group creation for your organization will affect users of other Microsoft services that need group creation, such as Exchange Online. Make sure to account for all people in your organization that need the ability to create groups when you configure this setting.
> - Controlling who can create Microsoft 365 Groups only prevents users from creating new plans. They will still be able to see and modify existing plans at tasks.</span>office.</span>com.

## How do I change the domain that Planner email notifications come from?

If you are interested in having your notification emails come from a custom email domain, follow the steps described in [Multi-domain support for Microsoft 365 Groups - Admin help](https://support.office.com/article/multidomain-support-for-office-365-groups--admin-help-7cf5655d-e523-4bc3-a93b-3ccebf44a01a).

## Can people outside of my organization get invited to participate in a plan?

Yes. Guest access allows you to invite people who aren't part of your Microsoft 365 organization to participate in a plan. Guest users will have limited functionality, but can perform the following tasks:

- Create and delete tasks and buckets
- Edit task fields
- Attach a file or link to a task, if given additional permission
- Edit the plan name

For more information, see [Guest access in Microsoft Planner](https://support.office.com/article/guest-access-in-microsoft-planner-cc5d7f96-dced-4da4-ab62-08c72d9759c6).

## Can people in my organization use Planner if they don't have an Exchange Online mailbox?

- If you are using Microsoft Planner in a hybrid environment in which your users may have Exchange Online or on-premises mailboxes, note that:
- Planner has full functionality when your user has a product license that includes Exchange Online. Planner users without Exchange Online may have issues with viewing or adding comments to a task.

## How do I make sure all my users can get emails for Planner?

In Planner, users can choose to receive emails when tasks are assigned to them or when tasks are due soon or late (see [Choose whether to have email sent directly to you](https://support.office.com/article/stay-on-top-of-tasks-and-plans-with-email-and-notifications-cce223d6-b0ae-43cf-a080-266e2414a859#bkmk_choosewhethertohaveemailsenttoyou_1_1_1_1_1)). However, email will only be sent to users who have a product license that includes Exchange Online. Users at organizations using on-premises Exchange Server or hybrid configurations may not receive all Planner emails.

## How do I turn off Outlook calendar sync in Planner for my organization?

Outlook calendar sync in Microsoft Planner allows users to view their Planner schedule in Outlook. This feature is turned on automatically in Planner. If you want to turn this off for your organization, follow the steps in [Turn off Outlook calendar sync in Planner for your organization](turn-off-outlook-calendar-sync.md).

## How do I turn off the Planner Loop component for my organization?

The Planner component allows users to view and edit Planner plans as a Loop component in the Loop app and in Microsoft apps that support Loop, for example, in Outlook and Teams. To turn off the component for your organization, follow the steps in [How to turn off the Planner component for your organization](disable-planner-component.md).

See [Use the Planner component in Loop](https://support.microsoft.com/office/use-the-planner-component-in-loop-545e967a-7c69-4e9a-9458-dfabdcf1d752) for details on how the component can be used.

> [!NOTE]
> The Planner component is a new feature that may not yet be available in all Microsoft apps that support Loop.

## How do I install or activate Planner for my organization?

Planner comes with these subscriptions:

- Microsoft 365 Business Basic
- Microsoft 365 Business Standard
- Office 365 E1
- Office 365 E3
- Office 365 E5
- Microsoft 365 A1

For more on these subscriptions, see [business plans](https://www.microsoft.com/microsoft-365/business), [enterprise plans](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), or [education plans](https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans). If your current subscription doesn't include Planner, the only way to get Planner is to switch to a subscription that does.

## Can I see who is already using Planner, or see a list of all the Planner sites?

You can see a list of all groups in the Microsoft 365 admin center, in the Groups section, and find out more detailed information about these groups using [Microsoft 365 Reports in the admin center - Microsoft 365 Groups](https://support.office.com/article/office-365-reports-in-the-admin-center--office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40). Every group comes with a plan, but a list of plans and active usage of plans are not included in these reports right now.

## How can I apply CA policies to the Planner iOS and Android apps?

To apply CA policies to the Planner iOS and Android apps, please make sure that CA policies are enabled for Exchange or SharePoint within Microsoft Intune in the Azure portal. Enabling CA policy for Planner alone (without policies enabled for Exchange or SharePoint) does not apply the policies for the Planner iOS and Android apps.

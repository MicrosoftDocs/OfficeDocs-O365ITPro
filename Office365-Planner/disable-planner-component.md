---
title: "How to turn off the Planner component for your organization"
description: "Learn what the Planner component is and how to turn off for specific users, groups, or your organization in Microsoft apps that support Loop."
ms.author: dahopkin
author: dahopkin
manager: hoyort
ms.date: 06/05/2023
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localization_priority: medium
---

# How to turn off the Planner component for your organization

## What is the Planner component?
The Planner component allows users to view and edit Planner plans as a Loop component in the same way that they can view and edit plans in the Planner web app. It's available in the Loop app and in Microsoft apps that support Loop, for example, in Outlook and Teams.

In the Loop app, for example, users can either choose **Planner** from the menu or paste the URL for a plan into a Loop page. Once pasted, it renders Planner UX inline in that page so that they can view and edit that plan.

See [Use the Planner component in Loop](https://support.microsoft.com/office/use-the-planner-component-in-loop-545e967a-7c69-4e9a-9458-dfabdcf1d752) for details on how the component can be used.

> [!NOTE]
> The Planner component is a new feature that may not yet be available in all Microsoft apps that support Loop.

## How do I turn off the Planner component for my organization?
The Planner component can be disabled via the **View and edit Planner plans with the Planner Loop component** cloud policy setting. This policy setting controls whether users can view and edit Planner plans as a Loop component in the Loop app and in Microsoft apps that support Loop. See [Overview of Cloud Policy service for Microsoft 365](/deployoffice/admincenter/overview-cloud-policy) for steps to configure cloud policies.

## How do I turn off the Planner component for specific users in my organization?
To turn off the Planner component for specific users in your organization, you can scope the policy setting in [How do I turn off the Planner component for my organization?](#how-do-i-turn-off-the-planner-component-for-my-organization) to a new or existing Microsoft 365 group that defines the users in your organization that the policy should apply to. You can learn how to create a Microsoft 365 group by visiting [Create a Microsoft 365 group](/microsoft-365/admin/create-groups/create-groups). If you prefer, you can also create other types of groups to use with Cloud Policy. See [learn more about creating groups in the Microsoft 365 admin center](/microsoft-365/admin/email/create-edit-or-delete-a-security-group) or [learn more about creating dynamic groups in AzureAD](/azure/active-directory/external-identities/use-dynamic-groups).

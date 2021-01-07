---
title: "Disable the creation of Roster containers in your organization's Planner tenant"
f1.keywords:
- NOCSH
ms.author: nisteidl
author: nisteidl
manager: arshishk
ms.date: 01/05/2021
audience: Admin
ms.topic: Overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
description: "This article shares information on how admins can disable the creation of Roster containers."
---

# Disable the creation of Roster containers in your organization's Planner tenant

## Roster Container Overview
Roster containers allow for collaboration between users without the creation of an AAD group.
A Roster container is a simple list of members stored in Planner and can be created by any user including guest users.

All members of a Roster container have the same permissions to:
   - add/remove members to the Roster
   - create/edit/delete tasks, the plan and the Roster itself

The Roster and the plan contained by the Roster automatically self-delete when the last member is removed from the roster. This could be because all the users are removed by a member, or the last user in the roster was deleted.

## Prerequisites for making Planner changes in Windows PowerShell

First, you will need to follow [these](prerequisites-for-powershell.md) steps in order to make Planner changes in Windows PowerShell.

## Disable the creation of Roster containers in your organization's Planner tenant

1. Open PowerShell and run the following command to disable the creation of Roster containers in your tenant (it is enabled by default):

   `Set-PlannerConfiguration -AllowRosterContainers $false`

    Disabling creation will not remove or prevent the use of existing Roster container based plans.
   
    If you’ve changed your mind and would like to allow Roster containers to be created in your tenant, run the following command.

   `Set-PlannerConfiguration -AllowRosterContainers $true`

   > [!NOTE]
   > You'll need to sign in using your Azure Active Directory credentials and use a local PowerShell window (not Azure Cloud Shell).

2. To verify your settings:

   - In PowerShell, run: `Get-PlannerConfiguration`.
   - The AllowRosterContainers value returned by this command indicates whether the creation of Roster containers is allowed.
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
description: "This article shares information on how admins can control and manage access to Planner, as well as answers to some other frequently asked questions about the management of Planner."
---

# Disable the creation of Roster containers in your organization's Planner tenant

## Roster Container Overview
Roster containers allow for collaboration between users without the creation of an AAD group as the roster's membership is stored in Planner.

## Prerequisites for making Planner changes in Windows PowerShell

First, you will need to follow [these](prerequisites-for-powershell.md) steps in order to make Planner changes in Windows PowerShell.

## Disable the creation of Roster containers in your organization's Planner tenant

1. Open PowerShell and run the following command to disable the creation of Roster containers in your tenant (it is enabled by default):

   `Set-PlannerConfiguration --AllowRosterContainers $false`

    Disabling creation will not remove or prevent the use of existing Roster container based plans.
   
    If you’ve changed your mind and would like to allow Roster containers to be created in your tenant, run the following command.

   `Set-PlannerConfiguration -AllowRosterContainers $true`

   > [!NOTE]
   > You'll need to sign in using your Azure Active Directory credentials and use a local PowerShell window (not Azure Cloud Shell).

2. To verify your settings:

   - In PowerShell, run: `Get-PlannerConfiguration`.
   - The AllowRosterContainers value returned by this command indicates whether the creation of Roster containers is allowed.
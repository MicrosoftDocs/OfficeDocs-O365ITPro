---
title: "Turn off Outlook calendar sync in Planner for your organization"
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/14/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
search.appverid:
- MET150
description: "If you are a global admin and you want to turn off calendar sync in Microsoft Planner, you can use Windows PowerShell"
---

# Turn off Outlook calendar sync in Planner for your organization

If you are a global admin and you want to turn off calendar sync in Microsoft Planner, you can use Windows PowerShell. Planner is automatically turned on for all organizations that have Planner as part of their subscription.

- [Prerequisites for making Planner changes in Windows PowerShell](#prerequisites-for-making-planner-changes-in-windows-powershell)
- [Turn off or on Outlook calendar sync in Planner using PowerShell](#turn-off-or-on-outlook-calendar-sync-in-planner-using-powershell)

> [!NOTE]
> Looking for how to sync your personal Outlook calendar with Planner? [See your Planner calendar in Outlook](https://support.office.com/article/see-your-planner-calendar-in-outlook-5dcccce5-2750-49b5-991b-1837379d96c7).

## Prerequisites for making Planner changes in Windows PowerShell

Follow the steps in [Prerequisites for making Planner changes in Windows PowerShell](prerequisites-for-powershell.md) to make Planner changes in Windows PowerShell.

## Turn off or on Outlook calendar sync in Planner using PowerShell

1. Open PowerShell and run the following command to turn off Outlook calendar sync for Planner:

   ```PowerShell
   Set-PlannerConfiguration -AllowCalendarSharing $false
   ```

   To turn Outlook calendar sync back on in Planner:

   ```PowerShell
   Set-PlannerConfiguration -AllowCalendarSharing $true
   ```

   > [!NOTE]
   > You'll need to sign in using your Azure Active Directory credentials.

2. To verify your settings, run:

   ```PowerShell
   Get-PlannerConfiguration
   ```
   - In Planner, go to **Planner** > **My Tasks**. Select the ellipses (...). Outlook calendar sync is enabled if you see the **Add "My Tasks" to Outlook calendar** command, and disabled if you don't.

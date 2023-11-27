---
title: Disabling direct-push notifications for your organization
f1.keywords:
- NOCSH
ms.author: wirawlin
author: WiRawlinWork
manager: arshishk
ms.date: 03/08/2021
audience: Admin
ms.topic: Overview
layout: LandingPage
ms.service: o365-administration
ms.localizationpriority: high
search.appverid:
- MET150
description: "If you are a tenant admin who wants to disable direct push mobile notifications in Planner, change this setting via Powershell"
---

# Disabling direct-push planner mobile notifications

## Overview

Because Planner is moving to a new system which uses a direct-push mechanism, we are adding the ability to turn off these direct-push notifications.  Details on this switch are covered in this article.

1. Direct-Push indicates that the contents of the push notification are being sent directly through Apple's or Google's services to get to the iOS or Android client, respectively. (This is the new system)

2. Push-to-Pull indicates that a string is sent through Apple/Google's services that tells the client how to retrieve the notification from a server controlled by Microsoft, without the actual contents of the notification passing through a 3rd party service. (This is the old system)

> [!NOTE]
> The switch only affects push notifications that are being sent through the new system.  Any notifications still being sent through the old system are unaffected by the tenant switch.

> [!NOTE]
> The effect is not instantaneous. It will take a few minutes after running the command to change the setting.

## Prerequisites for making Planner changes in Windows PowerShell

Follow the steps in [Prerequisites for making Planner changes in Windows PowerShell](prerequisites-for-powershell.md) to make Planner changes in Windows PowerShell.

## Disable direct-push notifications

1. Open PowerShell and run the following command to disable the notifications 

   ```PowerShell
   Set-PlannerConfiguration -AllowPlannerMobilePushNotifications $false
   ```
   
   Likewise, if you want to re-enable, run the below command 

   ```PowerShell
   Set-PlannerConfiguration -AllowPlannerMobilePushNotifications $true
   ```

   > [!NOTE]
   > You'll need to sign in using your Microsoft Entra credentials and use a local PowerShell window (not Azure Cloud Shell).

2. To verify your settings, run:

   ```PowerShell
   Get-PlannerConfiguration
   ```
   - The AllowPlannerMobilePushNotifications value returned by this command indicates whether the notifications are enabled
   

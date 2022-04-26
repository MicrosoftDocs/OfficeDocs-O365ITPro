---
title: "Block a user from deleting tasks in Microsoft Planner they didn't create"
f1.keywords:
ms.author: v-cichur
author: danfi
manager: danfi
ms.date: 02/23/2021
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
search.appverid:
description: "This article shares information on how admins can block a user from deleting tasks the user didn't create"
---

# Block a user from deleting tasks not created by themselves

Tenant admins can block a specific user from deleting tasks in Microsoft Planner that they didn't create.

## Prerequisites for making Planner changes in Windows PowerShell

Follow the steps in [Prerequisites for making Planner changes in Windows PowerShell](prerequisites-for-powershell.md) to make Planner changes in Windows PowerShell.

## Block a user from deleting tasks they didn't create

1. Use the Set-PlannerUserPolicy cmdlet to block a user from deleting Planner tasks that they didn't create.

   ```PowerShell
    Set-PlannerUserPolicy -UserAadIdOrPrincipalName <user's AADId or UPN> -BlockDeleteTasksNotCreatedBySelf $true
   ```

   |Parameter|Description|
   |:-------------------------|:---|
   |UserAadIdOrPrincipalName|Use either the Azure Active Directory ID or the UPN of the user for which you want to export content.|
   |BlockDeleteTasksNotCreatedBySelf|Whether or not to block the user from deleting tasks not created by themselves.|
   |HostName|You only need to use this parameter if you access Planner though a host name other than `task.</span>office.</span>com`. For example, if you access Planner through `tasks.</span>office365.</span>us`, include `-HostName tasks.</span>office365</span>.us` in your command.|
   |||

    The following cmdlet will block a user from deleting tasks in Planner that they didn't create.

      ```PowerShell
       Set-PlannerUserPolicy -UserAadIdOrPrincipalName amyg@contoso.onmicrosoft.com -BlockDeleteTasksNotCreatedBySelf $true
      ```

2. When you're prompted to authenticate, sign in as yourself (the global admin), not the user you want to unblock.

## Unblock a user from deleting tasks they didn't create

1. Use the Set-PlannerUserPolicy cmdlet to unblock a user from deleting Planner tasks that they didn't create.

   ```PowerShell
     Set-PlannerUserPolicy -UserAadIdOrPrincipalName "<User's AAD ID or UPN>"  -BlockDeleteTasksNotCreatedBySelf $false
   ```

   |Parameter&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Description|
   |:---|:---|
   |UserAadIdOrPrincipalName|Use either the Azure Active Directory ID or the UPN of the user for which you want to export content.|
   |BlockDeleteTasksNotCreatedBySelf&nbsp;|Whether or not to block the user from deleting tasks not created by themselves.|
   |HostName|You only need to use this parameter if you access Planner though a host name other than `task.</span>office.</span>com`. For example, if you access Planner through `tasks.</span>office365.</span>us`, include `-HostName tasks.</span>office365</span>.us` in your command.|
   |||

    For example, the following cmdlet will block a user from deleting tasks in Planner that they didn't create.

     ```PowerShell
      Set-PlannerUserPolicy -UserAadIdOrPrincipalName amyg@contoso.onmicrosoft.com -BlockDeleteTasksNotCreatedBySelf $false
     ```

2. When you're prompted to authenticate, sign in as yourself (the global admin), not the user you want to unblock.

## Get a user's current policy

1. Check a user's current policy with the Get-PlannerUserPolicy cmdlet.

    ```PowerShell
      Get-PlannerUserPolicy -UserAadIdOrPrincipalName "<User's AAD ID or UPN>"
    ```

   |Parameter&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Description|
   |------------------------|---|
   |UserAadIdOrPrincipalName|Use either the Azure Active Directory ID or the UPN of the user for which you want to export content.|
   |HostName|You only need to use this parameter if you access Planner though a host name other than `task.</span>office.</span>com`. For example, if you access Planner through `tasks.</span>office365.</span>us`, include `-HostName tasks.</span>office365</span>.us` in your command.|
   |||

   For example, the following cmdlet will get a user's current policy

    ```PowerShell
     Get-PlannerUserPolicy -UserAadIdOrPrincipalName amyg@contoso.onmicrosoft.com | fl
     @odata.context                   : https://tasks.office.com/taskApi/tenantAdminSettings/$metadata#UserPolicy/$entity
     id                               : amyg@contoso.onmicrosoft.com
     blockDeleteTasksNotCreatedBySelf : False
   ```

2. When you're prompted to authenticate, sign in as yourself (the global admin).

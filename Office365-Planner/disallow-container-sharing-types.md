---
title: "Disallow container types for usage in container sharing"
f1.keywords:
- NOCSH
ms.author : farzaddaei
author: farzaddaei
manager: mikemoin
ms.date: 12/18/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
search.appverid:
- MET150
description: "This article shares information on how admins can disallow certain container type pairs from container sharing"
---

# Disallow container types for usage in container sharing

## Container Sharing Overview

### Glossary

- `Container` – a container in Planner Context is the resource that specifies authorization rules and the lifetime of the plan (e.g. M365 group, roster, drive item).
- `Host container` – the container that the plan is contained by. This is the [Plan.Container](/graph/api/resources/plannerplan) of the OData API.
- `Shared container` – a container that a plan has been shared with so that users with access to the container are granted access to the plan.

### Overview

Container sharing allows Planner to extend authorization of a plan from a single container to multiple. When a plan is shared with a "shared container", it allows users who don't have access to the host container, but who do have access to that container to access the plan.

> Currently only plans with a `roster` host container can be shared with a `driveItem` container and all other pairings are disabled by Planner. This is to enable certain scenarios in Loop.

### Container types

Review the current [list of container types supported](/graph/api/resources/plannerplancontainer).

## Prerequisites for making Planner changes in Windows PowerShell

Follow the steps in [Prerequisites for making Planner changes in Windows PowerShell](prerequisites-for-powershell.md) to make Planner changes in Windows PowerShell.

## Disallow container types for usage in container sharing

Disallowing a Host Container, Shared Container type pair will not remove any existing relationship or disallow the creation of the relationship but it will no longer authorize users through an existing/new share of that type.

> [!NOTE]
> You'll need to sign in using your Azure Active Directory credentials and use a local PowerShell window (not Azure Cloud Shell).

Open PowerShell and run the following command to disallow container types for usage in container sharing (all types are allowed by default):

```powershell
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes @(@{hostContainerType = "<The type of the host container>"; sharedWithContainerType = "<The type of the shared with container>"})
```

> [!NOTE]
> Updating the setting replaces the previous configuration; should you want to add an additional disallowed pair, you must update the setting to the entire collection of disallowed pairs.

## Examples

### Disallow a single type pair

The following cmdlet will disallow plans contained by a `group` to be shared with a `roster` container:

```powershell
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes @(@{hostContainerType = "group"; sharedWithContainerType = "roster"})
```

### Disallow multiple type pairs

The following cmdlet will disallow plans contained by a `group` to be shared with a `roster` and plans contained by a `roster` to be shared with a `driveItem` container:

```powershell
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes @(@{hostContainerType = "group"; sharedWithContainerType = "roster"},@{hostContainerType = "roster"; sharedWithContainerType = "driveItem"})
```

### Add a disallowed pair to an existing list

The following cmdlet will disallow plans contained by a `roster` to be shared with a `group` to an existing disallow list by retriving the setting and adding to the collection:

```powershell
$configuration = Get-PlannerConfiguration
$configuration.DisallowedSharedWithContainerTypes += @{hostContainerType = "roster"; sharedWithContainerType = "group"}
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes $configuration.DisallowedSharedWithContainerTypes
```

> [!NOTE]
> Changes to the settings are not reflected immediately and it may take a few minutes after running the command to change the setting. Please ensure your previous changes have been applied by [verifying your changes](#verifying-your-changes).

### Re-allow all types

If you’ve changed your mind and would like to allow all types, reverting to the default behaviour, you can do so by running in the powershell:

```powershell
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes @()
```

## Verifying your changes

To verify your settings:

- In PowerShell, run:

  ```powershell
  Get-PlannerConfiguration
  ```

- The _DisallowedSharedWithContainerTypes_ value returned by this command indicates the type pairings that are disallowed.

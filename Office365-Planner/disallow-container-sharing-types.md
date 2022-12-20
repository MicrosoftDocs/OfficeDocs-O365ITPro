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

- `Container` – a resource that specifies authorization rules and the lifetime of the plan (e.g. M365 group, roster, drive item).
- `Host container` – the container that the plan is contained by.
- `Shared container` – a container that a plan has been shared with so that users with access to the container are granted access to the plan.

### Overview

Container sharing allows planner to extend its authorization from a single container to multiple. When a plan is shared with another "shared container", it allows users who may have access to that container access to the plan.

### Container types

Review the current list of container types supported at [plannerPlanContainer resource type](https://learn.microsoft.com/en-us/graph/api/resources/plannerplancontainer?view=graph-rest-beta).

## Prerequisites for making Planner changes in Windows PowerShell

Follow the steps in [Prerequisites for making Planner changes in Windows PowerShell](prerequisites-for-powershell.md) to make Planner changes in Windows PowerShell.

## Disallow container types for usage in container sharing

Disallowing a type pair will not remove any existing relationship or disallow the creation of the relationship but it will no longer authorize users through an existing/new share of that type.

> [!NOTE]
> You'll need to sign in using your Azure Active Directory credentials and use a local PowerShell window (not Azure Cloud Shell).

Open PowerShell and run the following command to disallow container types for usage in container sharing (all types are allowed by default):

```powershell
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes @(@{hostContainerType = "<The type of the host container>"; sharedWithContainerType = "<The type of the shared with container>"})
```

> [!NOTE]
> Updating the setting replaces the previous configuration; should you want to add an additional disallowed pair, you must update the setting to the entire collection of disallowed pairs.

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

### Re-allow all types

If you’ve changed your mind and would like to allow all types, reverting to the default behaviour, you can do so by running in the powershell:

```powershell
Set-PlannerConfiguration -DisallowedSharedWithContainerTypes @()
```

### Verifying your changes

To verify your settings:

- In PowerShell, run:

  ```powershell
  Get-PlannerConfiguration
  ```

- The _DisallowedSharedWithContainerTypes_ value returned by this command indicates the type pairings that are disallowed.

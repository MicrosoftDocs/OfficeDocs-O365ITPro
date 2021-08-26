---
title: Organization directory network
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
audience: Admin
ms.date: 05/08/2019
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.reviewer: nitinjms2
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to classify users in organization directory categories.
---

# Organization directory network 

Organization directory is classified into two networks: *Employee* and *Others*. Microsoft Kaizala enables organizations to classify their users as employees. Unclassified users are part of Others.

## View all users in a network
On the Kaizala management portal, from the left navigation pane, choose **Directory**. You'll find two organization networks stacked as tabs: **Employee** and **Others**.

### View Employee users

On the **Employee** tab, you can find a list of all users classified as Employees in your organization. These include:

- Users added by an organization admin as Employees, either in bulk or individually.
- Users synced automatically from Azure Active Directory (Azure AD).
- Users who have signed in to their Kaizala mobile app using an Office 365 account.

### View Others users

On the **Others** tab, you can find a list of all users that have not been classified into any other network in your organization. These include:

- Non-employee users added by a group admin to their organization groups.
- Users added by an organization admin as Others, either in bulk or individually.

## Move users within networks

Organization admins can move users between different networks. To move users between networks:

1. Select users that you want to move between networks.
2. Select **Move to Employees** if you have selected users in Others network. Or, select **Move to Others** if you have selected users in Employees network.

> [!NOTE]
> Employees who either have Azure AD users or have signed in to their Office 365 account cannot be moved to Others network.
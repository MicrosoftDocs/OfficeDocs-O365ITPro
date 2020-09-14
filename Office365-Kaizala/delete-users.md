---
title: Delete users from the organization directory in Kaizala
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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to delete users to the organization directory in Kaizala.
---

# Delete users from the organization directory in Kaizala

Organization admins only can delete users from an organization. They can delete users one at a time or delete multiple users at the same time.

## Delete a single user

1. On the [Kaizala management portal](https://manage.kaiza.la), from the left navigation bar, select **Directory**.
2. Select a user from the user list for your organization.
3. Click on that user to see that user's detailed view.
4. Select **Delete**.

## Delete multiple users

1. On the [Kaizala management portal](https://manage.kaiza.la), from the left navigation bar, select **Directory**.
2. Select the users from the network-specific user list that you want to delete. A maximum of 100 users can be selected.
3. Select **Delete**.

> [!NOTE]
> - Azure Active Directory (Azure AD) linked users cannot be deleted from the Kaizala organization directory using Kaizala management portal.
> - If an Azure AD user is deleted from Azure AD, the user is automatically deleted from the Kaizala organization directory.

Once you delete a user, that user gets removed from all organizational groups on Kaizala. All data – including messages, Kaizala Actions, and attachments – for these groups will be deleted from the user's device. 

---
title: AAD sync with the Kaizala Tenant User List
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: Admin
ms.date: 01/08/2018
ms.topic: article
ms.service: Kaizala
ms.custom: Kaizala
ms.reviewer: kavempar
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to enable and disable Azure Active Directory (AAD) sync feature in Kaizala.
---

# AAD sync with Kaizala Tenant User List

The Azure Active Directory (AAD) sync feature lets you sync user information in AAD with the Kaizala Tenant User List (TUL). As an admin, you can import data and sync changes occurring in your AAD. You can use this feature for:

- **User management** - Any user changes in AAD are automatically synced with the organization directory and associated groups. For example, if a user’s phone number is changed in the AAD, the information will be updated in the organization directory. Similarly, if a user is deleted from the organization’s AAD, the user is automatically removed from the organization group.

- **Dynamic group management** - Allows you to dynamically create and manage groups based on rules and user attributes. For example, you can set a rule to create a group for employees with the *Senior Manager* designation in the *Finance* department.

### Prerequisite

You must be a Kaizala organization admin with a Kaizala Pro license. 

## How the AAD sync feature works

- New users added in the AAD of the organization are automatically added to the organization directory.
- Users deleted from the AAD are automatically removed from the organization directory and all organization groups.
- Any information change in the AAD will sync with the TUL. For example, if designation of a user is changed in the AAD, the change is automatically reflected in the organization directory. 

## Configure the AAD-TUL sync

To configure the AAD and Kaizala TUL sync:

1. Log in to the [Kaizala management portal](http://manage.kaiza.la).

2. From the menu on the left, select **Users**.

3. Select **Add Users**, and then select **Configure AAD Sync**.

![Screenshot of the Add Users window in AAD Sync.](media/aad-sync-configure.png)

4. Under **AAD Sync**, in the **Manage Mapping** section:
   - Review and edit name, phone number, and city information of the user to sync with ADD attribute.
   - Select **Add New Attribute** to add more information. 

![Screenshot of the Manage Mapping window in AAD Sync.](media/aad-sync-attributes.png)

5. In the **Sync Frequency** section, choose the sync frequency to meet your requirement:
   - Select **One-time** to sync just once.
   - Select **Recurring** to sync every day. 

6. Select **Next** to start the ADD-TUL data sync. 
   > [!NOTE]
   > After you select **Next**, the sync process will start and it will take some time for the process to complete. The AAD sync will happen regularly based on the frequency set by you.

7. You can check the sync status through logs.
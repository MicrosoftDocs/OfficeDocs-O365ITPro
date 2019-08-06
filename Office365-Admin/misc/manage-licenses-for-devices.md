---
title: "Manage licenses for devices"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'MACBillingLicensesOPPDevicesLDP'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: "Learn how to assign licenses to groups for use with devices."
---
# Manage licenses for devices

If you have Office 365 ProPlus for Devices, you can assign licenses to devices by using Azure AD groups. When a device has a license, anyone who uses that device can use Office 365. 

> [!IMPORTANT]
> Office 365 ProPlus for Devices is only available to volume licensing customers, and Education A3 or A5 customers.

To begin, you [create a group in the Azure Active Directory (Azure AD) portal](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal), and then assign devices to the group. The group can also contain users, but only devices will receive a license. You can use any of the following group types: security, distributed, or dynamic. Security groups can also contain nested groups. To learn more about device-based subscriptions, see [Device-based licensing for Office 365 ProPlus for education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!NOTE]
> You must have Azure AD Premium P1 in order to use dynamic groups.

After you create the group, it will automatically show up on the Groups page in the Microsoft 365 admin center. However, you must use the Azure AD portal to manage devices. You cannot manage devices in the Microsoft 365 admin center.

To learn more about using Azure AD groups, see [Manage app and resource access using Azure Active Directory groups](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context).

> [!IMPORTANT]
> You must be a Global admin to complete the tasks in this article.

## Assign licenses to devices

When you assign licenses to a group, you assign licenses to all devices within the group. You can only assign one subscription to any single group.

1. In the Microsoft 365 admin center, go to the **Billing** > Licenses page.
2. On the **Licenses** page, select **Office 365 ProPlus for Devices**.
3. On the **Office 365 ProPlus for Devices** page, select **Assign licenses**.
4. In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.
5. If you have more than one subscription, pick one from the **Select a subscription to assign licenses** drop-down menu. You can only assign one subscription to one group.
6. When you’re finished, select **Assign**, then select **Close**.

If there are more devices in a group than there are available licenses, a message is displayed that tells you to either remove some devices from the group, or to buy additional subscriptions.

### To assign an existing subscription to a different group:

1. On the **Office 365 ProPlus for Devices** page, select **More options** for the row that contains the subscription.
2. Select **Assign to a different group**.
3. In the **Assign to a different group** pane, begin typing a group name, and then choose it from the results to add it to the list.
4. When you’re finished, select **Assign**, then select **Close**.

## Unassign licenses from devices

When you unassign licenses from a group, you remove the licenses from all devices within the group. All apps and their associated data will be read-only.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.
2. On the **Licenses** page, select **Office 365 ProPlus for Devices**.
3. On the **Office 365 ProPlus for Devices** page, select **More options** for the row that contains the subscription.
4. Select **Unassign licenses**.
5. In the **Unassign licenses** dialog box, select **Unassign**.
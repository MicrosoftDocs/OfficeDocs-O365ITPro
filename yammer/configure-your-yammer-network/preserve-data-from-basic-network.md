---
title: "Preserve data from the Yammer Basic Network"
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 11/18/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
description: "Learn how to preserve data from the Yammer Basic Network."
ROBOTS: NOINDEX, NOFOLLOW 
---

# What happens when you add a domain to your Office 365 tenant associated with a Yammer Basic network

In Yammer, having multiple primary networks is not supported. If you add an external domain with a Yammer Basic network (“Basic network”) to your Office 365 tenant, we must disassociate the domain from the basic network in order to associate the domain with the primary network for your O365 tenant.  The basic network is then queued for deletion. 

Below is a set of actions we immediately take after you add a domain. Also, there’s a set of steps you can take to preserve the data from the network before we delete it.

Microsoft will:

- Remove all users—from the network formerly associated with the added domain—so they can access the Basic network for your Office 365 tenant if permitted to do so based on your Yammer licensing.

- Enable the network formerly associated with the added domain to allow for data export.

- Add all Global Admins from your Office 365 tenant as guests with Verified Admin privileges in the network formerly associated with the added domain.

- Disable the network formerly associated with the added domain 30 days from the date you added the domain to your Office 365 tenant.

- Queue the network formerly associated with the added domain for deletion in an additional 30 days. At that time, we will delete the network, including all the data that was in the network formerly associated with the added domain.

**To preserve data from the network formerly associated with your domain**:

1. Click Settings ![Yammer settings icon](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png) in the home Yammer network of your Office 365 tenant.

2. Choose the network formerly associated with your domain from the list of available networks.

3. Export the data for the network formerly associated with your domain. For instructions, see [Export data from Yammer Enterprise](../manage-security-and-compliance/export-yammer-enterprise-data.md). None of the data from your Yammer Basic Network will be migrated to your Yammer Enterprise network for your Office 365 tenant.

>[!NOTE]
> If you do not want to access or download content from the network formerly associated with the added domain, you don’t need to do anything. The network formerly associated with the added domain, including all data in such a network, will be automatically deleted.

## Additional information

- To learn what to do when a domain associated with a Basic Yammer network is added to your Office 365 tenant, see [Manage Yammer domains in Office 365](manage-yammer-domains.md).

- To understand the difference between Yammer Basic and Yammer Enterprise networks, see [Compare options for a free trial of Yammer](../get-started-with-yammer/compare-options-for-a-free-trial.md).

## See also

[Network migration - Consolidate multiple Yammer networks](consolidate-multiple-yammer-networks.md)

---
title: "Data residency"
f1.keywords:
- NOCSH
ms.author: v-tosadd
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 
description: "Data residency for Yammer Enterprise."
---

# Data residency
Yammer offers local data residency to help meet data residency requirements. We commit to store message bodies and files attached to messages at rest within a specific geographical area (Geo). Yammer files are saved either in Yammer cloud storage, or for Microsoft 365 connected groups, some Yammer files are stored in SharePoint. Yammer files saved in SharePoint will be stored in SharePoint Online per your SharePoint Online data residency policy. Mobile push notifications require sending data to a third party notification service (Apple or Google), which might be outside your Geo.

Your Yammer Enterprise network is automatically created when you create your Office 365 tenant. For Office 365 Education subscribers, your network is associated with the US Geo. For all other Microsoft 365 or Office 365 subscribers, the country you enroll from determines the Geo your network is associated with. When you enroll from Europe or Africa your network is associated with the EU Geo and when you enroll from Australia, Asia, North America, or South America your network is associated with the US Geo. 

### Features not available for Yammer networks in the EU Geo

The following Yammer features are not available for Yammer networks in the EU Geo:

- All external collaboration features:

    - Only users in your Office 365 tenant can participate in your Yammer Enterprise network.

    - External guests can’t participate in your Yammer Enterprise network.

    - Your users can’t participate in other Yammer networks, including external networks. 

    - Your users can't be participants in [external messaging threads, or add external participants to threads](../work-with-external-users/external-messaging-faq.md) in your Yammer Enterprise network.

    - External groups can't be created in your Yammer Enterprise network, and your users can't participate in external groups belonging to other networks.

- [Posting to Yammer by sending an email message](https://support.office.com/article/058d1bc1-3492-47c5-bde2-29ea294acdb6) is only available for Microsoft 365 connected groups.


<a name="geodata"></a>

##  Determine which Geo your network is in

1. Log in to Yammer as a Verified Admin.

2. Click the **Settings** icon, click **Network Admin**, and then click **Success**. 

3. In the **New Network Checklist** section: 

    - If your network is in the EU, you'll see **Yammer network activated in the EU Geo**. 

    - If your network is in the US, you'll see **Yammer network activated in the US Geo**. 

##  Reprovision your Yammer Enterprise network to EU Geo
Customers with a minimum of 10,000 licensed users can have their Yammer Enterprise network reprovisioned to Yammer EU Geo. Please talk to your Microsoft account team representative for details.

## Related articles

[Where is your Microsoft 365 or Office 365 data located](/microsoft-365/enterprise/o365-data-locations)

[How do I tell where my Yammer files are being stored?](https://support.office.com/article/how-do-i-tell-where-my-yammer-files-are-being-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443)
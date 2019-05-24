---
title: "Data residency"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 5/22/2019
ms.audience: Admin
ms.topic: article
f1_keywords:
ms.service: yammer
localization_priority: High
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 
description: "Data residency for Yammer Enterprise."
---

# Data residency
Yammer offers local data residency to help meet data residency requirements. We commit to store message bodies and files attached to messages at rest within a specific geographical area (Geo). The country you enroll in Office 365 from will determine which Geo your Yammer Enterprise network is associated with. For a new Yammer Enterprise network, Microsoft will store Yammer message bodies and files in legacy Yammer Groups at rest in the Yammer Enterprise network Geo. 

Yammer files are saved either in Yammer cloud storage, or for Office 365 connected groups, some Yammer files are stored in SharePoint. Yammer files saved in SharePoint will be stored in SharePoint Online per your SharePoint Online data residency policy.

Mobile push notifications require sending data to a third party notification service (Apple or Google), which might be outside your Geo.

### Features not available for Yammer networks in the EU Geo

The following Yammer features are not available for Yammer networks in the EU Geo:

- All external collaboration features:

    - Only users in your Office 365 tenant can participate in your Yammer Enterprise network.

    - External guests can’t participate in your Yammer Enterprise network.

    - Your users can’t participate in other Yammer networks.

    - External groups can't be created in your Yammer Enterprise network, and your users can't participate in external groups belonging to other networks.

- [Post to Yammer by sending an email message](https://support.office.com/article/058d1bc1-3492-47c5-bde2-29ea294acdb6)


<a name="geodata"></a>

##  Determine which Geo your network is in

1. Log in to Yammer as a Verified Admin.

2. Click the **Settings** icon, click **Network Admin**, and then click **Success**. 

3. In the **New Network Checklist** section: 

    - If your network is in the EU, you'll see **Yammer network activated in the EU Geo**. 

    - If your network is in the US, you'll see **Yammer network activated in the US Geo**. 

## See also

[Where is your Office 365 data located](https://go.microsoft.com/fwlink/?linkid=2083810)

[How do I tell where my Yammer files are being stored?](https://support.office.com/article/how-do-i-tell-where-my-yammer-files-are-being-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443) 

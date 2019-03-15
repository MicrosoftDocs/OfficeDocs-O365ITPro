---
title: "Data residency in the European Union Geo (Preview)"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 3/15/2019
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
description: "Data ."
---

# Data residency in the European Union Geo (Preview)
Yammer Data Residency in the European Union (EU) offers local data residency to help organizations in the EU meet their data residency requirement. It is a commitment to store certain types of customer data at rest within the EU geographical area (Geo). Customer data stored at rest in the EU may be stored in any of the data center locations assigned to the EU Geo and is not bound to one specific EU country.

> [!NOTE]

> Yammer data residency in the EU Geo is in Preview. Once Preview is finished:
> - The country you enroll in Office 365 from will determine which Geo your network is associated with. 
> - For a new Yammer Enterprise network, Microsoft will store Yammer message bodies and files in legacy Yammer Groups at rest only in the Yammer Enterprise network Geo.
> - Files in Office 365 Connected Groups will be stored in SharePoint Online per your SharePoint Online data residency policy. 

## Features not available for tenants in the EU Geo

The following Yammer features are not available for tenants in the EU Geo:

- [External messaging](../work-with-external-users/external-messaging-faq.md), including external groups and networks

- [Posting to Yammer groups by sending email](https://support.office.com/article/058d1bc1-3492-47c5-bde2-29ea294acdb6)

## Data that isn't stored in the EU Geo

For the following types of data, Microsoft can't control storage:

- Push notifications are sent from Yammer to Android and iOS mobile devices. Storage for notifications sent to devices is controlled by Google and Apple. Yammer admins can't disable push notifications.  

- Data transmitted to Tenor when users search for GIFs to add to Yammer messages. This feature can be disabled by a Yammer network admin. For steps to disable this feature, see [Configure your Yammer network](configure-yammer.md#TenorGIFs).

- Link metadata for links posted in Yammer messages, including the title, summary, and preview image for the link. Existing URLs that are cached remain until the cache expires. For steps to disable this feature, see [Configure your Yammer network](configure-yammer.md#LinkMetadata). 

## FAQ

**Q: Are additional Geos planned?**

A: Microsoft will continue to invest in additional Geos to meet the requirements and needs of our customers, but we do not have the timing or a list of additional Geos at this time. Please reach out to your Microsoft account team to share your requirements. 

**Q: Does Yammer offer Multi-Geo data residency?**

A: No. Yammer does not offer Multi-Geo data residency.

**Q: How is my data handled during Preview?** 

A: All Office 365 Data Protection terms are adhered to during Preview. 

<a name="geodata"></a>
**Q: How do I know if my Yammer network stores data in the EU?**

A: Log in to Yammer as a Verified Admin, click the **Settings** icon, click **Network Admin**, and then click **Success**. In the **New Network Checklist** section: 

- If your network is in the EU, you'll see **Yammer network activated in the EU Geo**. 

- if your network is in the US, you'll see **Yammer network activated in the US Geo**. 

## See also

[Where is your Office 365 data located](https://go.microsoft.com/fwlink/?linkid=2083810)
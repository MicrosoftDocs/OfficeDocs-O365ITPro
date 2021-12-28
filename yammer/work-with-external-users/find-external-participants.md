---
title: "Find external messaging participants in a Yammer network"
f1.keywords:
- NOCSH
ms.author: pamgreen
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 9e8cd010-829a-4d11-8a57-a8f735407604
description: "Yammer admins can use data export to find external participants in a network."
---

# Find external messaging participants in a Yammer network

When you communicate with outside partners, suppliers, or customers, you want to make sure only authorized personnel have access to the information on your Yammer network. Verified admins can use data export to find the names of [external participants](add-external-participants.md) to see which conversations and files in their network are visible to external participants.

>[!NOTE] 
>Yammer Enterprise networks in the [EU Geo](../manage-security-and-compliance/data-residency.md) do not have external participants.
  
1. In the Yammer admin center, go to **Content and Security** \> **Export data**.

    You'll only see this option if you are a verified admin in the Yammer network.

    For more information, see [Export Yammer Enterprise data](../manage-security-and-compliance/export-yammer-enterprise-data.md).

2. To identify **threads in your network that users from other networks participate in**, locate the export folder on your computer, and open the **MessageThreads.Outbound.csv** export file.

    >[!NOTE]
    >The data export reflects the current view of the network. For example, if a user was added, but then removed before the report was created, that user won't appear in the report.
  
    ![Screenshot of an example data export file.](../media/90261f3d-0629-4fb6-bb42-33ed7eb3e99a.png)
  
    Column **D** (external_participants) lists the users in other networks that participate in threads in your network, along with their name, email address, and the network ID of the Yammer network they belong to.

If you want to remove an external participant, you can use the information from the list to go to the conversation they're included in and remove them from the conversation. See [Remove an external participant from a conversation](add-external-participants.md#RemoveExternal).
  
## Related articles

[Add external participants to your Yammer conversations](add-external-participants.md)
  
[External Yammer participants FAQ](external-messaging-faq.md)
  
[Disable external messaging in a Yammer network](disable-external-messaging.md)

---
title: "Find external messaging participants in a Yammer network"
ms.author: v-irpast
author: v-irpast
manager: scotv
ms.date: 3/23/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: 9e8cd010-829a-4d11-8a57-a8f735407604
description: "Yammer admins can use the data export tool to find external participants in a network and find conversations that users are participating in on other networks."
---

# Find external messaging participants in a Yammer network

Your users need the flexibility to [add external participants](add-external-messaging-participants-to-your-yammer-conversations.md) to conversations in your Yammer network. As an admin, you need to know who those participants are and what they're saying in case you need to make a change. Verified Admins can see which conversations and files in their network are visible to external participants and can identify conversations in which their employees are participating on other Yammer networks. This article helps you find the external participants in your Yammer network so you can stay in control. 
  
If you are a verified admin, you can use the data export tool to find external participants in your network and find conversations that your users are participating in on other networks.
  
1. In the Yammer admin center, go to **Content and Security** > **Export data**.
    
    You'll only see this option if you are a Verified Admin in the Yammer network.
    
    For more information, see [Export Yammer Enterprise data](../security-and-compliance-topics/export-data-from-yammer-enterprise.md).
    
2. To identify **threads in other networks that users from your networks participate in**, locate the export folder on your computer, and open the **MessageThreads.Inbound.csv** export file. 
    
    ![Screenshot of an example data export file](/Office365/Admin/media/6b96f531-7a77-4079-aacf-288e313ae023.png)
  
    Column **B** (networks_participants) lists the users in your network that participate in external threads, along with their name, email address, and the network ID of the Yammer network that they belong to. The data export reflects the current view of the network. If a user was added but removed before the report was created, that user won't appear in the report. 
    
3. To identify **threads in your network that users from other networks participate in**, locate the export folder on your computer, and open the **MessageThreads.Outbound.csv** export file. 
  
![Screenshot of an example data export file](/Office365/Admin/media/90261f3d-0629-4fb6-bb42-33ed7eb3e99a.png)
  
Column **D** (external_participants) lists the users in other networks that participate in threads in your network, along with their name, email address, and the network ID of the Yammer network that they belong to. The data export reflects the current view of the network. If a user was added but removed before the report was created, that user won't appear in the report. 
    
If you want to remove an external participant, you can use the information from the list to go to the conversation that they're included in and remove them from the conversation. See [Remove an external participant from a conversation](add-external-messaging-participants-to-your-yammer-conversations.md#RemoveExternal).
  
## Related Topics

[Add external participants to your Yammer conversations](add-external-messaging-participants-to-your-yammer-conversations.md)
  
[External Yammer participants FAQ](external-messaging-faq-yammer.md)
  
[Control external participants in a Yammer network with Exchange Transport Rules](control-external-messaging-in-a-yammer-network-with-exchange-transport-rules.md)
  
[Yammer - Admin Help](https://support.office.com/article/e1464355-1f97-49ac-b2aa-dd320b179dbe)
  


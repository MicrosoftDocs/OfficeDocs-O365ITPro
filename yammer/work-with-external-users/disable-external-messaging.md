---
title: "Disable external messaging in a Yammer network"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 5/13/19
ms.audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: f8fd6403-c8f3-4307-9230-65304d6000d9
description: "Disable external messaging, with options for preventing external users in groups and conversations, and preventing users from joining a Yammer network in another organization."
---

# Disable external messaging in a Yammer network

By default for Yammer Enterprise networks in the US Geo, users can add external participants to their Yammer conversations and Yammer groups, and members of your Yammer network can participate in another company's Yammer network if invited. If needed, you can turn off this external messaging.

> [!NOTE]
> As of May 2019, we are in process of rolling out a change to how you can disable external messaging. This change gives you a new option for restricting access to other organizations' Yammer networks, and no longer requires use of an Exchange Transport rule or contacting support for restricting external access to your Yammer network's groups and conversations. 

## Determine whether the new method is available 

1. In the Yammer admin center, go to **Content and Security** \> **Security Settings**.
    
2. In the **External Messaging** section: 

   - If you see one check box, **Enforce your Exchange Online Exchange Transport Rules (ETRs) in Yammer**, you are still using the previous method. For steps, see [Disable external messaging by using an Exchange Transport Rule](./control-external-messaging-with-exchange).

   - If you see the following three options, you are using the new method, and can use the steps in this article:

     -  **Allow users in this network to participate in groups or conversations in other networks, and allow external users to participate in groups or conversations in this network.**    
   
     - **Allow users in this network to participate in groups or conversations in other networks, but don't allow external users to participate in groups or conversations in this network.**     
   
     - **Don't allow users in this network to participate in groups or conversations in other networks, and don't allow external users to participate in groups or conversations in this network.**

 ## What each option does

| Option | Users can participate in other networks <sup>1</sup> | External participants can participate in groups and conversations <sup>2</sup> |
|--------|-------------------------------|----------------|
|**Allow users in this network to participate in groups or conversations in other networks, and allow external users to participate in groups or conversations in this network.**| Yes | Yes|
|**Allow users in this network to participate in groups or conversations in other networks, but don't allow external users to participate in groups or conversations in this network.** | Yes | No|
|**Don't allow users in this network to participate in groups or conversations in other networks, and don't allow external users to participate in groups or conversations in this network.**| No | No|

1. When you prevent users from being able to participate in other networks:

    - Users are blocked from receiving invitations from Yammer networks on other domains.

2. When you disable external access to your groups and conversations:

    - When a user tries to add an external participant in Yammer, the user receives an error message stating that they are unable to add external participants because it violates their company's policy. The user will not be allowed to post the message. 

    - Any current external participants are blocked from using external conversations or threads that they may have been participating in.

    - No new external groups can be created. 

 
## See also

[Add external participants to your Yammer conversations](add-external-participants.md)
  
[Find external participants in a Yammer network](find-external-participants.md)
  
[External Yammer participants FAQ](external-messaging-faq.md)

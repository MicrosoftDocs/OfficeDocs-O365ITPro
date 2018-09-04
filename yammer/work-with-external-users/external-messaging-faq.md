---
title: "External messaging FAQ - Yammer"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 9/4/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 35b59d6c-bb1c-4541-bf19-9f67d2f2b199
description: "Find answers to questions about adding external participants to your Yammer network, including general questions or questions about permissions and security and questions about opting out of external messaging."
---

# External messaging FAQ - Yammer

You can include people outside of your Yammer network in your conversations and private messages that are posted in external groups. You add people as external participants, and they can reply to messages and posts in your Yammer network without having to join. 
  
Find answers to frequently asked questions about external participants in this article. Or see [Add external participants to your Yammer conversations](add-external-participants.md), [Create and manage external groups in Yammer](create-and-manage-external-groups.md), [Find external participants in a Yammer network](find-external-participants.md), and [Disable external messaging in a Yammer network](control-external-messaging-with-exchange.md) for more information about working with external participants. 
  
    
## General questions
<a name="General"> </a>

### Q: What's the difference between external participants and external networks?

A: External networks are great for hosting external communities and managing long-term projects. The external participants feature is meant for one-off, short-term communications, which don't warrant the need of provisioning a new network.
  
### Q: Can I invite external participants to my Yammer groups?

A: You can [create external groups in Yammer](create-and-manage-external-groups.md) and invite external participants to those groups. 
  
### Q: What happens when I remove an external participant?

A: When you remove someone from a Yammer conversation, it removes the entire conversation from their Yammer inbox, and they can no longer access it.
  
The user that added the external participant can remove them from the conversation. In addition, both network and group admins can remove users from conversations.
  
### Q: What happens if I accidentally add an external participant to the conversation?

A: Don't worry. Simply click **Remove Participant** on the system-generated comment announcing that participant has been added to the thread. For more information, see [Add external participants to your Yammer conversations](add-external-participants.md).
  
### Q: What happens if I select "Stop following in inbox" for an external message?

A: The message is completely removed from your inbox.
  
### Q: Will Yammer users who unsubscribe from email notifications receive an invitation when they have been added to a conversation?

A: No.
  
### Q: What if I add an external participant who is not a Yammer user?

A: If you add someone and they are not a Yammer user, they will receive a copy of the message in their email inbox. They will also receive an invitation to join their Yammer network.
  
### Q: Can I add a user with a personal email address (like Hotmail or Gmail) to a Yammer conversation with External Messaging?

A: No. You must invite people using their company or work email address.
  
### Q: Will pending Yammer users who have been added to a conversation receive an email to join Yammer?

A: Yes.
  
### Q: Can I see external participants in my type-ahead search box when I create or reply to a message?

A: After an external participant has been added to a conversation, their name appears in the type-ahead search. Their name appears higher or lower on the suggested list depending on how frequently you communicate with that person on Yammer. Because of permission restrictions (which depend on the privacy settings of a group and whether the participant is internal or external), the type-ahead search experience varies. The following table explains the permissions and experience for type-ahead search with external participants:
  
|**Situation**|**Experience for internal members**|**Experience for external participants**|
|:-----|:-----|:-----|
|An external participant is added to a conversation in a public group.  <br/> |Type-ahead search includes the external participant for all members of the network.  <br/> |Type-ahead search is limited to participating members in the conversation.  <br/> |
|An external participant is added to a conversation in a private group.  <br/> |Type-ahead search includes the external participant for all members belonging to that group.  <br/> |Type-ahead search is limited to participating members in the conversation.  <br/> |
|An external participant is added to a private message.  <br/> |Type-ahead search is limited to participants in the private message.  <br/> |Type-ahead search is limited to participants in the private message.  <br/> |
|A public group is made private.  <br/> |Type-ahead search includes the external participant for all members of the network.  <br/> |Type-ahead search is limited to members that have participated in the conversation the external participant has been invited to join.  <br/> |
|A private group is made public.  <br/> |Type-ahead search includes the external participant for all members of the network.  <br/> |Type-ahead search is limited to members that have participated in the conversation the external participant has been invited to join.  <br/> |
   
## Permissions and security questions
<a name="Security"> </a>

### Q: How can I protect against risk and maintain our privacy?

A: Privacy and security is really important to us, too. We've spent a long time building tools to monitor and proactively protect your company's IP and employees. As part of External Messaging, we've built a number of security features:
  
- **Clear UI warnings:** We've built warnings to ensure users are consciously aware before they add an external participant. When you add an external user to a conversation or reply to a conversation with an external participant, you'll see a clear warning in the UI. See [Add an external participant](add-external-participants.md#AddExternal).
    
- **Exchange Online mail flow rules:** We've created an opt-out option for [verified admins](../manage-yammer-users/manage-yammer-admins.md) to turn off external messaging and external groups by enforcing Exchange Online mail flow rules (also known as Exchange Transport Rules) in Yammer, providing a consistent experience across modes of communication. If your organization is concerned about external sharing, you likely already have mail flow rules defined in Exchange Online. See [Disable messaging in a Yammer network](control-external-messaging-with-exchange.md).
    
- **Remove users:** You can remove external participants from a conversation. Once removed, a user can't view that conversation anymore. Both network and group admins can remove users from conversations. See [Remove an external participant from a conversation](add-external-participants.md#RemoveExternal).
    
- **Data export:** Yammer verified admins can keep track of all conversations and files that include external participants and monitor conversations their users are having outside of your network. See [Find external participants in a Yammer network](find-external-participants.md).
    
- **Keyword monitoring:** Yammer verified admins can set up keyword monitoring to alert admins of potential breaches. See [Monitor Keywords](../manage-security-and-compliance/manage-data-compliance.md#MonitorKeywords)
    
### Q: When I add an external participant to a conversation, what can they see?

External participants can only see conversations that they have been explicitly invited to. They can see anything included on that conversation—for example, a file that has been uploaded. But they can never find or join another conversation on your network without an explicit invitation.
  
### Q: Can external participants upload files to the conversation?

A: Yes.
  
### Q: Can external participants invite other participants as well?

Yes, external participants can add others to the conversation, just as they can @-mention people in that conversation. They can only invite people to conversations they have already been explicitly included on.
  
### Q: What information can external participants see about me?

A: External participants can only see a limited view of your hover card. Fields listed on the hover card include your name, title, email address, and network. Your profile picture, phone number, and more remain hidden to external participants.
  
### Q: What permissions do external participants have for content that is uploaded to a conversation?

A: External participants can view and download files. External participants can only view notes.
  
### Q: Can an external participant share this conversation?

A: No. Because permissions restrict the audience to privileged members, external participants must be added individually to the conversation.
  
### Q: Where does the data for external participants live?

A: The conversation data is available to [verified admins](../manage-yammer-users/manage-yammer-admins.md) (by using data export) of any participant on the conversation. So if your employee is participating in a conversation on another network, because that conversation shows up in their inbox, it is available in your network's data export. For more information, see [Find external participants in a Yammer network](find-external-participants.md).
  
### Q: When I add an external participant to a conversation do they enter my network?

A: No. External participants can only participate in conversations they have been explicitly invited to. They access these conversations via their Yammer inbox (on their network). They have no access to the rest of your network.
  
### Q: What rights do verified admins have?

A: [Verified admins](../manage-yammer-users/manage-yammer-admins.md) can remove all external participants from any conversation any time. They can also see which files and conversations are accessible to external users by using data export. For more information, see [Find external participants in a Yammer network.](find-external-participants.md)
  
### Q: If I have keyword monitoring in place, will it apply to messages external participants post in my network?

Yes. Keyword monitoring applies to any posts in your network, including those from external participants.
  
## Opt-out questions
<a name="OptOut"> </a>

> [!NOTE]
> Only Yammer Enterprise networks can opt out of external messaging. 
  
### Q: I don't want external messaging and external groups enabled for my network. What options do I have to disable all of external messaging?

As an admin, you can choose to disable external messaging and external groups in your Yammer network. This blocks users from creating external groups in their home network, but still allows users to be invited to groups hosted on other networks. 

To do this, you create an Exchange Online mail flow rule, and configure Yammer to enforce your rule. For instructions, see [Disable external messaging in a Yammer network](control-external-messaging-with-exchange.md). 

If this security functionality is not sufficient, you can also choose to use a logical firewall to prevent users from creating or joining external groups in Yammer networks, such as partner or customer organizations, hosted in that other Yammer network. However, we highly discourage restricting messaging in this manner because it will cause users to seem difficult to reach and collaborate with, with the Yammer equivalent of having an email bounce, and it will limit engagement within Yammer. 
    
### Q: What is the user experience if I disable external messaging?

If you decide to opt out of external messaging by using an Exchange Online mail flow rule, messages that begin on your network will not be able to be shared with external participants. Users on your network will still be able to receive messages from other networks; these messages will be available to the user in their Yammer inbox. They will be able to read and respond to these messages as normal. In addition, the full thread they are participating in (including all messages on the thread) will be available in your data export. This enables you to keep track of conversations your employees are having on other networks.
  
If you decide to use a firewall to prevent external messages to your users, this means they are unable to send or receive messages from other networks. If someone tries to send a message to your users, that person will receive an error message and be prevented from sending the message.
  
### Q: Can I use external groups, but not external messaging?

No, if you opt out for external messaging, you can't opt in for external groups. You opt out or in for both external messaging and external groups at the same time.
  
You use the same method to opt out of external participants and external groups. 
  
### Q: If I decide to use a firewall to prevent external messages to my users, what functionality will my network not receive?

As we continue innovating Yammer, additional new capabilities are likely to be built as part of the External Messaging framework. Blocking external sharing and even more so, using a firewall to prevent external messages to your users, will leave some other future Yammer capabilities unavailable to customers. As we continue to work on Yammer, we will be sure to announce which features build on the External Messaging framework so companies know which features they will receive.
  
> [!TIP]
> To see what's coming for Yammer, see the [Office 365 Roadmap](https://go.microsoft.com/fwlink/?LinkId=524076). 
  
## See also

[Add external participants to your Yammer conversations](add-external-participants.md)
  
[Create and manage external groups in Yammer](create-and-manage-external-groups.md)
  
[Find external participants in a Yammer network](find-external-participants.md)
  
[Disable external messaging in a Yammer network](control-external-messaging-with-exchange.md)
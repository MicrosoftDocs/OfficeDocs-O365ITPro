---
title: "Control external messaging in a Yammer network with Exchange Transport Rules"
ms.author: v-irpast
author: v-irpast
manager: scotv
ms.date: 3/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: f8fd6403-c8f3-4307-9230-65304d6000d9
description: "Use Exchange Transport Rules to identify, monitor, and protect your IP in Yammer when external participants are in your network."
---

# Control external messaging in a Yammer network with Exchange Transport Rules

In Yammer, users can add external participants to their Yammer conversations with external messaging. Organizations can identify, monitor, and protect their IP in Yammer, similarly to how they can protect it in Exchange. Yammer external messaging applies [Exchange Transport Rules](https://go.microsoft.com/fwlink/?LinkID=404243) (ETRs), a set of proactive controls to prevent company information from being shared. These are configured in Exchange Online to protect content in their Yammer networks. 
  
When you have set ETRs to apply in Yammer, if a user tries to add an external participant, and it violates your companies ETRs, the user receives an error message stating that they are unable to add external participants because it violates their company's policy. The user will not be allowed to post the message. The following diagram shows this experience.
  
![When a Yammer user adds an external participant to a message, if Exchange Transport Rules are set, Yammer checks the rules before sending the message. If the message complies with the rules, the message is sent. If not, the user cannot send the message.](../../../../media/e0cad306-d83c-4bd9-922c-6b74b685a805.png)
  
Because Yammer does not read through the rules at this time, turning on ETRs for Yammer can result in disabling external messaging for your network if there are any rules enabled that are not on the Yammer ETR list. When support for more rules is added and this behavior changes, this article will be updated with additional information. See [Q: Do all ETRs work with Yammer?](control-external-messaging-in-a-yammer-network-with-exchange-transport-rules.md#ETRswork) in the FAQ. We recommend this as a method for opting out of the ability to include external participants in your network. For more information about how to opt out, see [Opt-out questions](external-messaging-faq-yammer.md#OptOut) in the [External participants FAQ](external-messaging-faq-yammer.md).
  
You define the ETRs in Exchange Online (see [Transport rules](https://go.microsoft.com/fwlink/?LinkId=613303) for more information). After you set ETRs to apply in Yammer, any ETRs will apply to both Exchange Online emails and Yammer communications. 
  
## Set ETRs to apply in Yammer

You can set ETRs to apply to any Yammer Enterprise network, including external networks. If you apply it to an external network, the external network uses the ETRs from the parent network.
  
1. Log on to Yammer as a [verified admin](../user-topics/manage-yammer-admins.md), and in the Yammer admin center, go to **Content and Security** > **Security Settings**.
    
2. Under **External Messaging**, select **Enforce your Exchange Online Exchange Transport Rules (ETRs) in Yammer**.
    
3. Choose **Save**.
    
## FAQ for Exchange Transport Rules and Yammer

### Q: If I have on-premises ETRs, will those work?

A: No. We can only integrate with ETRs established in Exchange Online. However, if you have on-premises ETRs and would like those to apply to Yammer, simply create an Office 365 tenant with Exchange Online and Yammer, and provision your ETRs in Exchange Online.
  
### Q: Do all ETRs work with Yammer?
<a name="ETRswork"> </a>

A: Not all ETRs from Exchange Online apply to Yammer. Yammer ignores the following conditions and actions (they are mostly about identifying spam messages):
  
- **Conditions**
    
  - MessageSizeOver
    
  - ContentCharacterSetContainsWord
    
  - MessageTypeMatches
    
  - SCLOver
    
  - WithImportance
    
- **Actions**
    
  - SetScl
    
  - PrependSubject
    
  - RemoveOME
    
For any other ETR rule you have in place that is not on this list, for now we will err on the side of caution and disable External Messaging for your network. Over time, Yammer's interpretation of ETRs will evolve and more closely map to the rule's intention, instead of erring on the side of blocking too many external messages.
  
### Q: Is this available to Yammer Basic networks?
<a name="ETRswork"> </a>

A: No. In order to apply ETRs, the Yammer network must be associated with an Office 365 tenant which includes Exchange Online, so that we know which ETRs to look at. Linking a Yammer network to Office 365 requires Yammer Enterprise.
  
## See Also

[Add external participants to your Yammer conversations](add-external-messaging-participants-to-your-yammer-conversations.md)
  
[Find external participants in a Yammer network](find-external-messaging-participants-in-a-yammer-network.md)
  
[External Yammer participants FAQ](external-messaging-faq-yammer.md)
  
[Yammer - Admin Help](https://support.office.com/article/e1464355-1f97-49ac-b2aa-dd320b179dbe)
  


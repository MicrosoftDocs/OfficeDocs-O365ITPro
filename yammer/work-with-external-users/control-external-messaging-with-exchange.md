---
title: "Disable external messaging in a Yammer network"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 9/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: f8fd6403-c8f3-4307-9230-65304d6000d9
description: "Disable external messaging in a Yammer network by using an Exchange Online mail flow rule."
---

# Disable external messaging in a Yammer network

By default in Yammer, users can add external participants to their Yammer conversations with external messaging. Organizations can disable external messaging and use of external groups by creating a mail flow rule in Exchange online and configuring Yammer to use it.  

When you have set up a mail flow rule and configured Yammer to use it, when a user tries to add an external participant in  Yammer, the user receives an error message stating that they are unable to add external participants because it violates their company's policy. The user will not be allowed to post the message. 

You can set this up for your home Yammer network, or for external Yammer networks.
  
 
## Step 1: Define the mail flow rule in Exchange Online

> [!IMPORTANT] 
> Yammer only checks to see if any mail flow rules are defined: it does not check the content of the rules. However, Exchange Online does check the content of the rules, so you need to create a rule that won't impact mail flow.  

For steps to create a rule using the [Exchange admin center](https://docs.microsoft.com/en-us/exchange/exchange-admin-center), (see [Manage mail flow rules](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).  

Here is an example of a simple rule you can create to disable external messaging in Yammer that won't impact email flow:
1. In **Name**, enter a name such as "Disable Yammer external messaging and external groups"
2. **In Apply this rule if**, specify **notanemail@notadomain.com**. Note that the exact value doesn't matter: it just must be in valid email format. 
3.  In Do the following, select **Reject the message with the explanation** and add an explanation such as "This disables external groups and messaging in Yammer".
4. In Choose a mode for this rule, select **Enforce**.
5. Click **Save**.

See [Q: Do all mail flow rules work with Yammer?](control-external-messaging-with-exchange.md#ETRswork).
  
## Step 2: Configure Yammer to use Exchange Online mail flow rules

1. Log in to Yammer as a [verified admin](../manage-yammer-users/manage-yammer-admins.md), and in the Yammer admin center, go to **Content and Security** \> **Security Settings**.
    
2. Under **External Messaging**, select **Enforce your Exchange Online Exchange Transport Rules (ETRs) in Yammer**. (Mail flow rules are also known as Exchange Transport Rules.)
    
3. Choose **Save**.
    
## FAQ for mail flow rules and Yammer

### Q: If I have on-premises Exchange Transport rules, will those work?

A: No. Yammer only checks for mail flow rules established in Exchange Online. 
 
<a name="ETRswork"> </a> 
### Q: Do all Exchange Online mail flow rules work with Yammer?

A:Not all mail flow rules from Exchange Online apply to Yammer. We suggest using the sample rule defined above. 

Yammer ignores the following conditions and actions (they are mostly about identifying spam messages):
  
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
    
For any other mail flow rule you have in place that is not on this list, if you have configured Yammer to enforce your Exchange Online mail flow rules, Yammer will block external messaging and external groups. 
  
### Q: Is this available to Yammer Basic networks?

A: No. In order to apply mail flow rules, the Yammer network must be associated with an Office 365 tenant which includes Exchange Online, so that we know which mail flow rules to look at. Linking a Yammer network to Office 365 requires Yammer Enterprise.
  
## See also

[Add external participants to your Yammer conversations](add-external-participants.md)
  
[Find external participants in a Yammer network](find-external-participants.md)
  
[External Yammer participants FAQ](external-messaging-faq.md)
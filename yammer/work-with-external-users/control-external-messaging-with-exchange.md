---
title: "Disable external messaging in a Yammer network"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 1/11/19
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
description: "Disable external messaging in a Yammer network by using an Exchange Online mail flow rule."
---

# Disable external messaging in a Yammer network

By default in Yammer, users can add external participants to their Yammer conversations with external messaging. Organizations can disable external messaging and use of external groups by creating a mail flow rule in Exchange online and configuring Yammer to use it.  

When you have set up a mail flow rule and configured Yammer to use it, external messaging is disabled. This means:

- When a user tries to add an external participant in Yammer, the user receives an error message stating that they are unable to add external participants because it violates their company's policy. 
The user will not be allowed to post the message. 

- Any current external participants are blocked from using external conversations or threads that they may have been participating in.

- No new external groups can be created.

You can set this up for your home Yammer network, or for external Yammer networks.
  
 
## Step 1: Define the mail flow rule in Exchange Online

> [!IMPORTANT] 
> Yammer only checks to see if a rule based on the specified criteria and actionis defined: it does not check the name of the rule. However, Exchange Online does check the content of the rules, so you need to create a rule that won't impact other (non Yammer) mail flow.  

For steps to create a rule using the [Exchange admin center](https://docs.microsoft.com/en-us/exchange/exchange-admin-center), (see [Manage mail flow rules](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).  

Here is a simple rule you can create to disable external messaging in Yammer that won't  impact other (non Yammer) email flow:
1. Click on **+**, and select **Create new rule...**
2. Click on the **More options...** link at the bottom of the dialog
3. In **Name**, enter a name such as "Disable Yammer external messaging and external groups"
4. **In Apply this rule if**, select "This sender..." + "is this person", and then specify **Yammer@yammer.com;notifications@yammer.com** in the "Check names" field. Confirm the entry with a click on the "Check name" button and close the dialog with a click on "OK".
5. **add condition**, select "This recipient..." + "is external/internal", and then select the recipient location as "Outside the organization"
6.  In "Do the following", select **Redirect the message to...** + **hosted quarantine**
7. In "Choose a mode for this rule", ensure the option **Enforce** is selected.
8. Click **Save**.


See [Q: Do all mail flow rules work with Yammer?](control-external-messaging-with-exchange.md#ETRswork).
  
## Step 2: Configure Yammer to use Exchange Online mail flow rules

1. Log in to Yammer as a [verified admin](../manage-yammer-users/manage-yammer-admins.md), and in the Yammer admin center, go to **Content and Security** \> **Security Settings**.
    
2. Under **External Messaging**, select **Enforce your Exchange Online Exchange Transport Rules (ETRs) in Yammer**. (Mail flow rules are also known as Exchange Transport Rules.)
    
3. Choose **Save**.

> [!IMPORTANT] 
> The change may take up to 30 minutes. During this period users will still be able to create external groups. With the checkbox selected Yammer will show this message "(Last synced at: )". This message can be ignored, as it is not updated even after the change was successful.

## FAQ for mail flow rules and Yammer

### Q: If I have on-premises Exchange Transport rules, will those work?

A: No. Yammer only checks for mail flow rules established in Exchange Online. 
 
<a name="ETRswork"> </a> 
### Q: Do all Exchange Online mail flow rules work with Yammer?

A: Not all mail flow rules from Exchange Online apply to Yammer. We suggest using the sample rule defined above. 

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

---
title: "Create organization-wide signatures and disclaimers"
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: "Learn to add email signature, legal disclaimer, or disclosure statement to all the email messages that enter or leave your organization."
---

# Create organization-wide signatures and disclaimers

 You can add an email signature, legal disclaimer, or disclosure statement to the email messages that enter or leave your organization. You can set it up to apply to all incoming and outgoing messages as shown below. Or you can apply it to certain messages like those containing specific words or text patterns.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/4b6fc71a-ed01-434f-ac08-92c4a0b2b982?autoplay=false]
  
## Create a signature that applies to all messages

> [!TIP]
> Organization-wide signatures are called "disclaimers," regardless of what they include. For example, they can just be a signature, or also include your address, legal disclaimer, or other information you want.
    
::: moniker range="o365-worldwide"

Go to the [Microsoft 365 admin center](https://admin.microsoft.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

1. Click the app launcher ![The app launcher icon in Office 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png), and then click **Admin**.
   
    Can't find the app you're looking for? From the app launcher, select **All apps** to see an alphabetical list of the Office 365 apps available to you. From there, you can search for a specific app. 
    
2. Choose **Admin centers**, and then click **Exchange**.
    
3. Under Mail flow, choose **Rules**.
    
4. Click the **+** (Add) icon and choose **Apply disclaimers**.
    
5. Give the rule a name.
    
6. Under Apply this rule, choose **[Apply to all messages]**.
    
    > [!TIP]
    > [Learn more](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) about applying conditions if you don't want the disclaimer applied to all messages. (This scoping article is for Exchange Server, but it also applies to Office 365.) 
  
7. Under Do the following, leave **Append the disclaimer** selected. 
    
8.  Click **Enter text** and type your disclaimer. 
    
    > [!TIP]
    > [Learn more](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) about formatting disclaimers. (This formatting article is for Exchange Server, but it also applies to Office 365.) 

9. Click **Select one** and choose **Wrap** as a fallback option. Then **OK**. This means that if the disclaimer can't be added because of encryption or another mail setting, it will be wrapped in a message envelope.
    
10. Leave **Audit this rule with severity level** selected. Then choose **Low**, **Medium**, or **High** to be used in the message log. 
    
11. Choose **Enforce** to turn on the disclaimer immediately, unless you want to test it first. 
    
12. Choose **More options** to include additional conditions or exceptions. 
    
13. Choose **Save** when finished. 
    
## Limitations of Office 365 organization wide signatures

You can't do the following with Office 365 signatures:
  
- Insert the signature directly under the latest email reply or forward
    
- Display server-side email signatures in users' Sent Items folders
    
- Embed images in email signatures
    
- Skip lines which contain variables that couldn't be updated (e.g. because the value wasn't provided for a user)
    
To gain these and other capabilities, use a third-party tool. Please do an internet search for **email signature software**. A number of these providers are Microsoft Gold Partners and their software provides these capabilities. 
  
## More resources

- See [Organization-wide message disclaimers, signatures, footers, or headers in Office 365](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) for information about using PowerShell. 
    


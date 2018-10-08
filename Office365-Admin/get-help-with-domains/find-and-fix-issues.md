---
title: "Find and fix issues after adding your domain or DNS records in Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 3/28/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: "Learn to track down any problems you run into while setting up a custom domain by making sure the DNS records are set up correctly."
---

# Find and fix issues after adding your domain or DNS records in Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
Getting your domain set up to work with Office 365 can be challenging. The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!
  
> [!TIP]
> We can help you fix this! [Still need help?](find-and-fix-issues.md#BKMK_GetHelp). 
  
## What's going on?

- [Can't verify your domain?](find-and-fix-issues.md#BKMK_verify)
    
- [Outlook isn't working?](find-and-fix-issues.md#BKMK_OutlookBroken)
    
- [Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?](find-and-fix-issues.md#BKMK_EmailSwitched)
    
- [Can't confirm non-profit or school account status?](find-and-fix-issues.md#BKMK_validateAcct)
    
- [Services not working with your domain?](find-and-fix-issues.md#BKMK_Test)
    
- [Accessing your website isn't working?](find-and-fix-issues.md#BKMK_Website)
    
## Can't verify your domain?
<a name="BKMK_verify"> </a>

There are a couple of common reasons that domain verification doesn't work as it should:
  
1. **The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too! 
    
2. **The record hasn't been saved.** At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet. Make sure you've saved your changes so Office 365 can see and verify the record. 
    
3. **The record hasn't updated across the Internet.** It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours. If you've waited longer than that, and you're sure the record value is correct, please [Still need help?](find-and-fix-issues.md#BKMK_GetHelp) so we can help sort out whatever's wrong. 
    
## Outlook isn't working?
<a name="BKMK_OutlookBroken"> </a>

If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## Everyone's email got switched to Office 365 and you only wanted YOUR email to switch?
<a name="BKMK_EmailSwitched"> </a>

When you add your domain to Office 365, typically your domain's MX record is updated (by you or Office 365) to point to Office 365, and ALL email sent to that domain will start coming to Office 365. Make sure you've created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record.
  
What if you don't want to move email for everyone on your domain to Office 365? You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## Can't confirm non-profit or school account status?
<a name="BKMK_validateAcct"> </a>

There are a couple of scenarios when you just need to verify your organization's domain and not set up any services. For example, to prove to Office 365 that your organization qualifies for a school subscription.
  
Check out the guidance in [Verify your Office 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) to make sure you've completed all the required steps. It's a little different for each situation. 
  
If you've followed all the steps and Office 365 isn't validating your status or letting you complete the process, you'll need to [Still need help?](find-and-fix-issues.md#BKMK_GetHelp) to see what's going on and resolve the issue. 
  
## Services not working with your domain?
<a name="BKMK_Test"> </a>

We can help you track down issues with your domain's DNS setup. The domains troubleshooter in Office 365 will show you any records that need fixing, and exactly what the records need to be set to. This video shows you how, or you can follow step-by-step help (below the video) to fix the records at your registrar.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/24a88baf-3b58-4f90-9196-012031b75204?autoplay=false]
  
> [!TIP]
> Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop? Check out the [different mail flow scenarios you can have with Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) to make sure you've got things set up correctly for your business. Or get more troubleshooting help with email here: [Fix Outlook problems](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## Accessing your website isn't working?
<a name="BKMK_Website"> </a>

If you've fixed any DNS issues and you're still having trouble, try one of the following.
  
- People can't get to your website at www.mydomain.com: [Track down website issues](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Office 365](../dns/add-or-edit-custom-dns-records.md)
    
## Still need help?
<a name="BKMK_GetHelp"> </a>

[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


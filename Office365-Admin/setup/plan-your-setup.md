---
title: "Plan your setup of Office 365 for business"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_1stInfoRqrd'
- 'O365P_1stDNSHoster'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: "Learn what all you will need to set up your Office 365 for business."
---

# Plan your setup of Office 365 for business

This article is for people who have subscribed to an Office 365 business plan.
  
There are a few things you need to decide, and info you need to have on hand, before moving your business to Office 365.
  
## Info to have on hand before you run the Office 365 setup wizard

When you're ready to run the Office 365 setup wizard and move your domain to Office 365, here's the info you'll need to have on hand:
  
1. List of people you want to add to Office 365. Even if you've already added them to Office 365, if you're updating your domain information, you need to enter their names here.
    
2. How you're going to notify your employees of their Office 365 user ID and password so they can sign in. Are you going to call them with the info? Or send it to their personal email address? They won't have access to their Office 365 email, so you can't use that.
    
3. If you have a domain name for your business (such as contoso.com) **and** you plan on using Office 365 email, you'll need to know where your domain is registered and have sign-on information. 
    
## What happens when you run the Office 365 setup wizard

Here are the steps you'll do when you run the setup wizard:
  
1. Add your domain, such as contoso.com.
    
    When you signed up for Office 365, you got a user ID that includes an "onmicrosoft.com" domain. In this step, you can add your own domain so your user ID and email are personalized for your business, like rob@contoso.com. Domain setup can be confusing, but we'll guide you through it step by step. [What's a domain?](domains-faq.md)
    
    ![Add your domain](../media/9a2caeb3-7e4a-4d6a-bc9c-fb8e86687e7c.png)
  
2. Verify your domain. In this step, the wizard gives you a code - called a TXT value - that you enter at your domain registrar. If your registrar is GoDaddy, the wizard prompts you to login in at GoDaddy so Office 365 can enter the code for you!
    
    ![Verify your domain](../media/88dbfa4d-aef1-4686-8891-69d382519e91.png)
  
3. Add your users. You can add users later, too; see [Add users individually or in bulk](../add-users/add-users.md).
    
    > [!NOTE]
    > If you need to [Assign admin roles in Office 365 for business](../add-users/assign-admin-roles.md) to the users you add in the wizard, you can do that later on the **Users** page. 
  
    ![Add users](../media/865a4703-15c5-46eb-8215-5c61748aaf08.png)
  
4. Migrate email and contacts from another email service that uses IMAP (such as Gmail). For more migration options, or if you just want to migrate your email later, see [Migrate email and contacts to Office 365](migrate-email-and-contacts-admin.md).
    
    ![Migrate email](../media/43083cd5-59d9-486d-a5c2-62ce1a88f407.png)
  
5. Setup online services, such as email and Skype for Business.
    
    ![Setup online services](../media/6cccda7d-37e6-43ae-8055-e6cf4bf72ad3.png)
  
6. Change your nameservers. (You don't have to do this step if your domain registrar is GoDaddy.) **IMPORTANT**: After you do this step, your user's email will be delivered to their Office 365 mailbox. It may take up to 72 hours for your domain provider to start rerouting email. 
    
    ![Change nameservers](../media/c825953a-e139-49c6-929f-d09ff1321259.png)
  
7. Congratulations! You're finished!
    
    ![Finished! Go to the Microsoft 365 admin center.](../media/54660b65-4ded-4fc8-b455-973e508440c4.png)
  
8. Now you can go to the Microsoft 365 admin center, where you can change the domain of your admin account. Plus you can manage your billing information, add or remove users, reset passwords, and do other business functions.
    
    > [!NOTE]
    > You can also update your account to the new domain on the **Active users** page. 
  
  
If you get stuck at any point, call us. [We're here to help!](../contact-support-for-business-products.md)
  
## When not to use the setup wizard: Active Directory synchronization and hybrid environments

There are a couple of scenarios that include either migrating data or users from on-premises environments, or setting up a hybrid system that includes directory synchronization. If you are in this category, follow the instructions in these articles.
  
- To set up directory synchronization with your on-premises Active Directory, see [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization), and to understand the different identity models in Office 365, read [Understanding Office 365 identity and Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).
    
- To set-up an Exchange hybrid, the full set of instructions that guide you through all the different ways of setting up a hybrid exchange (including setting up DNS records) can be found here: [Exchange Server Deployment Assistant](https://aka.ms/exdeploy)
    
- To set up a SharePoint hybrid, particularly hybrid search and site features, see [Hybrid Search in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).
    
## Do you want someone to help you set up Office 365?

- **If you have fewer than 50 employees:**
    
  - **Ask for help and we'll call you**. After you buy Office 365, you can access your Microsoft 365 admin center (you don't need to run setup to get to it). At the bottom of your admin center page, select **Need help?** Describe your problem, and we'll call you. 
    
      
  - **Call [Office 365 for Business Support](../contact-support-for-business-products.md) with your questions**. We're here to help! 
    
  - **Consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089)**. If you're short on time, or have advanced requirements (like moving thousands of files to Office 365 cloud storage or integrating with other software), an experienced partner can be a big help. 
    
- **If you have more than 50 employees**, the [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) is available to help you with your deployment. 
    
## Move to Office all at once or in stages

- **Do you want to move your business to Office 365 all at once?** If so, then plan to move your domain to Office 365 right away. Start by running the Office 365 setup wizard; it will prompt you to set up your domain. 
    
- **Or do you want to move to Office 365 gradually?** If you want to move to Office 365 in stages, then skip running the Office 365 setup wizard and consider adopting Office 365 features in the following order: 
    
1. [Add your employees to Office 365](../add-users/add-users.md) so they can download and install the Office apps. 
    
2. [Download and install the Office apps](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) to use Word, Excel, and PowerPoint on your computer and devices. 
    
3. [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb.aspx) to use for your meetings. 
    
4. [Move your content to Office 365 cloud storage](set-up-file-storage-and-sharing.md) (OneDrive or team sites). 
    
5. And, when you're ready, run the Office 365 setup wizard to [move your domain and email](add-domain.md).
    
## Check that your devices meet system requirements

Each person in your business can install the Office 2016 suite of apps (Word, Excel, PowerPoint, and so on) on up to 5 PCs and Macs. See the operating system and computer requirements for installing [Office 2016 suites](https://go.microsoft.com/fwlink/?LinkId=534827) for business. 
  
Mobile apps can be installed on iOS, Android, and Windows devices. You can find information on mobile device and browser support in [System requirements for Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## Plan for email

If you're planning to move from an existing email service to Office 365, it usually takes 2 days to make the switch.
  
 **Plan for email downtime**
  
If you're going to use Office 365 for your email:
  
- To move your business email address (such as *rob@contoso.com*) from another email service to Office 365, you need to direct your mail to be delivered to your new Office 365 mailbox. You do this using the Office 365 setup wizard, where we guide you through the updates you need to make at your domain host, step by step. 
    
- After you update your domain host, the changes typically take effect in just an hour or two. But be aware that it can sometimes take up to 72 hours for the changes update across the Internet.
    
- Because you might have email downtime, we recommend you plan to switch to Office 365 email during an evening or weekend when you receive fewer emails.
    
 **Plan to move your existing email, contacts, and calendar**
  
If you're going to use Office 365 for your email account, you can bring your existing email, contacts, and calendar with you. The Office 365 setup wizard helps you move your existing email and contacts for most scenarios. We also have step-by-step guides to move one or many mailboxes.
  
|**How many mailboxes?**|**Recommendation**|
|:-----|:-----|
|Just a few  <br/> |If you don't want to use the setup wizard to migrate the mailboxes, you can let mailbox owners migrate their own email and contacts. See [Migrate email and contacts to Office 365 for business](migrate-email-and-contacts-admin.md).  <br/> |
|Several  <br/> |If you are migrating from Gmail, see [Migrate G Suite mailboxes to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> If you are migrating from another email provider, including Exchange, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |
   
## Plan for file storage and migration

Office 365 provides cloud storage for individuals, small businesses, and enterprises. For guidance about what to store where, see [Where you can store documents in Office 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
 **You can move hundreds files** to [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) or to an Office 365 [team site](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242). You can upload 100 files at a time. Avoid uploading files larger than 2GB, which is the maximum file size by default.
  
 **If you want to move several thousand files** to Office 365 storage, review the [SharePoint Online Limits](https://go.microsoft.com/fwlink/p/?LinkID=856113). We recommend that you use a migration tool or consider hiring a [partner](https://go.microsoft.com/fwlink/?linkid=391089) to help you with the migration. For information about how to migrate a large number of files, see [SharePoint Online and OneDrive Migration User Guide](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## Plan for Skype for Business

If you have [Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium) or Business Essentials, you can use Skype for Business to make calls to other people in your business who are on your subscription. For example, if your business has 10 people, you can call and IM each other using Skype for Business without any special setup. 
  
For the following features, you need to take some additional steps:
  
### Make and receive calls from people external to your business

To make and receive phone calls from people external to your business, you have two options:
  
- **Option 1. Use the free [Skype app](https://www.skype.com/)**. If you have a very small business (for example, 1-2 people) using the Skype app is the better way to go. It's less expensive to use for domestic and international calls. You can still hold conference calls, make video calls, and share your desktop for presentations. [Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

    Note that the Skype app isn't part of the Office 365 suite, so it won't be integrated with Outlook 2016 the way Skype for Business is. This means your contacts in Outlook 2016 won't show up in Skype; you'll need to add your contacts to Skype.

    We recommend starting with the Skype app to see if it meets your needs. If it doesn't, then consider the next option, to upgrade your plan.

- **Option 2. Upgrade your plan, and buy Cloud PBX and the PSTN Calling plan**. 

1. [Switch to the E1 or E3 plan](../subscriptions-and-billing/switch-to-a-different-plan.md) : 

  - Buy the E1 plan if you don't want to receive voicemail.

  - Buy the E3 plan if you do want to receive voicemail. Here's how Cloud PBX voicemail works: When a user receives a voicemail, it will be delivered to their mailbox as an email with the voicemail message as an attachment. They can also listen to their messages over their Skype certified desktop phone, all Skype for Business applications.
    
2. Buy the Cloud PBX add-on.
    
3. Buy a [PSTN Calling plan](https://docs.microsoft.com/microsoftteams/what-are-calling-plans-in-office-365): you can only buy this after you buy the Cloud PBX add-on.

    This second option is ideal for businesses with several people who make and receive external phone calls.

There are other Skype for Business features you can add to your subscription, too. To learn more, see [Skype for Business add-on licensing](https://support.office.com/article/3ed752b1-5983-43f9-bcfd-760619ab40a7.aspx).
  
### Do you want to use Skype Meeting Broadcast?

Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees. To learn more about how it works, see [What is Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d.aspx)
  
To use Skype Meeting Broadcast, you need to [enable](https://docs.microsoft.com/SkypeForBusiness/set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast) it, [configure your network](https://docs.microsoft.com/SkypeForBusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast), and [schedule a practice meeting](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553.aspx) and have a user join it. 
  
### IM with Skype contacts or other external Skype for Business users

By default, everyone in the world who uses Skype for Business will be able to contact you, assuming they know your email address, your firewall is configured to allow it, and they have open communication policies.
  
If you want to allow your users to communicate with some businesses but not others, see [Allow users to contact external Skype for Business users](https://docs.microsoft.com/SkypeForBusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users).
  
Skype for Business and the free Skype app are two different services. You can give your users permissions to search for and IM with people who are using the free Skype app. To do this, see [Let users add external contacts from Skype](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/let-skype-for-business-users-add-skype-contacts).
  
### Choose who sees whether co-workers are online

The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting. You can choose the default settings for everyone in your business. For instructions, see [Configure presence in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/configure-presence-in-skype-for-business-online).
  
## Plan for integration with Active Directory or other software

 **Do you want to integrate with your on-premises Active Directory?** You can integrate your on-premises Active Directory with Office 365 by using Azure Active Directory Connect. For instructions, see [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
 **Do you want to integrate Office 365 with software made by other companies?** If you need to integrate Office 365 with other software in your business, we recommend you consider [hiring a partner](https://go.microsoft.com/fwlink/?linkid=391089) to help you with your deployment. 
  
  


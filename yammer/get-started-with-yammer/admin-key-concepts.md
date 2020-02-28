---
title: "Yammer admin key concepts"
f1.keywords:
- NOCSH
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 02/28/2020
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: a9c206d4-fb18-4250-bec6-e783b926e4f6
description: "Key concepts for planning how you'll administer  your new Yammer network. "
---

# Yammer admin key concepts

Welcome to your Yammer network! We're super glad you're here. Using Yammer is going to change the way your company gets work done (if it hasn't already!), and you, as an admin, will be a huge part of helping your coworkers become comfortable with the way Yammer works.
  
Your best resource, and the page you should add to your Favorites is [Yammer admin help](../yammer-landing-page.md): you'll find links for everything you need to do to plan your rollout, configure and customize Yammer, manage users and groups, manage security and compliance, and build community and engagement. 
  
This article describes the key concepts you should know, and key decisions you should make before you open Yammer for business. 
  
## Do some planning

1. To get started with planning, look at the resources in  [Yammer adoption resources](https://resources.techcommunity.microsoft.com/yammer-adoption-resources/). You'll find guides and templates to help you prepare your strategy for how to use Yammer most effectively in your organization, build a Yammer vision statement, identify the business outcomes you want, identify key stakeholders, and build a launch plan. 
    
2. Plan who will help administer Yammer for your organization. There are several types of admins:
    
      - Verified admins have the most permissions, and are responsible for the big decisions of how to use Yammer in your company. They can manage security-related tasks, as well as configure and customize Yammer, and manage users and groups. All Office 365 global admins are automatically Yammer verified admins.
    
      - Network admins can configure and customize Yammer, and manage users and groups. 
    
      - Group admins can configure and customize their groups, and manage day-to-day operations for their groups. 
    
    For information on how to make someone an admin and a full list of who can do what, see [Manage Yammer admins](../manage-yammer-users/manage-yammer-admins.md). 
    
3. Set up your Yammer network to match your organizational goals: 
    
      - [Configure](../configure-your-yammer-network/configure-yammer.md) and [customize](../configure-your-yammer-network/customize-the-look-of-yammer.md) your network. [Set up a usage policy](../manage-security-and-compliance/set-up-a-usage-policy.md) to keep conversations appropriate and useful. 
    
      - Review the [security and compliance features](../manage-security-and-compliance/security-and-compliance.md) and define your data retention and export plans. 
    
      - Make sure your domains are set up in Office 365 the way you want them. By default, your Yammer internal network can be accessed only by employees whose email addresses match the domains verified in Office 365. 
    
        If all your domains are verified in Office 365, you're all set. For more information, see [Manage Yammer domains across their lifecycle in Office 365](../configure-your-yammer-network/manage-yammer-domains.md). 
    
        If your company has business units with different domains, Yammer can help you join these into a consolidated network. You can also create external networks for each business unit, or a singular external network for all employees to access. To weigh these options and merge or create networks, see [Combine multiple Yammer networks](https://go.microsoft.com/fwlink/?LinkID=523730)
    
4. Explore the options for managing user identity:
    
      - Learn how [users are managed from Office 365](../manage-yammer-users/office-365-sign-in.md), including how user profile data from Office 365 is used in Yammer. If you have Yammer users who aren't in Office 365, you can manage them from within Yammer. See [Add, block, or remove Yammer users](../manage-yammer-users/add-block-or-remove-users.md). You can also decide whether to [enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md). 
    
      - Decide whether you'll use Yammer to collaborate with people outside your organization.
    
        Your internal network, also known as a home network, is a private and secure collaboration space where company employees can connect with their coworkers. Only employees with verified corporate email addresses can join the home network and access its content and users. Users from one home network cannot view the content or interact with users from another network unless they are affiliated with both organizations. Messages posted within your home network are owned by your company and cannot be shared externally without permission. Note that admins can invite external users as guests to the internal network, as described in [External messaging FAQ (Yammer)](../work-with-external-users/external-messaging-faq.md).
    
        An external network is a separate extension of your home network, but includes invited users from outside your organization. It is a private and secure collaboration space for your company to engage with outside partners, such as customers, suppliers, or investors. While external networks can accommodate users with different email domains, access is invitation-only. More information about how to set up and use external networks can be found in [Create and manage an external network](../work-with-external-users/create-and-manage-an-external-network.md).
    
5. Explore the options for groups, and set up the groups you need:
    
      - To set up public or private groups, see [Create a group in Yammer](https://support.office.com/article/b407af4f-9a58-4b12-b43e-afbb1b07c889). Though anyone on Yammer can create groups, it is often helpful for the admin to set up groups for each department using a consistent group naming strategy, such as Sales Team, Marketing Team, etc. 
    
      - If you want to use groups that can use Office 365 services, such as SharePoint Online, OneNote, and Planner, called [Office 365 connected groups](../manage-yammer-groups/yammer-and-office-365-groups.md), you need to [enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md).
    
      - Set up groups that include external users, called [external groups](../work-with-external-users/create-and-manage-external-groups.md).
    
      - Decide if you want to use [dynamic groups](../manage-yammer-groups/create-a-dynamic-group.md) to keep membership current as people change roles in your company. 
    
6. People are the core of the enterprise social network, so invite your team to get started on Yammer via the Yammer admin center. 
    
    Users in Office 365 plans that include Yammer automatically get a license to use Yammer Enterprise, but they may not be automatically added to your Yammer network. For information on how users are added to Yammer, see [Manage Yammer users across their lifecycle from Office 365](../manage-yammer-users/manage-users-across-their-lifecycle.md).

    If your network is not enforcing Office 365 identity, to ensure that all your Office 365 users are on Yammer, use the Yammer admin center to add them. For more information, see [Add, block, or remove Yammer users](../manage-yammer-users/add-block-or-remove-users.md). 
    
7. Understand mobile device options, and if needed create a policy for mobile Yammer use. For example, you might require that user's have passwords or other locks on their phones in order to use Yammer on their phone. You can monitor device usage through the Yammer admin center, and [manage Yammer devices by using Microsoft Intune](../manage-security-and-compliance/manage-yammer-with-intune.md). 
    
8. Think through how you want to integrate Yammer with other apps, including SharePoint and Teams. 
    
9. Define how your organization will train and support Yammer users. End-user support options include online help and training, and the online community. See [Yammer help center](https://support.office.com/article/8663922d-8f76-47c2-827a-ee86e8cac00f.aspx). Consider creating a Yammer 101 group - your own local self-support community.
    
    For admin support options, if you need more help than [Yammer admin help](../yammer-landing-page.md) provides, you can [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
    Check the [Office 365 Service health dashboard](https://admin.microsoft.com/AdminPortal/Home#/servicehealth) to see real-time status of the Yammer service. 
    
10. Yammer is always changing. To stay current on what's happening, regularly review the [Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?LinkId=509914). 
    
11. Learn more.
    
    To learn about all the admin features of Yammer, see [Yammer admin help](../yammer-landing-page.md).
     
## FAQs
<a name="Activation"> </a>

### Q: What are the browser and system requirements for Yammer
<a name="Requirements"> </a>

A: Yammer's system requirements are consistent with those of Office 365. See the list of supported browsers in the [Office 365 system requirements](https://support.office.com/article/719254c0-2671-4648-9c84-c6a3d4f3be45).
  
> [!IMPORTANT]
> Internet Explorer 10 support ended on March 1, 2018. For more information, see [Yammer life-cycle support information for Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10](https://go.microsoft.com/fwlink/?LinkId=526880). 
  
#### Mobile and desktop requirements
<a name="bk_MobileDesktop"> </a>

- iOS support for two most recent versions

- Android support for last four most recent versions

- Windows 7 SP1 or later

- MAC OS 10.10 or later

For the most up-to-date information, see [Office mobile apps](https://go.microsoft.com/fwlink/?linkid=2119145) 

### Q: Can I have a Yammer network where some users have Office 365 licenses and some users don't?
<a name="Requirements"> </a>

A: It depends on whether you configure your Yammer network to enforce Office 365 identity.
  
- If you select the option to enforce Office 365 identity, all users must have a Yammer license through Office 365. For more information, see [Enforce Office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md).
    
- If you do not choose to enforce Office 365 identity, users who are on the same email domain as your Yammer network but do not have Office 365 licenses can join the network by creating a Yammer account at https://www.yammer.com.
    
    There are some differences in how you manage these users: their profile won't be automatically filled in, and you can't block them by removing their Yammer license. These users can be made admins, create groups, and use all basic Yammer features. If they are made admins, they have to get to the Yammer admin center by clicking the **Settings** icon in Yammer, and selecting **Network Admin**.

    
### Q: What are the limitations of Yammer (number of users, networks, documents, storage, access, and so on)?
<a name="Requirements"> </a>

A: Yammer is designed as a SaaS, multi-tenant environment with scale in mind. The  *only*  limit is file size. An individual file can't be larger than 5 GB in Yammer Enterprise or100 MB in Yammer Basic.) Both versions support unlimited users, unlimited files, unlimited external networks, and unlimited document types. 
  
### Q: What file types can be uploaded to Yammer?
<a name="Requirements"> </a>

A: By default, there are no restrictions on the file types that can be uploaded. A Yammer Enterprise network admin can go to **Settings** \> **Network Admin** \> **Configuration** to change this. The Yammer network admin can restrict file uploads and allow only photo and video file types to Yammer. In the case of a network that allows only photo and video file types, we make our best effort to enforce this restriction by checking the file extension and some of the files' metadata, but do not guarantee that users can't bypass this restriction. 
  
### Q: Why am I seeing different features, colors, or a different layout than my colleagues?
<a name="Requirements"> </a>

A: As part of Yammer development methodology, we A/B test all aspects of Yammer and use data to select the better design. The tests are performed on a subset of users across all networks, so changes don't occur at the network level until they're tested and launched. 
  
### Q: What's the roadmap for Yammer?
<a name="Requirements"> </a>

A: Yammer rapid release and iterative development methodology means that change is constant. The items currently being developed and their stage of development and testing are available in the [Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?LinkId=509914).

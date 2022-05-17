---
title: "Upgrade your network to stand-alone Yammer Enterprise subscription"
f1.keywords:
- NOCSH
ms.author: pamgreen
author: ToniSFrench
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid:
- MET150
- SPO160
- MOE150
- YAE150
- BSA160
ms.assetid: 9cdcf894-4a3d-4956-8a6c-6cb4d62770ea
ROBOTS: NOINDEX
description: "Upgrade a Yammer Basic network to Yammer Enterprise and get more granular control over the look and feel, content and membership management, or security of your Yammer network. "
---

# Upgrade your network to stand-alone Yammer Enterprise subscription

Yammer Basic is an enterprise social networking service that helps workers connect, share, and collaborate. It's a free service that provides companies and their employees with a private network for posting messages, uploading files, "liking" posts, "following" particular individuals, tagging posts, searching, and so on. When a company signs up for the Yammer Basic service, any employee of that company who has a valid company email address can participate in the Yammer network. Yammer Basic is included with Office 365.
  
Qualifying Office 365 customers who are looking for more granular control over the look and feel, content and membership management, or security of their Yammer network can upgrade the service to Yammer Enterprise. Yammer Enterprise provides all of the features of Yammer Basic but adds branding, security, and administrative features that enable customization and protection of the private network. Features include:
  
- The option to create a custom design so you can brand the network with the company's look and feel
    
- Advanced configuration settings that provide overall user governance and content management
    
- Robust security controls that help you manage network access and security
    
- The ability to export network data for reporting, retention, and analysis
    
## How to upgrade


You can activate Yammer Enterprise through the Microsoft 365 admin center by following these steps.
  
1. Navigate to the Microsoft 365 admin center.
    
2. Under included services, click **Yes, activate Yammer Enterprise for my network**.
    
3. Follow the steps in the wizard.
    
Upon activation, your Office 365 Global Administrators will become administrators in the corresponding Yammer network and can customize and administer Yammer. Please note that Yammer administrators must have a domain that matches the Yammer network. For example, on the contoso.com network, only Office 365 global administrators with an @contoso.com email address will become Yammer administrators. Also, Yammer administrator account email addresses must not contain "admin," "support" or "user."
  
For more information about the upgrade to Yammer Enterprise, see [Yammer Plans &amp; Pricing](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans). 
  
## Determine your Yammer Enterprise upgrade strategy


Your Yammer service includes a private network or collection of private networks that are organized by email domain. Yammer creates a network for every unique email domain in your organization so at sign-in, users will be routed to the Yammer network that matches their email address. For example, john@contoso.com would be in the  *contoso.com*  network. 
  
Some organizations have only one email domain for all users; large organizations often have multiple domains based on business unit or locale (e.g., contosoeurope.com, contosoasia.com, and so on). If you have multiple domains, you'll have to determine your Yammer network upgrade strategy.
  
When defining your upgrade strategy, you'll determine which existing Yammer network to upgrade, whether to create a new one, and how secondary networks will be integrated into your social networking vision. The way in which you upgrade and combine networks determines the amount of collaboration that will be possible among users, particularly if employees are spread out among different business units, subsidiaries, or geographies. The key is to decide whether you want the end product to be one central Yammer network that's accessible by the majority of users in your organization or multiple networks that are segmented by email domain.
  
### Upgrade one existing network or create a new one

Upgrading or creating one central Yammer network is the recommended approach because it facilitates collaboration among all employees and allows for users from other domains to be invited to the primary domain as guests. A single network also provides for centralized administration, which ensures consistency in policy implementation and management, feature rollout, scheduled maintenance, and so on. A single network makes sense when all employees are in one location or are dispersed but share a common email address.
  
When you choose to upgrade a single network, you'll want to choose either the email domain that the majority of users can access, which is usually the primary organization email alias, OR the network with the most data so as to retain valuable content. You'll retain the corresponding content and active users when you upgrade an existing Yammer network.
  
Most organizations have one primary domain for employee email addresses, so upgrading or creating a single network is the most common approach.
  
### Upgrade multiple networks

If you have multiple Yammer networks, we recommend that you consolidate the smaller networks into your organization's primary network by performing a network migration (see [Network migration: Consolidate multiple Yammer networks](../configure-your-yammer-network/consolidate-multiple-yammer-networks.md)). Consolidating networks lets you:
  
- **Reduce Yammer administration cost:** After the consolidation, you can manage one single Yammer service, rather than managing individual Yammer networks. 
    
- **Reduce information silos in your organization:** Having a consolidated Yammer service that is shared by all your users empowers them to connect and work with everyone in your organization. 
    
- **Allow Office 365 users to sign-in to Yammer easily:** Users can sign-in to Yammer with their Office 365 credentials, and easily access Yammer from the Office 365 app launcher. See [Office 365 sign-in for Yammer](../manage-yammer-users/office-365-sign-in.md).
    
- **Seamlessly manage the Yammer service from Office 365:** After the consolidation, the management of Yammer service is simplified. For example, you can have a single sign-on solution when you [enforce office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md), and you can manage users and administrators centrally from Office 365 when you [manage Yammer users across their life cycle from Office 365](../manage-yammer-users/manage-users-across-their-lifecycle.md).
    
### Upgrade one network and merge associated domains or pre-existing networks

When you integrate an email domain that has an existing Yammer network into a larger parent network, it's called a network merge. A network merge is a valid option when an organization has multiple business units or subsidiaries that want to take advantage of the collaboration and administrative features of Yammer Enterprise but don't share a common email domain. In this scenario, all users can join a single network without express Network Administrator permission and begin collaborating from initial log-in.
  
For example, let's say Contoso.com is an international company with subsidiaries in major cities around the world. Each of those subsidiaries has different product lines to serve the unique needs of customers in the area. Employee email addresses reflect the name of their subsidiary (@contosoeurope, @contosoasia, etc.). In a network merge, all subsidiary domains would be merged into the parent Yammer network, such as @contoso.com, and users with subsidiary email addresses would be routed to the parent Yammer network when they sign in.
  
When upgrading and merging domains, we recommend that you choose the most relevant existing network, that is, the network with the most content or users to be your parent network. You'll want to consider this option carefully because merging email domains will cause users to lose access to any content that was created in their original Yammer network.
  
Contact [Yammer Enterprise Support](https://support.microsoft.com/oas/default.aspx?prid=14876) to work through the plan for a network merge. 
  
> [!NOTE]
> Integrating an email domain that isn't affiliated with a Yammer network into a larger parent network is called a "domain add." Because there is no pre-existing Yammer network, no content will be lost during the domain add process. 
  
#### Prepare your users for the network merge

Any time you roll out new technology or services, it's imperative to inform and prepare your users, particularly if a network merge is part of your rollout process. This not only gives you the opportunity to build excitement in your user community but provides community members the chance to learn and voice questions well before the new technology arrives. Clear, engaging, and well-timed communications are critical to the success of your rollout. Here are some suggestions for ensuring a successful merge.
  
1. Prior to the merge, communicate to users whose networks will be merged with the parent network the date, time, and effects of the merge. In this communication, share the reasons for the merge, highlight the benefits, and provide instructions for archiving private message data, notes, files, and so on. Let them know that this data will be inaccessible after the merge. See the Communication Plan for a template.
    
2. Inform users in the parent network that new users are joining and encourage current users to welcome the new ones.
    
3. Consider a data export prior to the merge, particularly if your organization adheres to specific data retention policies. Data exports must be handled by the Verified Administrator.
    
## Resources
<a name="__support_resources"> </a>

Yammer provides a number of tools, templates, and support resources for planning and implementing your upgrade to Yammer Enterprise: 
    
- [Yammer Enterprise Support](https://support.microsoft.com/oas/default.aspx?prid=14876) includes both online submission and phone support. 
    
- The [Yammer site status](https://status.yammer.com/) page contains the latest details on the health of your Yammer site. 
    
## Related articles

[Pick your enterprise social network: Yammer or Newsfeed?](../integrate-yammer-with-other-apps/yammer-and-newsfeed.md)
  
[Say hello to Yammer](https://support.office.com/article/02ac514e-cf1d-4060-9cde-6038ca812ede)

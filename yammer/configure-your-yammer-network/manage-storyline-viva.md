---
title: "Manage storyline for Microsoft Viva Engage and Yammer"
description: "Manage storyline for Microsoft Viva Engage and Yammer"
ms.author: v-jebizie
author: v-jebizie
manager: dmillerdyson
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: viva
localization_priority: Priority
ms.collection:  
- M365initiative-viva
search.appverid:
- MET150
---

# Manage storyline for Microsoft Viva Engage and Yammer 

Storyline empowers everyone within your organization to connect and contribute, and enables your leaders to reach and engage employees. Through storyline, people can share updates, experiences, and perspectives to reach followers and colleagues across the organization. Engage with storylines from the Web and mobile applications you use every day: Outlook, Microsoft Teams, Yammer, and Microsoft Viva. 

When storyline is enabled in your organization, you'll see the following changes in Yammer and the Viva Engage app.  

1. Internal (non-guest) users who have access to Yammer and Viva Engage see a new default storyline tab on their user profile page.    
2. Users see a new “storylines” page from which they can access a personalized feed of content posted to storyline, or toggle to a focused feed that includes only storyline content from the people the user has followed. 

## Configuration quick start guide 
Configuration and management of storyline is straightforward. Yammer Network and Verified admins can manage storyline for their organizations by clicking the “Manage storyline” link that is behind the gear icon on Yammer.com, and behind the ellipsis in the global header for the Viva Engage app. 
 
### Enabling storyline
Once storyline has reached general availability, a single toggle can be used to enable or disable storyline. During public preview, admins will have two toggles for enabling storyline within their organization. 

* **Enable public preview of storyline**: This toggle is defaulted to the OFF position. Select this option if you would like to turn on storyline for your organization during public preview. This toggle will be removed once storyline has reached general availability. 

* **Enable storyline when it reaches general availability**: This toggle is defaulted to the ON position, which means storyline will become available to your users when the feature has been fully released. This control is independent of the public preview control, so that customers can choose whether or not to automatically enable storyline regardless of their usage of storyline in public preview.  

When you enable storyline in your organization, it becomes available to all internal users who have access to Yammer and Viva Engage. All internal users will have their own storyline feed on their profile pages and will be able to see, react, and respond to others’ storyline posts. Guests won't have their own storyline, and won't be able to see or engage with storyline content from your internal users who do. 

When you disable storyline, it removes the storylines tab from all user profile pages and removes the storylines landing page. Disabling storyline prevents new storyline conversations from being started, but does not delete any conversations that were posted prior to storyline being disabled. Previously posted storyline content can still be accessed through search and the Yammer Inbox by the people who participated in the storyline conversation. Users who didn't participate in the conversation won't have access after storyline has been disabled. Storyline content will continue to be available through network data export and will be available through eDiscovery for networks that are in native mode.  

## Preview features
This toggle allows you to preview some of the features that will be available in Yammer and the Viva Engage app through Viva Engage. The features available through this preview will be available to all of the internal users in your tenant who have access to Yammer and Viva Engage, irrespective of license status. Pricing and licensing requirements for these features post-preview are yet to be determined. 

The preview is currently scheduled to continue until at least December 31, 2022. All features from this preview will be turned off automatically at the end of the preview without any intervention or obligations required from you. 

The features included in the preview include: 
* Conversation insights for storyline – Users are able to see detailed metrics for conversations they’ve posted to their storyline including impressions, reactions, and comments. 

* Storyline digest – This collects any unseen storyline posts for the week from followed people and sends it to the user once per week in an email or notification in their Teams activity feed. The storyline digest isn't sent if the people followed don't post, or if all of the posts were already seen by the user.  

* Post on behalf of (POBO) for storyline – During the preview, any user who has assigned POBO delegates can give those delegates the additional privilege of posting to the assigning user’s storyline. 

* Custom cover photo – This feature allows users to customize their user profile page by uploading a photo to be the background image for the header of their user profile page.     
 
## Security and compliance 

Storyline is built on the same content and conversation platform as community messages in Yammer and Viva Engage. This means that you can use the same tools for storyline that you use today for monitoring and governance.  

* eDiscovery through the compliance portal for native mode networks  
* Storyline content is available via network export 
* Files shared through storyline are stored in OneDrive and are subject to any governance you already have in place 
* Storylines supports the same “[Report a conversation](/yammer/manage-yammer-groups/configure-conversation-reporting)” feature available for community conversations 
* Microsoft Purview Communications Compliance (E5): Use AI to monitor conversations for bullying, harassment, or topics that are against usage policy 

In addition to the capabilities listed above, storyline also features a feed that includes all storyline posts sorted by the date the storyline conversation was started. To access this feed, go to the storyline landing page. While on the feed, click the filter icon in the upper right corner of the feed to switch the filter to “All”. 

## Frequently Asked Questions (FAQ)
 
### Why isn’t storyline available in our organization? 
Storyline is only supported in Yammer enterprise networks that [enforce Office 365 identity](/yammer/configure-your-yammer-network/enforce-office-365-identity). If your network doesn't enforce Office 365 identity, or if you have a Yammer Basic network, storyline won't be available to your organization. 

### Who can see storyline content? 
Storyline content is visible to any internal user who has access to Yammer and Viva Engage. Guests won't be able to see any storyline content.  

### Does storyline work for guests? 
Guests are excluded from storyline access. They won't have their own storyline, and won't be able to see any storyline content posted by other users. 
 
### Can I control who sees storyline content? 
It isn't possible to prevent any internal user from seeing storyline content if they have access to Yammer and Viva Engage. Guests won't be able to see any storyline content. 
 
### Can I control which users get their own storyline?  
We plan to add the capability of limiting who gets their own storyline shortly after storyline reaches general availability. Once available, you'll be able to designate, via AAD groups, which users will have a personal storyline feed appear on their user profile page in Yammer. Users to whom you don’t grant a storyline will be able to reply and react to storyline posts from users who do have their own storyline. 
  
## Getting support 
**IMPORTANT**: The storyline public preview is unsupported. The Service Level Agreement (SLA) for Microsoft Online Services doesn't apply to this preview. 

When a reproducible break-fix issue affects the storyline public preview and a support case is opened, the issue will be logged for later investigation by the Yammer product group. The support case will be closed when adequate information has been captured. It may not be possible to resolve all issues reported during the public preview. 

### Do SLAs apply to the storyline public preview? 
The Service Level Agreement for Microsoft Online Services doesn't apply to this preview. 

### What is a break-fix issue? 
Break-fix issues are technical problems you experience while using the storyline public preview. Break-fix is an industry term that refers to work involved in supporting a technology when it fails in the normal course of its function, which requires intervention by a support organization to be restored to working order. 

### How do I open a support case? 
See the [Support for business products - Admin Help](https://aka.ms/yammersupportcase) page for general information. Your organization may have specific guidance for opening support cases, so you may need to talk with your IT team. 

### How should I submit feature requests and feedback? 
Feature requests and feedback on the product during preview should be submitted through the in-product feedback dialog boxes. 

Microsoft Support won't be accepting formal feature requests for the storyline public preview submitted via the Design Change Request (DCR) process during the preview period. 

### What severity of cases should be accepted during the preview? 
Open non-critical (severity B or C) cases during the preview period for break/fix issues affecting the storyline public preview. Critical (severity A) cases won't be accepted for preview features. 

### What steps should I take before reporting a technical problem? 
Before reporting a technical problem to Microsoft Support, check the following: 

* Can the issue be reproduced consistently? If the issue isn't occurring now, then it may have been resolved by a recent product update. 
* Can the issue be reproduced in multiple browsers? Testing with at least two different web browsers is best practice. 
* Does the issue occur on mobile as well? Sometimes issues occur with a backend service which affect multiple clients (web, mobile, or desktop). 
* Are multiple users affected? Issues affecting multiple users are more likely to be prioritized. 
* Do you have clear screenshots? Closely cropped screenshots can miss important information that is showing elsewhere on the screen. 
* Is there any relevant information in the browser developer tools? Support may ask you to check the JavaScript console for error information. While not everyone is familiar with JavaScript, you can often hit F12 in your browser on Windows and look for red error messages in the console tab. 

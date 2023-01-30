---
title: "Manage Storyline for Microsoft Viva Engage and Yammer"
description: "Manage Storyline for Microsoft Viva Engage and Yammer"
ms.author: mamiejohnson
author: mamiepjohnson
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
ms.date: 08/30/2022
---

# Manage Storyline for Microsoft Viva Engage and Yammer 

Storyline empowers everyone within your organization to connect and contribute, and enables your leaders to reach and engage employees. Through Storyline, people can share updates, experiences, and perspectives to reach followers and colleagues across the organization. Engage with Storylines from the Web and mobile applications you use every day: Outlook, Microsoft Teams, Yammer, and Microsoft Viva. 

When Storyline is enabled in your organization, you'll see the following changes in Yammer and the Viva Engage app.  

1. Internal (non-guest) users who have access to Yammer and Viva Engage see a new default Storyline tab on their user profile page.    
2. Users see a new **Storylines** page from which they can access a personalized feed of content posted to Storyline, or toggle to a focused feed that includes only Storyline content from the people the user has followed. 

## Configuration quick start guide 
Configuration and management of Storyline is straightforward. Yammer Network and Verified admins can manage Storyline for their organizations by selecting the **Manage Storyline** link that is behind the gear icon on Yammer.com, and behind the ellipsis in the global header for the Viva Engage app. 

## Enabling Storyline
Once you have entered the Manage Storyline screen, you will see the toggle which controls the availability of Storyline within your organization. When you enable Storyline in your organization, it becomes available to all internal users who have access to Yammer and Viva Engage. All internal users will have their own Storyline feed on their profile pages and will be able to see, react, and respond to others’ Storyline posts. Guests won't have their own Storyline, and won't be able to see or engage with Storyline content from your internal users who do. 

When you disable Storyline, it removes the Storylines tab from all user profile pages and removes the Storylines landing page. Disabling Storyline prevents new Storyline conversations from being started, but does not delete any conversations that were posted prior to Storyline being disabled. Previously posted Storyline content can still be accessed through search and the Yammer Inbox by the people who participated in the Storyline conversation. Users who didn't participate in the conversation won't have access after Storyline has been disabled. Storyline content will continue to be available through network data export and will be available through eDiscovery for networks that are in native mode.  

## Advanced Settings

Storyline supports additional controls for admins who wish to customize their configuration of Storyline. Initially, this includes setting the default notification preferences for Storyline, but we expect other advanced features to follow. 

### Set default notification channels for Storyline posts

Storyline, in its default configuration, notifies followers via Teams, Email, and Yammer, when a person they are following posts to their Storyline. Network and Verified admins can override the network default with custom defaults for their organization. If you customize this for your network, it will change what default notifications are selected when a user follows someone. Users can always change from the default selections to their personal preferences for notifications for each person they follow.  
 
The system default selections for notifications include: 

- Microsoft Teams – notifications are delivered in the Teams Activity feed 
- Email – email delivered to your Inbox includes support for Actionable messages, so the conversation can be viewed and replied from Outlook Web Access.
- Viva Engage & Yammer – notifications are delivered to the Viva Engage & Yammer notification bells. 

## Preview features
This toggle allows you to preview some of the features that will be available in Yammer and the Viva Engage app through Viva Engage. The features available through this preview will be available to all of the internal users in your tenant who have access to Yammer and Viva Engage, irrespective of license status. Pricing and licensing requirements for these features post-preview are yet to be determined. 

The preview is currently scheduled to continue until at least December 31, 2022. All features from this preview will be turned off automatically at the end of the preview without any intervention or obligations required from you. 

The features included in the preview include: 
* Conversation insights for Storyline – Users are able to see detailed metrics for conversations they’ve posted to their Storyline including impressions, reactions, and comments. 

* Storyline digest – This collects any unseen Storyline posts for the week from followed people and sends it to the user once per week in an email or notification in their Teams activity feed. The Storyline digest isn't sent if the people followed don't post, or if all of the posts were already seen by the user.  

* Post on behalf of (POBO) for Storyline – During the preview, any user who has assigned POBO delegates can give those delegates the additional privilege of posting to the assigning user’s Storyline. 

* Custom cover photo – This feature allows users to customize their user profile page by uploading a photo to be the background image for the header of their user profile page.     
 
## Security and compliance 

Storyline is built on the same content and conversation platform as community messages in Yammer and Viva Engage. This means that you can use the same tools for Storyline that you use today for monitoring and governance.  

* eDiscovery through the compliance portal for native mode networks  
* Storyline content is available via network export 
* Files shared through Storyline are stored in OneDrive and are subject to any governance you already have in place 
* Storylines supports the same “[Report a conversation](/yammer/manage-yammer-groups/configure-conversation-reporting)” feature available for community conversations 
* Microsoft Purview Communications Compliance (E5): Use AI to monitor conversations for bullying, harassment, or topics that are against usage policy 

In addition to the capabilities listed above, Storyline also features a feed that includes all Storyline posts sorted by the date the Storyline conversation was started. To access this feed, go to the Storyline landing page. While on the feed, click the filter icon in the upper right corner of the feed to switch the filter to **All**. 

#### Security, compliance, and governance for files uploaded to Storyline posts and stories

Storyline posts and stories are backed by Yammer services. Compliance for posts and stories are therefore the same as the rest of Yammer and Viva Engage. If you are in native mode, posts are ingested into the substrate and support the same compliance and e-Discovery capabilities as posts in communities, including communications compliance and retention. Because files are stored in OneDrive, they inherit security and compliance policies configured for files in OneDrive. 

When users are deleted—for example when an individual leaves the company—the system follows the Microsoft 365 user deletion process described in the section called **Delete a user** in the “[Manage Yammer users across their lifecycle from Office 365 – Yammer | Microsoft Docs.](/yammer/manage-yammer-users/manage-users-across-their-lifecycle)” 

## File storage for Storyline

Files attached to Storyline posts, and videos or photos shared as stories, are stored in a hidden library in the author’s OneDrive. While there is no entry point to this location in the user experience (UX) of Microsoft 365, you can access it with a URL resembling the following example: https://tenantname-my.sharepoint.com/personal/**useridentifier/VivaEngage/Attachments/Storyline**

You can determine the precise URL for a user's Storyline folder by following these steps: 

1. Open the user's OneDrive in the browser.
2. Note the URL to the user's OneDrive.
3. Locate the **user identifier**, located in the URL immediately after my.sharepoint.com/personal/ 
4. Remove everything after the profile identifier and the backslash, and replace with **VivaEngage** (without a space, case insensitive). The resulting URL will resemble this example: https://tenantname-my.sharepoint.com/personal/**useridentifier/VivaEngage**
5. Press ENTER. The library will appear.  
6. Open the Attachments folder, then open the Storyline folder. The resulting URL directly to the folder where Storyline files are saved will resemble this example: https://tenantname-my.sharepoint.com/personal/**user identifier/VivaEngage/Attachments/Storyline**. 

### Managing files uploaded to Storyline posts and stories 

Edit documents and rich media uploaded to posts using the Storyline interface. We strongly discourage you from managing (adding, replacing, or deleting) documents and rich media directly in OneDrive, as you will risk breaking the front-end experience of posts and stories in your Storyline.  

If you wish to delete files associated with a post or story from the **VivaEngage** library: 
1. Remove the file from the associated post. From any post, the author or an admin can select the ellipsis (...) menu and choose **Edit**.  
2. Navigate to the author's **VivaEngage** library and delete the file itself. 

## Frequently Asked Questions (FAQ)
 
### Why isn’t Storyline available in our organization? 
Storyline is only supported in Yammer enterprise networks that [enforce Office 365 identity](/yammer/configure-your-yammer-network/enforce-office-365-identity). If your network doesn't enforce Office 365 identity, or if you have a Yammer Basic network, Storyline won't be available to your organization. 

### Who can see Storyline content? 
Storyline content is visible to any internal user who has access to Yammer and Viva Engage. Guests won't be able to see any Storyline content.  

### Does Storyline work for guests? 
Guests are excluded from Storyline access. They won't have their own Storyline, and won't be able to see any Storyline content posted by other users. 
 
### Can I control who sees Storyline content? 
It isn't possible to prevent any internal user from seeing Storyline content if they have access to Yammer and Viva Engage. Guests won't be able to see any Storyline content. 
 
### Can I control which users get their own Storyline?  
We plan to add the capability of limiting who gets their own Storyline shortly after Storyline reaches general availability. Once available, you'll be able to designate, via AAD groups, which users will have a personalStoryline feed appear on their user profile page in Yammer. Users to whom you don’t grant a Storyline will be able to reply and react to Storyline posts from users who do have their own Storyline. 

### How do I delete custom cover photos that are uploaded to a person’s Storyline? 
When the preview features toggle is in the ON position, uploaded cover photos can be deleted by the user themselves, or by Network and Verified Admins, by going to the user profile page and choosing the delete option under **Update cover photo**. 

If you want to delete a previously uploaded cover photo when the preview toggle is in the OFF position, you will need to temporarily opt in to the preview so you can access the delete cover photo option as discussed above.   
  

---
title: "Yammer and Office 365 Groups"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 5/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOP150
- MOE150
- MEW150
- MED150
ms.assetid: d8c239dc-a48b-47ab-b85e-6b4b8191a869
description: "If your network is eligible, group experiences in Yammer can get access to Office 365 services, including a SharePoint Online team site and document library, a OneNote notebook, a plan in Planner, and a workspace in PowerBI. This is called an Office 365 connected group."
---

# Yammer and Office 365 Groups

If your network is eligible, group experiences in Yammer can get access to Office 365 services, including a SharePoint Online team site and document library, a OneNote notebook, a plan in Planner, and a workspace in PowerBI. This is called an Office 365 connected group. 
  
You can tell if a group in Yammer is connected with Office 365 groups when you see the Office 365 Resources section in the right navigation of the group: 
  
![Screenshot showing Office 365 Resources](../media/195dd76c-6007-469e-9242-7889a3b217a9.png)
  
For information on how to create and manage a group, see [Create a group in Yammer](https://support.office.com/article/b407af4f-9a58-4b12-b43e-afbb1b07c889) and [Manage a Yammer group](https://support.office.com/article/6e05c6d6-5548-4c88-89cd-e6757a514ef2.aspx).
  
## Configuration requirements to enable Yammer integration with Office 365 Groups in your tenant

If you are interested in having Yammer integration with Office 365 Groups enabled in your Office 365 tenant, make sure you meet the following requirements:
  
1. The Yammer's integration with Office 365 Groups is initially available only for 1:1 network configurations. This means you have one Yammer network that is associated with one Office 365 tenant.
    
2. You must [enforce Office 365 identity](../configure-your-yammer-network/enforce-office-365-identity.md) for Yammer users. 
    
Only groups owned by users with group creation privileges are connected to Office 365. In other words, people who cannot create new Office 365-Connected Yammer groups today will not see the existing Yammer groups they own get connected to Office 365.
  
## Email and Yammer groups

In a connected group, you can have group conversations in Yammer or in Outlook.
  
You can send an email to a group in Yammer and it will appear in the group messages. Additionally, the Office 365 connected Yammer group's name is in the global address list (GAL) of your company. Your company can continue to use groups in Yammer and Groups in Outlook based on which group type better fits the scenario for a team.
  
Also, just like today, email notifications may be sent to users depending on the preferences that they have set in their Yammer notification settings.﻿
  
## Plans for additional integration with Office 365 Groups

Yammer's integration with Office 365 Groups started in 2017. Subsequent phases will address remaining groups types, Office 365 tenants, and deliver integration with Outlook calendar and enhancements for SharePoint and Planner. The best place to stay informed of change management is to follow the Yammer updates on the [Office 365 Roadmap](https://fasttrack.microsoft.com/roadmap).
  
## FAQ

 **Q: I'm an admin, how do I know if my Yammer network is configured correctly and eligible for Office 365 connected Yammer groups?**
  
A: In the Yammer admin center, click **Security Settings**. In the **Office 365 Connected Yammer Groups** section, you'll see the status for your network. 
  
 **Q: Can I disable Office 365 Yammer Connected Groups?**
  
A: No, but you can [Manage who can create Office 365 Groups](https://support.office.com/article/4c46c8cb-17d0-44b5-9776-005fced8e618). These restrictions do not apply to tenant admins. .
  
 **Q: If I [Manage who can create Office 365 Groups](https://support.office.com/article/4c46c8cb-17d0-44b5-9776-005fced8e618) for my tenant, will the groups that I create in Yammer be Office 365 connected? **
  
A: No. In that case the groups you create in Yammer will not be Office 365 connected.
  
 **Q: If I have multiple Yammer networks that are mapped to Office 365, will the** **Office 365 connected Yammer groups work?**
  
A: No. The Office 365 connected Yammer groups experience will work only for Office 365 tenant that is associated with a single Yammer network. See [Network migration: Consolidate multiple Yammer networks](../configure-your-yammer-network/consolidate-multiple-yammer-networks.md) for information on how to consolidate your Yammer networks. 
  
 **Q: What kinds of Yammer groups can be Office 365 Groups?**
  
A: To start with, only private and public internal groups will be enabled. External groups and private-unlisted groups will be included in a later wave.
  
 **Q: Can I make my Office 365 connected Yammer group private and not list it in Group Directory (secret)?**
  
A: No. That setting is not available for Office 365 connected Yammer groups.
  
 **Q: Where can I create Office 365 connected Yammer groups?**
  
A: Only in Yammer.
  
 **Q: Can I create an Office 365 connected Yammer group in the Office 365 admin center?**
  
A: No, this will be added in later waves. However, you will be able to manage members and delete groups from the Office 365 admin center. Metadata updates can also be applied to groups from the admin center.
  
 **Q: Can I add external users to** **Office 365 connected Yammer groups?**
  
A: No. This will cause a sync failure because external users are not managed by Azure AD.
  
 **Q: I don't want my existing groups to get connected to Office 365. Can I turn this off?**
  
A: No, but you can [Manage who can create Office 365 Groups](https://support.office.com/article/4c46c8cb-17d0-44b5-9776-005fced8e618) which will also apply to the backfill for existing groups. Only groups owned by users with group creation privileges will be connected to Office 365. If you apply new a creation policy, this will not retroactively change groups that are connected to Office 365. This will only impact new groups moving forward. 
  
 **Q: If I become eligible for connected groups, what happens?**
  
We will begin connecting your existing groups as new groups get connected.
  
 **Q: How many members can my group have?**
  
A: More than 1,000.
  
 **Q: What happens if I delete an Office 365 connected Yammer group?**
  
A: As with all Office 365 groups, all the content associated with the group is deleted. This includes the document library, OneNote notebook and Planner plans. See this article about [Delete a group](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) for details. 
  
 **Q: Can I have a group with dynamic membership in Yammer**
  
A: Yes. Any Office 365 connected Yammer group can be converted to dynamic membership. See [this article](create-a-dynamic-group.md)for requirements and limitations.
  
 **Q:** **In a new group, I see there are Yammer Files and a SharePoint Online Doc Library, are these the same thing?**
  
A: No, these are separate locations to store files but the members of the group have access to both locations. Files uploaded to Yammer are stored in Azure today and will remain so for the time being, while retaining all their current permissions and capabilities. With Office 365 connected Yammer groups, users will also be able to upload and store files in their group's SharePoint document library. 
  
We recommend storing content that needs the structure and management capabilities of SharePoint in the group document library. For easy, quick sharing of images and documents, or to stream videos in Yammer, we recommend continuing to use Yammer. Longer term, our plan is to migrate all files stored in Yammer to SharePoint to provide unified file storage.
  
 **Q: Do my Office 365 connected Yammer groups follow my Office 365 group naming policy?**
  
A: Yes. Any new group created in Yammer will add the prefix and suffix from the group naming policy, and will not allow blocked words in the group name. For more information, see [Office 365 Groups naming policy](https://support.office.com/article/6ceca4d3-cad1-4532-9f0f-d469dfbbb552).
  
 **Q: How does Office 365 First Release fit into Yammer integration with Office 365 Groups?**
  
A: Yammer uses A/B Testing to inform product decisions which is a process that includes all users in all networks. You cannot opt-in nor opt-out to Yammer A/B Testing. Other Office 365 properties like SPO and Planner employ the Office 365 First Release program which may manage access to new capabilities and changes within that technology. For more information on Office 365 First Release program, see [How Office 365 commercial customers can get early access to new Office 2016 features](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead).
  
## See also

[Create a group in Yammer](https://support.office.com/article/b407af4f-9a58-4b12-b43e-afbb1b07c889)
  
[Manage a group in Yammer](https://support.office.com/article/6e05c6d6-5548-4c88-89cd-e6757a514ef2.aspx)


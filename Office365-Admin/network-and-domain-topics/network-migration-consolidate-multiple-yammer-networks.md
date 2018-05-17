---
title: "Network migration Consolidate multiple Yammer networks"
ms.author: v-irpast
author: v-irpast
manager: scotv
ms.date: 3/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid: YAE150
ms.assetid: a22c1b20-9231-4ce2-a916-392b1056d002
description: "Migrate one or more subsidiary Yammer networks into a parent Yammer Enterprise network (previously called 'Network merge')."
---

# Network migration: Consolidate multiple Yammer networks

You can migrate one or more Yammer networks with their own email domains ("subsidiary" networks) to a larger Yammer Enterprise network ("parent" network). The subsidiary networks can be either Yammer Basic or Yammer Enterprise, but the parent network must be Yammer Enterprise. For example, assume your company has multiple business units or subsidiaries, and each one of them has its own Yammer network. Also, you have a Yammer network at the parent company and want to get all of your employees closely collaborating with each other on the parent network. In other words, you want to consolidate the subsidiary networks. You can do this by migrating the subsidiary Yammer networks into your parent Yammer network.
  
> [!NOTE]
> Migrating Yammer networks across Office 365 tenants is not supported. 
  
Here's an example showing Contoso, Ltd. with subsidiaries, each one of which has its own Yammer network:
  
- **Contoso.com** The parent network for Contoso, Ltd.; serves users with emails @contoso.com. 
    
- **Contoso_Sub.com** A subsidiary network for employees of a division of Contoso, Ltd.; serves users with emails @contoso_sub.com. 
    
- **ContosoPharmaceuticals.com** A subsidiary network for employees of the Pharmaceutical division; serves users with emails @contosopharmaceuticals.com. 
    
Contoso, Ltd. wants to keep the pharmaceutical employees in their own network but wants to move employees from Contoso_Sub.com to Contoso.com. Contoso, Ltd. would migrate the users from the Contoso_Sub.com subsidiary to the Contoso.com parent network.
  
The following illustration shows the Contoso_Sub subsidiary network before being migrated into the Contoso parent network.
  
![A subsidiary Yammer network and a parent Yammer network before a migration is performed to consolidate the users from the subsidiary into the parent network](/Office365/Admin/media/53972669-499c-4255-8098-25448a47b08c.png)
  
The following illustration shows the after state, where the users and any external networks and users have been migrated from Contoso_Sub to the Contoso, Ltd. network. Notice that the subsidiary network and its content are not available after migration.
  
![After a Yammer network migration, the users from the subsidiary network have been consolidated into the parent network. Any external networks have also been migrated (with users). The subsidiary network (including all content) is no longer available.](/Office365/Admin/media/b76d79f6-8e1c-47bc-8b99-0e636dc30f91.png)
  
If you're just looking to add guest users or work together across company boundaries, consider [external messaging](../external-messaging-topics/add-external-messaging-participants-to-your-yammer-conversations.md) or [](../configure-your-yammer-network.md#ExternalNetworks) instead of migrating. 
  
> [!CAUTION]
> **A network migration migrates only the active and pending users.**Along with the active users, the users' information, such as name and profile picture, is also migrated. Any network content, including groups, is not migrated. > **Network migration can't be reversed.** You will not be able to access your subsidiary network and its content after migration. So before you consider a migration, you want to plan carefully. 
  
## Before you begin

Keep in mind:
  
- Only users with the global admin role in Office 365 can perform network migration. This is because network migration involves looking up the list of verified domains on the Office 365 tenant, which needs global admin permissions.
    
- Multiple network migrations can be started back-to-back, without waiting for the previous ones to finish.
    
- If a user exists in both networks, the user's account in the parent network will remain and will be promoted from a guest account to a regular account, if necessary, and the account in the subsidiary network will be deleted.
    
It is critical to communicate major network changes such as migration early to all users - so that users can be prepared and can start using and benefitting from these changes. We recommend that you do the following before starting the network migration:
  
- Review the content/activity in your subsidiary network, export any data you need, and after migration, manually move any content you want to keep, including the manual re-creation of relevant groups. For information about how to export your Yammer data, see [](../security-and-compliance-topics/manage-yammer-data-compliance.md#ExportData). Note that all source network content will be lost during migration.
    
- Because a network migration is a big change for your network users, be sure to also have a communication plan in place for users of the affected networks. Before the migration is complete, communicate the date, time, and effects of the migration to the users who are affected, along with why the migration is being done. For a network that is being migrated, recommend that users save the information they want to keep, such as private message data, notes, and files, before the migration start date, because they'll no longer have access to their content or information after the migration.
    
- Inform the parent network users that new users are joining.
    
## Perform the network migration
<a name="self-service"> </a>

The network migration has three steps that you will be guided through. Multiple network migrations can be started back-to-back, without waiting for the previous ones to finish. Start from the parent network (the network into which you want to migrate the other network):
  
1. In the parent Yammer network, go to **Settings** > **Network Admin**. 
    
2. Choose **Network Migration**. 
    ![Screenshot of the Network Migration menu item for Yammer Admins](/Office365/Admin/media/f9ae9328-9cb2-46f7-9bce-26bcdc29b3fa.png)
  
    You start on the page with the title **Step 1 of 3 - Check/Add Verified Domains**. This page lists the verified domains that have already been added to the Office 365 tenant for this Yammer network. If you don't see the network you want, follow the link to Office 365 to [add additional verified domains](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611), and then return to this page.
    ![Screen shot of Step 1 of 3 - Check/Add Verified Domains before migrating a Yammer network](/Office365/Admin/media/cac649d6-9245-4645-8f59-fb27dffd87e8.png)
  
3. When you have added all of the verified domains you want, choose **Next**. 
    
    You are now on the **Step 2 of 3 - Choose a Yammer Network to Migrate** page. This page lists all the networks that are eligible for migration. Remember, all of the domains of a Yammer network that you want to migrate must be added as verified domains on Office 365. Only the verified domains for Yammer networks are listed on the page. If you don't see the network you're looking for, choose the **Previous** button and add the verified domains. 
    ![Screen shot of Step 2 of 3 - Choose a Yammer Network to Migrate](/Office365/Admin/media/3a975838-6d80-4dd1-9b3e-14f157820773.png)
  
4. On the **Step 2 of 3 - Choose a Yammer Network to Migrate** page, select the Yammer network that you want to migrate into this network, and then choose **Next**. 
    
5. You reach the page with title **Step 3 of 3 - Export Data &amp; Start Migration**. This page gives you information about the network you are about to migrate, such as network name and number of messages, so that you can confirm if it is the right network. Note that only  *active*  and  *pending users*  will be migrated. All other content is permanently deleted. It's highly recommended that you first [](../security-and-compliance-topics/manage-yammer-data-compliance.md#ExportData) from the subsidiary network before starting the migration. 
    ![Screen shot of Step 3 of 3 - Export Data &amp; Start Migration](/Office365/Admin/media/8de9e6e7-d172-44bc-808c-ec72f34f09e2.png)
  
6. When you have exported the data you want, and you are ready to begin the migration, choose **Start Migration**. 
    
    A confirmation dialog box appears.
    ![Screen shot of dialog box to Confirm that you want to migrate a Yammer network](/Office365/Admin/media/4b93a2e6-9dc4-409c-99cb-2ab7dc225679.png)
  
7. In the **Are you absolutely sure you want to migrate the network?** box, under **I confirm the network migration of** _Network Name_, enter the name of the network you want to migrate to confirm it, and then choose **Migrate**. 
    
    > [!CAUTION]
    > You cannot stop or reverse the migration. So be very sure that you have exported all of the data that you want and that you have chosen the correct network to migrate before you choose **Migrate**. If you are unsure, choose **Cancel** and go back to export your data or check the network name. > Please note, once you migrate a network, all content and data in the subsidiary network will be lost. Make sure to export any files or documents you wish to keep before initiating the migration. ﻿ 
  
8. On the **Status of network migrations** page, you can view the status for the migration. It lists the domains associated with the networks being migrated, the person who initiated the migration, the start and completed dates and times for the migration, and the status of the migration. You can see details about the network, such as the number of active users, the number of messages, and the external networks. 
    
9. ![Screen shot showing the Status of network migrations - Yammer network migration is running](/Office365/Admin/media/05c6da77-091b-48fc-8d08-4455454d4c87.png)
  
    Note that multiple network migrations can be started back-to-back, without waiting for the previous ones to finish. So, you can start the next migration immediately by going through the wizard again.
    
## Status of network migration
<a name="self-service"> </a>

The network migration process works as shown in the following illustration.
  
![Flowchart showing that first you migrate the domains from the subsidiary Yammer network and decommission the network, and then migrate users and external networks in parallel.](/Office365/Admin/media/00d177ba-3be3-45eb-9341-a00abf7b295c.png)
  
In step 1, the domains from the subsidiary network are migrated and the subsidiary network is decommissioned. Then in step 2, the active and pending users and external networks are migrated in parallel. Even if a subset of users or external networks is not migrated, the migration itself will continue and finish, and more details/errors can be found on the status page.
  
The migration status page can show the following error messages.
  
|**Error message**|**What it means**|
|:-----|:-----|
|Failed to migrate  _source network name_ <br/> |The migration of the subsidiary network did not succeed.  <br/> |
|Failed to migrate  _user email_ <br/> |If one or more users failed to migrate, there will be one or more error messages to that effect. At this point, you can decide to add the user manually to the parent network. Note that the subsidiary network has been migrated at this point.  <br/> |
|Failed to migrate  _external network name_ <br/> |If one or more external networks failed to migrate, there will be one or more error messages to that effect. Note that the subsidiary network has been migrated at this point.  <br/> |
   
To troubleshoot further, contact [Yammer support](https://go.microsoft.com/fwlink/p/?LinkId=512399).
  


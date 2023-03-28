---
title: "Create and manage an external network in Yammer"
f1.keywords:
- NOCSH
ms.author: v-whitfieldd
author: dwhitfield233
manager: dmillerdyson
ms.date: 2/14/2023
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid: 
- MOE150
- MET150
ms.assetid: 04ffd9c0-f004-498f-b058-3ea7da3b7311
description: "Create and manage an external network to collaborate with people outside your company, such as customers, suppliers, and partners."
---

# Create and manage an external network in Yammer

If you have permission, you can create an external Yammer network to collaborate with people outside your company, such as customers, suppliers, and partners. People with external email addresses must be invited into or request access to an external network. When they join the external network, they can only see content posted specifically to that external network. That means they won't have access to your home network.
  
External networks are essentially their own networks: each has its own admin center and has its own admins.

>[!NOTE]
>This feature is not available for Yammer Enterprise networks in the [EU Geo](../manage-security-and-compliance/data-residency.md).
> This feature is not available in Trial versions.
  
## Create an external network

1. Select the Yammer settings icon ![Yammer settings icon.](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then go to **Networks** \> **Create a New Network**.

   ![Settings menu, with permission to create external networks.](../media/76058573-115f-43a3-b073-59ba5d3b28d0.png)
  
   > [!NOTE]
   > You must be a verified Admin to create an external network and your home network must have already existed for at least 30 days. If **Create a New Network** is not visible, it means you're not a verified Yammer admin, or you have not met the minimum age for your home network.
   >
   >To find a home network admin for help setting up an external network, in your browser go to ```**https://yammer.com/***your_network***/admin**``` to find the list of Yammer admins.  
  
2. Fill in the required settings:

    - **Network Image:** Click **Choose File** to select an image to use in the header for your new external network.

    - **Network Name:** Provide a name for your new external network, which will now have its own email address and URL. This name must be unique - no other company can use the same name. The URL will be:

      **https&#58;//www&#46;yammer&#46;com**/*external_network_name*

      with any spaces removed from the network name. You may want to include your company name, such as Contoso Customer Feedback. In this example, the URL would be

      https&#58;//www&#46;yammer&#46;com/contosocustomerfeedback

    - **Network Description:** A clear and succinct description ensures users understand the basic purpose of this network.

    - **Add a Network Image:** Upload a thumbnail image or logo that represents the new network.

    - **Permissions:** Select whether membership is **Open** (where all members can invite new members) or **Closed** (where only admins can invite new members). You can also select whether or not members of your company's home network can join without an invitation.

    - **Allow members to join without an invite:** When you select this, users can join without an invite. When you clear this checkbox, users in your home network must request approval before joining this external network.

    - **Best Practice: Setting Permissions to Closed and Invite Required recommended for most secure use.**

3. Click **Create Network**.

   The top bar of your network shows that you're now in the external network. The settings icon for the external network ![Settings icon for an external network.](../media/e1f84edf-4842-4732-89b2-f7e46e4c94e1.png) has a blue circle in it.

   ![Top navigation for an external Yammer network.](../media/ea784fcd-2b12-4b4e-b9f7-20b8726b7a3b.png)
  
   The **All Network** group is automatically created. This group can't be deleted. Users can create additional groups.

4. To start inviting people to join your external network, click the external network settings icon ![Settings icon for an external network.](../media/e1f84edf-4842-4732-89b2-f7e46e4c94e1.png), and then click **Invite**.

   > [!NOTE]
   > You can now invite EU users to participate in external networks hosted in the US. If an EU-based organization had previously used a network in the US geo, it is possible that a subset of users were active members in external networks before their network moved to the EU geo. If a previously active user profile already exists, it will be marked as "deleted" without deleting the content in those external networks when the user is reinvited to access external networks using a new profile.  For more information, see [Cross-geo external collaboration support on Yammer External Networks for the EU](https://techcommunity.microsoft.com/t5/yammer-blog/cross-geo-external-collaboration-support-on-yammer-external/ba-p/3056462).
  
## Go to and from an external network

To get to an external network from your home network, click the Yammer settings icon ![Yammer settings icon.](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then near the bottom of the settings list, select the external network, or select **Browse External Networks**.
  
For example, if you select Contoso Customer Feedback in the first screenshot, you'll go to a new Yammer site for the Contoso Customer Feedback external network. The settings icon will have a blue dot to indicate you're in an external network. The URL will change to show the external network name. For example for the Contoso Customer Feedback external group, the URL is
https&#58;//yammer&#46;com/ContosoCustomerFeedback.

![Settings menu for an external network.](../media/1338f356-0650-477c-a1fd-653d15753fca.png)
  
To get back to your home network, click the home network name at the end of the settings list.
  
![Select the home network in the networks section of the Settings menu.](../media/6cd65fb1-18d9-4e1c-8afa-c3a99e47844f.png)

> [!TIP]
> Email notification settings that each user set for the home network don't apply to the new external network. Users must set email notifications for each external network. For more information, see [Yammer email and push notifications](https://support.office.com/article/93e530e0-189f-4768-8f28-7683d48cc996).  

## Manage settings for an external network that you are an admin for

1. To go to your external network, click the Yammer settings icon ![Yammer settings icon.](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then select an external network, or select **Browse External Networks**.

   ![Settings menu for an external network.](../media/1338f356-0650-477c-a1fd-653d15753fca.png)
  
2. In your external network, click the external network settings icon ![Settings icon for an external network.](../media/e1f84edf-4842-4732-89b2-f7e46e4c94e1.png).

   Select **Network Admin** to configure and design your external network. For information on these settings, see [Configure your Yammer network](../configure-your-yammer-network/configure-yammer.md).

   ![Admin menu for an external network.](../media/afc2fe6a-f41d-4dc6-bce5-c59595997bcc.png)
  
   > [!NOTE]
   > Not all settings are available for external networks: you can't create another external network from an existing external network, invite guests, or monitor a person's account activity. End users who create an external network have fewer configuration options. End users can modify the **Configuration**, **Design**, and **Usage Policy** settings, as well as create additional admins and manage users. They can't bulk update users or change anything in the **Content and Security** section.

   > [!NOTE]
   > Networks Admins note that the "Require admin approval for members to join other companies' external groups or external networks" setting is **OFF** by default. Turn this setting **ON** to review and select whether or not members of your home network can participate in external networks hosted by other organizations. You can review pending requests under **Pending Requests** options under **Edit** settings in your home network.

   ![Pending tasks](../media/yammer-contoso-demo.png)
  
## Delete an external network

> [!CAUTION]
> Deleting an external network deletes all content in the external network and removes all members from the network. Once a network is deleted, it can't be reactivated.
  
1. To go to an external network, click the Yammer settings icon![Yammer settings icon.](../media/9704ce70-56ce-43f7-96c6-f253b0413d40.png), and then select an external network, or select **Browse External Networks**.

   ![Settings menu for an external network.](../media/1338f356-0650-477c-a1fd-653d15753fca.png)
  
2. In the external network, click the external network settings icon ![Settings icon for an external network.](../media/e1f84edf-4842-4732-89b2-f7e46e4c94e1.png).

3. Go to **Network Admin** \> **Configuration**.

4. At the bottom of the page, click **Delete External Network**, and then on the confirmation page, click **Delete**.

When the Microsoft 365 tenant is deleted, all disabled external networks and content are deleted. For more information,see [What happens to my data and access when my Microsoft 365 for business subscription ends?](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires).

## Related articles

[Manage Yammer security settings](../manage-security-and-compliance/yammer-security-settings.md)

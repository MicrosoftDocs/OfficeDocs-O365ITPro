---
title: "Manage your external network profile"
f1.keywords:
- NOCSH
ms.author: pamgreen
author: Starshine89
manager: pamgreen
ms.date: 5/10/2023
audience: Admin
ms.topic: article
ms.service: yammer
ms.localizationpriority: medium
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 9e8cd010-829a-4d11-8a57-a8f735407604
description: "Members of an external network can manage their personal information."
---

# Manage your external network profile
Each Microsoft Viva Engage external network is separate from the user's home network. 
Users in an external network are responsible for managing their profiles and the amount of information they provide.  

> [!IMPORTANT] 
> Your profile is visible to all other participants within the external network. Additionally, profile information is shared between your external and home network accounts.   
By participating in an external network, you agree to share this information about yourself
with other participants in the external network. Be aware that profile information may also be 
visible in other areas of Viva Engage or through the Yammer REST API. 

## Update your user profile
To change your profile, you must sign-in to the external network.
After you sign in, the **Settings** icon contains a blue dot. 

>:::image type="content" source="media/ext-network-toolbar.png" alt-text="Check the settings icon in your external network for a blue dot.":::

1. Select **Settings** > **Edit Settings**.
 
2. Under **Profile**, make the changes you need to your information.

:::image type="content" source="media/ext-network-account-profile.png" alt-text="Locate profile settings in a tab under Account settings.":::

  All information on this tab is visible to others in the network. 
  Any changes you make here carry over to your home network profile.

3. Select **Save**.

  If you're unable to modify or save changes to your profile, your home tenant admin has disabled this feature.

> [!NOTE] 
> Viva Engage obfuscates the name in an email address with asterisks (***) but not the domain, which remains visible to others in the external network. APIs in the external network may not perform the same obfuscation.

## Leave the external network
You can leave a Viva Engage external network at any time and for any reason.

1.	After logging in to the external network, select **Settings** > **Edit Settings**.

  :::image type="content" source="media/ext-network-settings.png" alt-text="Locate Network settings in a tab under Account settings.":::
  

2. Under Networks, select the **Leave Network** option for the external network you want to leave.  

  :::image type="content" source="media/ext-network-leave.png" alt-text="The Networks tab lists all networks you're a member of.":::

### What happens after I leave the external network
When you leave an external network, the network retains all of your posts along with your display name.  

To have these posts removed by the admin, review [Manage data subject requests](https://learn.microsoft.com/en-us/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise).
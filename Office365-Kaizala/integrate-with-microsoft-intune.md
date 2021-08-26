---
title: Kaizala integration with Microsoft Intune
f1.keywords:
- NOCSH
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 8/21/2018
audience: Admin
ms.topic: article
ms.service: kaizala
ms.custom: Kaizala
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d6215c0e-6c52-440f-9ae1-324f1a452182
description: Learn how to protect your organization's Kaizala data by using Microsoft Intune.
---

# Kaizala integration with Microsoft Intune

Microsoft Intune has now been integrated into Kaizala. You can now use it to protect your organization's Kaizala data. With Intune, you can:
  
- Manage the mobile devices your workforce uses, to access organization data.
    
- Manage the mobile apps your workforce uses.
    
- Protect your organization's information by helping in controlling the way your workforce accesses and shares it.
    
- Ensure devices and apps are compliant with organization's security requirements.
    
Check out more info about [Intune](/mem/intune/fundamentals/what-is-intune).
  
## Turn on Intune for Kaizala

To turn on Intune for Kaizala, you'll have to perform steps in the Azure active directory center and in the Kaizala admin center. You'll need to be a global admin to perform the following tasks:
  
1. Log in to the Azure Management Portal.
    
2. From the left navigation bar, go to **Intune App protection**.
    
3. In the list of apps, select **Microsoft Kaizala**.
    
4. In **User groups**, add the groups that you want the policy to be applied on.
    
5. In **Policies**, add the policies and operating system settings that you want to apply. Select **OK**.
    
Now go to the Kaizala app.
  
1. Go to **Profile** \> **Linked accounts** \> **Work Account**, and sign in with your Azure Active Directory account(Azure AD).
    
2. Once you're logged in the app with your Azure AD, you should see the policies getting applied on Kaizala.

---
title: "Set up multi-factor authentication for Office 365 users"
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- 'O365E_AdmSetSecPrivMFA'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: "Learn how to set up multi-factor authentication for Office 365 users and manage the user settings. "
monikerRange: 'o365-worldwide'
---

# Set up multi-factor authentication
  
This article describes how to set up multi-factor authentication (MFA) for Office 365 users. For more information about MFA, see [How Azure multi-factor authentication works](https://go.microsoft.com/fwlink/p/?LinkId=627437).
  
You get a free version of Azure multi-factor authentication as part of your Office 365 for business subscription. For a list of features included in your version of Office 365, see [How to get Azure Multi-Factor Authentication](https://docs.microsoft.com/en-us/azure/multi-factor-authentication/multi-factor-authentication-versions-plans).

> [!NOTE]
> You must be an Office 365 global admin to set up or modify multi-factor authentication.
  
## Enable multi-factor authentication for your organization

All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL). This means that app passwords aren't required for Office 2016 clients. However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.

1. To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), turn on the new admin center by selecting **Try the new admin center** toggle located at the top of the Home page.

2. Select **Settings** \> **Services & add-ins** and then choose **Modern authentication** from the list.

3. Check the **Enable modern authentication** box in the **Modern authentication** panel. 

    ![Modern authentication panel with enable checkbox checked.](../media/enablemodernauth.png)
    
> [!IMPORTANT]
> As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have Modern Authentication enabled by default. Pre-existing tenants won't have a change in their default MA state. To check your MA status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials. Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride. If -ClientADALAuthOverride is 'Allowed', your Modern Authentication is on.
To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).
In SharePoint online, by default, modern authentication is enabled.


## Set up multi-factor authentication

> [!NOTE]
> If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.


1. In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), turn on the new admin center by selecting the **Try the new admin center** toggle located at the top of the Home page.

2. In the left navigation pane, select **Setup**.

3. Under **Setup** > **Turn on multi-factor authentication (MFA)**, select **View**. 

4. On the **Turn on multi-factor authentication (MFA)** page, select **Get started**.

5. Select the **Require multi-factor authentication** and **Require users to register for multi-factor authentication and block access if risk is detected** check boxes.

6. Under **Do you want to exclude anyone from these policies**, select any users that you want to exclude from the drop-down list box.

7. Select **Create policy**. You will return to the **Turn on multi-factor authentication (MFA)** page, which will now say **Completed**. 

After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices. For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).

### Manage MFA settings 

1. In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), turn on the new admin center by selecting **Try the new admin center** toggle located at the top of the Home page.

2. In the left navigation pane, select **Setup**.

3. Under **Turn on multi-factor authentication (MFA)**, it will say **Completed**. Select **View**.

4. On the **Turn on multi-factor authentication (MFA)** page, select **Manage**.

5. The **Azure portal Conditional Access - Policies** page will appear. To turn multi-factor authentication on or off:

    1. Select **Baseline policy: End user protection (Preview)**, and turn the **Enable** toggle on or off.

    2. Select **Baseline policy: Require MFA for admins (Preview)**, and turn the **Enable** toggle on or off.

    > [!NOTE]
    > To exclude users from a policy, select **specific users excluded** > **Select excluded users**, select the users from the list, and then choose **Select**.


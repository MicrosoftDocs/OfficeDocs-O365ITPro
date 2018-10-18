---
title: Enable or disable Kaizala Pro for your organization
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: Admin
ms.date: 10/18/2018
ms.topic: article
ms.service: Kaizala
ms.custom: Kaizala
ms.reviewer: nitinjms2
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: 
description: Learn how to enable and disable the Kaizala app in the Kaizala management portal.
---

# Enable or disable Kaizala Pro for your organization 

Microsoft Kaizala Pro is now commercially [available in 28 countries](regional-availability.md). If your organization is in one of these 28 countries, Kaizala Pro is enabled by default for your organization. For all organizations that are not in one of these countries, Kaizala Pro is disabled by default. The Office 365 administrator can choose to enable or disable Kaizala regardless of the default state. 

The Office 365 administrator can control whether the members of their organization can use Office 365 to log in to the Kaizala Pro app and the Kaizala management portal. 

Enabling Kaizala Pro allows your organization users to:
- Log in to the Kaizala Pro app to search for other employees from AAD and access groups with enhanced security.
- Log in to the Kaizala management portal to access reports, create actions, and create connectors.
 
## To enable or disable Kaizala Pro

1. From the [Kaizala management portal](https://manage.kaiza.la/), sign in to your Office 365 account, and then go to the **Settings** page to view the current state and to modify the settings if needed. 
2. Skip the prompt to add phone number (when no phone numbers are mapped already) by closing the pop up window.
![Prompt to add phone number in Kaizala management portal](media/prompt-to-add-phone-number.png)
> [!NOTE]
> Only the Office 365 administrator can enable or disable Kaizala Pro. 

3. In the **Microsoft Kaizala for your Organization** section, use the **Disable** button to provide confirmation on the pop-up window and disable Kaizala Pro for their account. 
![Enable or disable Kaizala from the Settings page in Kaizala management portal](media/enable-disable-kaizala-from-settings-page.png)

When Kaizala Pro is disabled, the user will see one of the messages in the following table based on who attempted to sign in (Office 365 admin or others), where the sign in was attempted (portal or app), and why Kaizala was disabled (explicitly Office 365 admin action or by default).

### Disabled explicitly by admin

|End point  |Office 365 admin |Other admin  |
|-----------|-------------|------------------|
|Management portal     |Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)    |
|App     |Login with work account is disabled for your organization. Enable using the Kaizala management portal. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)    |

### Disabled by default (not part of commercially available countries)

|End point  |Office 365 admin |Other admin  |
|-----------|-------------|------------------|
|Management portal     |Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)    |
|App     |Login with work account is disabled for your organization. Enable using the Kaizala management portal. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)  |

Once disabled, users in the organization will no longer be able to sign in using Office 365 on the Kaizala Pro app or the Kaizala management portal. All users who are already signed in will be signed out automatically. Users can continue to use the Kaizala Pro app for their personal use without logging in using their work account.


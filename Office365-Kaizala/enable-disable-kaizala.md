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

Microsoft Kaizala Pro is now commercially [available in 28 countries](regional-availability.md). If your organization is in one of these 28 countries, Kaizala Pro is enabled by default for your organization. For organizations that are not in one of these countries, Kaizala Pro is disabled by default. The Office 365 administrator can choose to enable or disable Kaizala Pro regardless of the default state. 

The Office 365 administrator can control whether the members of their organization can use Office 365 to log in to the Kaizala app and the Kaizala management portal. 

Enabling Kaizala Pro allows your organization users to:
- Log in to the Kaizala app to search for other employees from AAD and access groups with enhanced security.
- Log in to the Kaizala management portal to access reports, create actions, and create connectors etc.
 
## To enable or disable Kaizala Pro

1. In the [Kaizala management portal](https://manage.kaiza.la/), sign in using Office 365 account, and then go to the **Settings** page to view whether Kaizala Pro is in enabled or disabled state and to modify the state if needed. 
2. Skip the prompt to add phone number (when no phone numbers are mapped already) by closing the pop up window.
![Prompt to add phone number in Kaizala management portal](media/prompt-to-add-phone-number.png)

3. The **Microsoft Kaizala for your Organization** section, provides option to toggle the current setting. Click on the **Disable** button and provide confirmation on the pop-up window to disable Kaizala Pro for the account. Procedure is same for enabling Kaizala pro as well.
![Enable or disable Kaizala from the Settings page in Kaizala management portal](media/enable-disable-kaizala-from-settings-page.png)
> [!NOTE]
> Only the Office 365 administrator can enable or disable Kaizala Pro. 

When Kaizala Pro is disabled, the users will see one of the messages in the following table based on who attempted to sign in (Office 365 admin or others), where the sign in was attempted (portal or app), and why Kaizala was disabled (explicitly Office 365 admin action or by default).

### Disabled explicitly by admin

|End point  |Office 365 admin |Others  |
|-----------|-------------|------------------|
|Management portal     |Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)    |
|App     |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)    |

### Disabled by default (not part of commercially available countries)

|End point  |Office 365 admin |Others  |
|-----------|-------------|------------------|
|Management portal     |Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)    |
|App     |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md)  |

Once disabled, users in the organization will no longer be able to sign in using Office 365 on the Kaizala app or the Kaizala management portal. However, users can continue to use the Kaizala app for their personal use (without a work account sign in).


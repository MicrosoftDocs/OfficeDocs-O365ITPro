---
title: Enable or disable Kaizala Pro for your organization
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: Admin
ms.date: 10/30/2018
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

Microsoft Kaizala Pro is now commercially [available in 28 countries](regional-availability.md). If your organization is in one of these 28 countries, Kaizala Pro is enabled by default for your organization. For all organizations that are not in one of these countries, Kaizala Pro is disabled by default. The Office 365 administrator can choose to enable or disable Kaizala Pro regardless of the default state. 

The Office 365 administrator can control whether the members of their organization can use Office 365 to log in to the Kaizala app and the Kaizala management portal. 

Enabling Kaizala Pro allows your organization users to:
- Log in to the Kaizala app to search for other employees from AAD and access groups with enhanced security.
- Log in to the Kaizala management portal to access reports, create actions, create connectors, and so on.
 
## To enable or disable Kaizala Pro

1. In the [Kaizala management portal](https://manage.kaiza.la/), sign in using your Office 365 account, and then go to the **Settings** page to view whether Kaizala Pro is in an enabled or disabled state and to modify the state if needed. 
2. Skip the prompt to add phone number (when no phone numbers are mapped already) by closing the pop up window.
![Prompt to add phone number in Kaizala management portal](media/prompt-to-add-phone-number.png)
3. The **Microsoft Kaizala for your Organization** section provides an option to toggle the current setting. Select the **Disable** button and provide confirmation on the pop-up window to disable Kaizala Pro for the account. Use the same procedure to enable Kaizala Pro. 
![Enable or disable Kaizala from the Settings page in Kaizala management portal](media/enable-disable-kaizala-from-settings-page.png)
> [!NOTE]
> Only the Office 365 administrator can enable or disable Kaizala Pro.

When Kaizala Pro is disabled, users will see the following messages.


|Column1  |Column2  |Column3  |
|---------|---------|---------|
|Management portal          |Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)         |![Message in the Office 365 admin center that Kaizala is disabled](media/disabled-message-tenant-admin-portal.png)         |
|Row2     |         |         |
|Row3     |         |         |
|Row4     |         |         |



|End point  |Office 365 admin |Message   |
|-----------|-----------------|----------|
|Management portal     |Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md) |![Message in the Office 365 admin center that Kaizala is disabled](media/disabled-message-tenant-admin-portal.png)    |
|App     |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md) |![Message on a user's device that Kaizala is disabled](media/disabled-message-users-app.jpg)    |
<br>
|End point  |Other users     |Message   |
|-----------|-----------------|----------|
|Management portal     |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md) |![Message in the Office 365 admin center that Kaizala is disabled](media/disabled-message-other-admins-portal.png)     |
|App     |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro. [Learn more](kaizala-management-portal.md) |![Message on a user's device that Kaizala is disabled](media/disabled-message-users-app.jpg)     |

Once disabled, users in the organization will no longer be able to sign in using Office 365 on the Kaizala app or the Kaizala management portal. However, users can continue to use the Kaizala app for their personal use (without signing in to their work account).


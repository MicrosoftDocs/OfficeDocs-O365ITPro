---
title: Enable or disable Kaizala Pro for your organization
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: Admin
ms.date: 04/05/2019
ms.topic: article
ms.service: Kaizala
ms.custom: Kaizala
ms.reviewer: ramarut
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

Microsoft Kaizala Pro is currently [available in 28 countries](regional-availability.md). Beginning in May 2019, Kaizala Pro will be available internationally, with the exception of Cuba, Iran, North Korea, People's Republic of China, Sudan, Syria, Region of Crimea, and Russia. If Kaizala Pro is available in your area, it’s enabled by default for your organization. For all organizations located somewhere else, Kaizala Pro is disabled by default. In any case, the Office 365 administrator can always enable or disable Kaizala Pro. 

The Office 365 administrator can control whether members of an organization can use Office 365 to log in to the Kaizala app and the Kaizala management portal. 

Enabling Kaizala Pro allows users to:
- Log in to the Kaizala app to search for other employees from Azure Active Directory and access groups with enhanced security.
- Log in to the Kaizala management portal to see reports, set up actions, and create connectors.
 
## To enable or disable Kaizala Pro

1. In the [Kaizala management portal](https://manage.kaiza.la/), sign in using your Office 365 account and go to **Settings**. From here, you can enable and disable Kaizala Pro.
2. Skip the prompt to add a phone number (when no phone numbers are mapped already) by closing the pop-up window.
![Prompt to add phone number in Kaizala management portal](media/prompt-to-add-phone-number.png)
3. The **Microsoft Kaizala for your Organization** section provides an option to toggle the current setting. Select **Disable** or **Enable** and confirm your decision in the pop-up window. 
![Enable or disable Kaizala from the Settings page in Kaizala management portal](media/enable-disable-kaizala-from-settings-page.png)
> [!NOTE]
> Only the Office 365 administrator can enable or disable Kaizala Pro.

When Kaizala Pro is disabled, users will see the following messages.

|End point  |Role |Message  |
|---------|---------|---------|
|Management portal  |Office 365 admin    |![Message - Microsoft Kaizala Pro is disabled for your organization. Enable to allow login with work account.](media/disabled-message-tenant-admin-portal.png)   |
|Management portal  |Other users        |![Message - Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala Pro.](media/disabled-message-other-admins-portal.png)   |
|Mobile app     |All users        |![Message on an app user's device that Kaizala is disabled.](media/disabled-message-users-app.jpg)  <br>(Note: The message displayed varies depending on the app's version.)       |

Once the app is disabled, members of the organization can no longer sign in using Office 365 on the Kaizala app or the Kaizala management portal. However, employees can still use the Kaizala app for their personal use outside of work.


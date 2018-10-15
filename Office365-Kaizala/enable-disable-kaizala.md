---
title: Enable and disable Kaizala
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: Admin
ms.date: 10/15/2018
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

# Enable and disable Kaizala 

Microsoft Kaizala is now commercially [available in 28 countries](regional-availability.md). If your organization is in one of these 28 countries, Kaizala is enabled by default for your organization. For all organizations that are not on of these countries, Kaizala is disabled by default. The Office 365 administrator can choose to enable or disable Kaizala regardless of the default state. 

The Office 365 administrator can control whether the members of their organization can use Office 365 to log in to the Kaizala app. 

Enabling Kaizala allows your organization users to:
- Log in to the Kaizala app to search for other employees from AAD and access groups with enhanced security.
- Access reports, create actions, and create connectors from the Kaizala management portal.
 
## To enable or disable Kaizala

1. From the Kaizala management portal, go to the **Settings** page to view the current state and to modify the settings if needed. 
2. When prompted (when no phone numbers are mapped already), enter a phone number. This step can be skipped by closing the pop-up window.
![Prompt to add phone number in Kaizala management portal](media/prompt-to-add-phone-number.png)
3. In the **Microsoft Kaizala for your Organzation** section, use the **Disable** button to provide confirmation on the pop-up window and disable Kaizala for their account. 
![Enable or disable Kaizala from the Settings page in Kaizala management portal](media/enable-disable-kaizala-from-settings-page.png)

When Kaizala is disabled, the user will see one of the messages in the following table based on who attempted to sign in (tenant admin or others), where the sign in was attempted (portal or app), and why Kaizala was disabled (explicitly tenant admin action or by default).

### Disabled explicitly by admin

|End point  |Tenant admin |Non-tenant admin  |
|-----------|-------------|------------------|
|Management portal     |Microsoft Kaizala is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala. [Learn more](kaizala-management-portal.md)    |
|App     |Login with work account is disabled for your organization. Enable using the Kaizala management portal. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala. [Learn more](kaizala-management-portal.md)    |

### Disabled by default (not part of commercially available countries)

|End point  |Tenant admin |Non-tenant admin  |
|-----------|-------------|------------------|
|Management portal     |Microsoft Kaizala is disabled for your organization. Enable to allow login with work account. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala. [Learn more](kaizala-management-portal.md)    |
|App     |Login with work account is disabled for your organization. Enable using the Kaizala management portal. [Learn more](kaizala-management-portal.md)   |Login with work account is disabled for your organization. Contact your Office 365 administrator to enable Kaizala. [Learn more](kaizala-management-portal.md)  |

Once disabled, users in the organization will no longer be able to sign in using Office 365 on the Kaizala app or the management portal. All users who are already signed in will be signed out automatically. 


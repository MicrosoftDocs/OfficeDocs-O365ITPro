---
title: "Manage email app access in Office 365 admin center"
ms.author: kwekua
author: kwekua
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365E_AdminSettingsEmailApp
O365M_AdminSettingsEmailApp'
ms.service: o365-administration
localization_priority: Normal
ms.custom: Core_O365Admin_Migration
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: "Learn how to choose which mobile apps people can use to access email, calendar, and contacts."
---

# Manage email app access in the admin center

Use the mobile email access settings to choose which mobile apps people in your organization can use to access their work or school account to access email, calendar and contacts.
  
> [!IMPORTANT]
> Your organization will have access to this setting unless you're using Microsoft Intune or you've configured mobile device management settings in the Exchange admin center. 
  
## Manage email app options

> [!IMPORTANT]
>  If you don't use this feature, there'll be no changes to your users' experience. They'll be able to use any mobile email app to access their work or school account for email, calendar, and contacts from their mobile device. 
  
1. Sign in to Office 365 with your work or school account. 
    
2. Click **Admin** to go to the admin center. 
    
3. Navigate to **Settings** \> **Services &amp; add-ins**.
    
    ![Click Settings, then click Services and add-ins](../media/192267c1-84ac-492c-aeba-7e653c7991db.png)
  
4. Turn the toggle **On** to manage email app access options. 
    
    ![Mobile email access settings](../media/f031a555-32ee-43ff-a772-aa561781473b.png)
  
Choose how users in your organization use email apps on their devices:
  
Choose the option to set how users in your organization access their Office 365 work or school account from their mobile devices
  
- **Outlook only** - users in your organization will be required to use the Outlook for Android or Outlook for iOS app on their mobile device. 
    
- **Any email app** - all users in your organization will be prompted to use the Outlook for Android or Outlook for iOS app on their mobile device, but they can choose to use any email app. 
    
- **Any email app** - new users or devices in your organization will be prompted once to use the Outlook for Android or Outlook for iOS app on their mobile device, but they can choose to use any email app. 
    
For more details, check out [Options for accessing email from your mobile device](access-email-from-a-mobile-device.md).
  
## New user or device is activated in your organization

As soon as a user in your organization adds their work or school email to a third-party email app or to a new device, they'll receive an email from **Microsoft on behalf of your organization**. The email will let them know about the benefits of using the Outlook mobile app and provide a link to the download location. Your users can then choose whether to continue using the third-party app or choose to use the Outlook mobile app. During the 24 hours after the user first receives this email, their device will be in quarantine, and email, calendar, and contact data won't be updated. If they choose to use the Outlook mobile app, the third-party app will remain quarantined and data will only sync with the Outlook mobile app. If they decide to continue using the third-party app, data will start to sync instantly. If no action is taken during those first 24 hours, the email will be removed from their inbox and data will start to sync from the server automatically.
  
## Previously configured users in your organization

If you decide to recommend Outlook to everyone in your organization, in addition to the experience described above for new users, users who have previously connected their work or school email account to a third-party app will receive an email from **Microsoft on behalf of your organization** within 48 hours of this setting being enabled. The email will let them know about the benefits of using the Outlook mobile app and provide a link to the download location. Your users can then choose whether to continue using the third-party app or choose to use the Outlook mobile app. During the 24 hours after the user first receives this email, their device will be in quarantine, and email, calendar, and contact data won't be updated. If they choose to use the Outlook mobile app, the third-party app will remain quarantined and data will only sync with the Outlook mobile app. If they decide to continue using the third-party app, data will start to sync instantly. If no action is taken during those first 24 hours, the email will be removed from their inbox and data will start to sync from the server automatically. 
  


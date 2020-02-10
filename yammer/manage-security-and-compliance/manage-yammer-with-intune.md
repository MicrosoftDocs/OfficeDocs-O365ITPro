---
title: "Manage Yammer with Microsoft Intune"
f1.keywords:
- NOCSH
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: conceptual
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 76f5c4c9-6a4e-43d1-87dc-2848a90686be
description: "Subscribe to Microsoft Intune to add mobile application management to Yammer"
---

# Manage Yammer with Microsoft Intune

When you subscribe to [Microsoft Intune](https://go.microsoft.com/fwlink/p/?LinkId=817224), you can use mobile application management (MAM) with Yammer along with other apps. MAM allows you to manage and protect data in an app on a device even if it is not enrolled in mobile device management (MDM).
  
## Manage Yammer with MAM

Microsoft Intune provides mobile application management (MAM) capabilities for Yammer, Outlook, and other Office mobile apps for iOS and Android. 
  
This feature is especially helpful for organizations where devices and apps are used for both work and personal use and the device is not enrolled in MDM. When using Yammer with Intune, you can set up policies that apply to the Yammer app on Android and iOS devices to help protect your corporate data. For example, you can do the following:
  
|**Intune policy you can enforce on the app**|**Available for Android?**|**Available for iOS?**|
|:-----|:-----|:-----|
|Allow apps to transfer data to other apps.  <br/> |Yes  <br/> |Yes  <br/> |
|Allow apps to receive data from other apps.  <br/> |Yes  <br/> |Yes  <br/> |
|Prevent "Save As".  <br/> |Yes  <br/> |Yes  <br/> |
|Prevent iTunes and iCloud backups.  <br/> |No  <br/> |Yes  <br/> |
|Prevent Android backups.  <br/> |Yes  <br/> |No  <br/> |
|Restrict cut, copy, and paste with other apps.  <br/> |Yes  <br/> |Yes  <br/> |
|Restrict web content to display in the Intune Managed Browser.  <br/> |Yes  <br/> |Yes  <br/> |
|Encrypt app data.  <br/> |Yes  <br/> |Yes  <br/> |
|Disable contacts sync.  <br/> |Yes  <br/> |Yes  <br/> |
|Require PIN for access, and set specific requirements such as PIN length and number of allowed tries.  <br/> |Yes  <br/> |Yes  <br/> |
|Allow use of fingerprint instead of PIN.  <br/> |Yes  <br/> |Yes  <br/> |
|Require corporate credentials for access.  <br/> |Yes  <br/> |Yes  <br/> |
|Block managed apps from running on jailbroken or rooted devices.  <br/> |Yes  <br/> |Yes  <br/> |
|The frequency of how often the access requirements are checked.  <br/> |Yes  <br/> |Yes  <br/> |
|Block screen capture and Android Assistant.  <br/> |Yes  <br/> |No  <br/> |
|When a device with the Yammer app is retired or un-enrolled, all of the application's corporate data will be deleted.  <br/> |Yes  <br/> |Yes  <br/> |
   
> [!NOTE]
> Intune MAM policies will be enforced when users authenticate to Yammer through Office 365 (Azure Active Directory) accounts and sign-in. They are not enforced when users authenticate to Yammer with Yammer-specific passwords or Yammer temporary passwords. 
  
For more information about using Intune for mobile application management, see:
  
- [What is Intune?](https://go.microsoft.com/fwlink/p/?LinkId=817226)
    
- [Supported operating systems and browsers](https://go.microsoft.com/fwlink/p/?LinkId=817230)
    
- [What are app data protection policies?](https://go.microsoft.com/fwlink/p/?LinkId=823757)
    
- [How to create and assign app protection policies](https://go.microsoft.com/fwlink/p/?LinkId=817225)
    


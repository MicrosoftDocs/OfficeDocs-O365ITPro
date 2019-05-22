---
title: "Phasing out temporary mobile passwords in Yammer"
ms.author: v-irpast
author: IrenePasternack
manager: pamgreen
ms.date: 6/30/2017
audience: Admin
ms.topic: conceptual
ms.service: yammer
localization_priority: Normal
search.appverid: 
- MET150
- MED150
ms.assetid: ed49e255-4e20-484d-a5da-96bd3bd24012
description: "Support is ending for temporary mobile passwords. Learn how you can transition to AAD Conditional Acess to continue with similar functionality. "
---

# Phasing out temporary mobile passwords in Yammer

Temporary Mobile Passwords have been a useful workaround for situations where users needed to use Yammer mobile applications, even if the identity provider is blocked for devices connecting from the internet. With the recent end of support for Yammer SSO, and all Yammer federated authentication having been moved to use Azure Active Directory (AAD), the time has come to also end support for this workaround, and instead rely on [AAD Conditional Access](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal) (CA) as a solution. 
  
AAD CA is a much better solution than Yammer Temporary Mobile Passwords because it does not require users to manage two separate passwords for Yammer authentication. With AAD CA, customers can enable the same access control scenario, while also giving users a better authentication experience that works consistently across all their devices.
  
## Removal schedule for Temporary Mobile Passwords

Temporary Mobile Passwords will be phased out based on the schedule below. Yammer networks that currently use TMPs will need to transition to using AAD CA to limit their authentication to work only on the intranet in general, with the exception of allowing Yammer mobile app authentication from the Internet.
  
Important dates:
  
- **June 29th, 2017:** End of support for Temporary Mobile Passwords announced. New networks will no longer have this functionality. 
    
- **July 3rd, 2017:** Yammer networks with minimal usage (fewer than 30 logins a month) will have Temporary Mobile Passwords disabled. If your network falls into this category, and you require an extension - please follow your tenant's normal process to open an Office 365 support request and Support can provide you with a temporary extension. 
    
- **April 3rd, 2018:** Temporary Mobile Passwords will no longer function. 
    
 **After April 3rd, 2018**, if you do nothing, the following changes will take place: 
  
- Temporary Mobile Passwords will be removed from the Yammer interface &amp; blocked from the authentication path.
    
## Yammer Temporary Mobile Password scenarios and their replacement

If you are currently using Temporary Mobile Passwords for specific scenarios or behaviors, you can transition to new methods to continue with similar functionality. The following table lists these scenarios or behaviors and the replacement for that behavior.
  
|
|
|**Scenario**|**Replacement**|
|**Intranet Only Access.** Admin has blocked federated Yammer authentication from working for devices which connect from the Internet, only allowing authentication on their intranet. Temporary Mobile Passwords ensure users access credentials via the company intranet &amp; allows users to authenticate to the mobile app.  <br/> |**[AAD Conditional Access](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal).** AAD CA allows admins to restrict access to trusted networks and allows users to authenticate via AAD.  <br/> |
|**Password Security on Untrusted Devices.** There's a risk that untrusted devices can be compromised &amp; expose corporate passwords to unauthorized users. Temporary Mobile Passwords offers a way to protect sensitive corporate passwords, by providing ephemeral login credentials that don't provide access to the entire O365 suite.  <br/> |**[AAD Conditional Access with Intune](https://docs.microsoft.com/en-us/intune/conditional-access).** With AAD CA, you can enforce multi-factor authentication--using multi-factor authentication helps protect resources from being accessed by an unauthorized user who might have gained access to the credentials of a valid user.  <br/> |
   
## To immediately disable Temporary Mobile Passwords for your network

Open a support case using the Microsoft 365 admin center and we would be happy to disable Temporary Mobile Passwords for your network.
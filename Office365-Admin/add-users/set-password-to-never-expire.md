---
title: "Set an individual user's password to never expire"
ms.author: dianef
author: dianef77
manager: mnirkhe

ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466

description: "Learn how to set some individual user passwords to never expire, using Windows PowerShell."
---

## Set password expiration policies in Azure AD

A global administrator for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set user passwords not to expire. You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire. 

This guidance applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services. Password expiration is the only part of the policy that can be changed.

> [!NOTE]
> Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire. For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
>

## Set or check the password policies by using PowerShell

To get started, you need to [download and install the Azure AD PowerShell module](https://docs.microsoft.com/powershell/module/Azuread/?view=azureadps-2.0). After you have it installed, you can use the following steps to configure each field.

### Check the expiration policy for a password

1. Connect to Windows PowerShell by using your company administrator credentials.
1. Execute one of the following commands:

   * To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *aprilr@contoso.onmicrosoft.com*) or the user ID of the user you want to check: `Get-AzureADUser -ObjectId <user ID> | Select-Object @{N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}}`
   * To see the **Password never expires** setting for all users, run the following cmdlet: `Get-AzureADUser -All $true | Select-Object UserPrincipalName, @{N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}}`

### Set a password to expire

1. Connect to Windows PowerShell by using your company administrator credentials.
1. Execute one of the following commands:

   * To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user: `Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None`
   * To set the passwords of all users in the organization so that they expire, use the following cmdlet: `Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None`

### Set a password to never expire

1. Connect to Windows PowerShell by using your company administrator credentials.
1. Execute one of the following commands:

   * To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user: `Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration`
   * To set the passwords of all the users in an organization to never expire, run the following cmdlet: `Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration`

   > [!WARNING]
   > Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute. If you set the user passwords to never expire and then 90+ days go by, the passwords expire. Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in. This change can affect a large number of users. 

## Next steps

The following articles provide additional information about password reset through Azure AD:

* [How do I complete a successful rollout of SSPR?](howto-sspr-deployment.md)
* [Reset or change your password](../user-help/active-directory-passwords-update-your-own-password.md).
* [Register for self-service password reset](../user-help/active-directory-passwords-reset-register.md).
* [Do you have a licensing question?](concept-sspr-licensing.md)
* [What data is used by SSPR and what data should you populate for your users?](howto-sspr-authenticationdata.md)
* [What authentication methods are available to users?](concept-sspr-howitworks.md#authentication-methods)
* [What is password writeback and why do I care about it?](howto-sspr-writeback.md)
* [How do I report on activity in SSPR?](howto-sspr-reporting.md)
* [What are all of the options in SSPR and what do they mean?](concept-sspr-howitworks.md)
* [I think something is broken. How do I troubleshoot SSPR?](active-directory-passwords-troubleshoot.md)
* [I have a question that was not covered somewhere else](active-directory-passwords-faq.md)

  


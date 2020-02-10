---
title: "Manage Yammer user licenses in Office 365"
f1.keywords:
- NOCSH
ms.author: v-teflor
author: TeresaFG-writer
manager: pamgreen
ms.date: 9/23/2019
audience: Admin
ms.topic: article
ms.service: yammer
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: 34a67e3a-3fd8-4e54-bffb-dd5ad0e48590
description: "Yammer is moving from a licensing model where the entire Office 365 subscription is licensed as a whole, to a model where you can assign licenses for each user. "
---

# Manage Yammer user licenses in Office 365

When you assign user licenses as part of a bundled Office 365 subscription plan such as Office 365 Enterprise E3, the Yammer license is automatically assigned to the user. You can remove or assign Yammer licenses for specific users in the Microsoft 365 admin center or by using Windows PowerShell cmdlets for Office 365.
  
You can block users who don't have Yammer licenses from accessing Yammer by turning on the security setting **Block Office 365 users without Yammer licenses** (see [Start blocking users who don't have Yammer licenses](manage-yammer-licenses-in-office-365.md#StartBlocking)).
  
You need to be an Office 365 global administrator or user management administrator to do the following operations.
  
Only users with a Yammer license will see a Yammer tile in the Office 365 app launcher. 
  
![Assign licenses section of Microsoft 365 admin center with Yammer Enterprise license available to assign.](../media/33a074a6-6141-4293-89b2-17c0845c7020.png)
  
## Manage Yammer licenses in the Microsoft 365 admin center

You assign or remove the Yammer license to users the same way you assign any other Office 365 Enterprise E3 license.
  
- Sign in to Office 365 Enterprise E3, navigate to the Microsoft 365 admin center, and on the **Users** \> **Active Users** page, assign or remove the Yammer license for users. 
    
See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and [Remove licenses from users in Office 365 for business](https://support.office.com/article/9b497c85-d0a4-4735-80fa-d3565bc05bd1) for more information. 
  
## Manage Yammer licenses by using Windows PowerShell

You can use cmdlets in Windows PowerShell to assign Office 365 licenses. With Windows PowerShell, you can more easily see who has a license, and assign licenses for multiple users at the same time. For more information, see [Use Office 365 PowerShell to assign licenses to user accounts](https://go.microsoft.com/fwlink/?LinkID=613097). You can also bulk update licenses based on a CSV file. For more information, see [Bulk license assignment to Office 365 users based on CSV](https://go.microsoft.com/fwlink/?LinkId=717762).
  
Below are some example Windows PowerShell script snippets that you can use to manage Yammer licenses. Use them to develop a complete script for your organization.
  
- The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.
    
  ```
  Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:YAMMER_ENTERPRISE_STANDALONE"
  ```

- The following example unassigns the Yammer Enterprise license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) to the user belindan@litwareinc.com.
    
  ```
  $UPN = "belindan@litwareinc.com"
  $LicenseDetails = (Get-MsolUser -UserPrincipalName $UPN).Licenses
  ForEach ($License in $LicenseDetails) {
    $DisabledOptions = @()
    $License.ServiceStatus | ForEach {
       If ($_.ProvisioningStatus -eq "Disabled" -or  $_.ServicePlan.ServiceName -like "*YAMMER*") { $DisabledOptions += "$($_.ServicePlan.ServiceName)" } 
    }
    $LicenseOptions = New-MsolLicenseOptions -AccountSkuId $License.AccountSkuId -DisabledPlans $DisabledOptions
     Set-MsolUserLicense -UserPrincipalName $UPN -LicenseOptions $LicenseOptions
  }
  
  ```

- If you'd instead like to enable Yammer for a user without affecting anything else in their license, you can run the above script but change:
    
  ```
  If ($_.ProvisioningStatus -eq "Disabled" -or $_.ServicePlan.ServiceName -like "*YAMMER*") { $DisabledOptions += "$($_.ServicePlan.ServiceName)" }
  ```

    to
    
  ```
  If ($_.ProvisioningStatus -eq "Disabled" -and $_.ServicePlan.ServiceName -notlike "*YAMMER*") { $DisabledOptions += "$($_.ServicePlan.ServiceName)" }
  ```

- The following example returns information about any users who are not currently licensed for Office 365.
    
  ```
  Get-MsolUser -All -UnlicensedUsersOnly
  ```

<a name="StartBlocking"> </a>
## Start blocking users who don't have Yammer licenses

It takes just a few steps to start blocking Office 365 users who don't have Yammer licenses. However, turning this setting on can accidentally disrupt users' access to Yammer. So before you begin, do the following to make sure your Yammer users can continue working smoothly:
  
- **Make sure that you have turned on the setting to enforce Office 365 identity for Yammer users.** You can assign or unassign Yammer licenses only to Yammer users who are managed in Office 365. So, to block Office 365 users without Yammer licenses, it is required that all Yammer users are managed in Office 365. The setting **Block Office 365 users without Yammer licenses** can be turned on only when the [Enforce office 365 identity for Yammer users](../configure-your-yammer-network/enforce-office-365-identity.md) setting is turned on. 
    
- **Make sure all current Yammer users have a Yammer license.** When you start blocking Office 365 users without Yammer licenses, any user without a Yammer license will be unable to access Yammer. So before you begin, make sure that all of your current Yammer users have Yammer licenses. One method to check this is to go to the **Export Users** page in Yammer and export all users. Then compare that list to the list of users in Office 365 and make any changes required. For more details, see the article [How to audit Yammer users in networks connected to Office 365](audit-users-connected-to-office-365.md).
    
- **Tell your users about this change.** We strongly recommend that you tell users that you are starting to block Office 365 users without Yammer licenses, because it can disrupt their day to day usage of Yammer. 
    
You must be a global administrator on Office 365 who was synchronized to Yammer as a verified admin to perform these steps.
  
If you are ready to block users who don't have Yammer licenses, follow these steps.
  
1. In Yammer, go to the **Network Admin** section, and choose **Security Settings**.
    
2. In the Security Settings page, go to the **Enforce Office 365 Identity** section, select the **Enforce Office 365 identity in Yammer** checkbox and confirm the selection. Enforcing Office 365 identity is a pre-requisite step to block users without Yammer licenses. 
    
3. After the **Enforce Office 365 identity in Yammer** checkbox is selected, the **Block Office 365 users without Yammer licenses** checkbox will be available. Select the **Block Office 365 users without Yammer licenses** checkbox and then choose **Save**.
    
    ![Screenshot of Block Office 365 users without Yammer licenses checkbox in Yammer Security Settings](../media/b29af1f2-cc46-42da-88d9-a9c4fc0ab1be.png)
  
4. You see a confirmation message that asks if you are ready to start blocking Office 365 users without Yammer licenses.
    
    ![Screenshot of confirmation dialog box to start blocking users without Yammer licenses](../media/1b6605a6-e84e-4f5f-9f66-78baeac5b50a.png)
  
    The confirmation message shows the number of active users on the Yammer network. Make sure all the current Yammer users have Yammer licenses. For more details, see [How to audit Yammer users in networks connected to Office 365](audit-users-connected-to-office-365.md).
    
    If you want, you can automatically log out all current users, so that you can be sure that everyone using the Yammer service has logged in with their Office 365 identities and have a Yammer license. If you choose to do this, select the **Log out all current users** checkbox. We strongly recommend doing this at a time of minimal user activity (because users might be logged out in the middle of their work) and communicate it to them ahead of time. 
    
5. If you are ready to start blocking Office 365 users without Yammer licenses, select **Yes, I am ready** to confirm your choice. This returns you to the **Security Settings** page where the **Block Office 365 users without Yammer licenses** checkbox is now selected. 
    
6. Choose **Save** to save all your settings on the page. 
    
    If you don't choose **Save** but instead navigate away from the page, your settings will not take effect. 
    
## FAQ
<a name="StartBlocking"> </a>

### Q: Why are Yammer licenses per-user?

A: Per-user licenses let you assign Yammer to a subset of users in your company - typically for a geographical or team-by-team rollout. Only users with a license can see the Yammer tile in the Office 365 app launcher. 
  
### Q: How does this affect Yammer users who sign-in with their email and password?

A: Licenses are enforced only for users who sign-in with Office 365 identity.
  
### Q: What if I do not want anyone in my company to use legacy Yammer identity?

A: You can [Enforce Office 365 identity](../configure-your-yammer-network/enforce-office-365-identity.md) for all your Yammer users. 
  
### Q: How can I tell if all of my Yammer users have accounts in Office 365?

A: You can export your list of users from Yammer and check for users who are not in Office 365. For more information, see [Audit Yammer users in networks connected to Office 365](audit-users-connected-to-office-365.md).
  


---
title: "Manage guest access in Office 365 Groups"
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: "Learn how to add guests to an Office 365 Group, view guest users, and use PowerShell to control guest access."
---

# Manage guest access in Office 365 Groups

By default, guest access for Office 365 groups is turned on for your organization. Admins can control whether to allow guest access to groups for their whole organization or for individual groups.

When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web. Invitations are sent to the group owner for approval.

Once approved, the guest user is added to the directory and the group.

> [!NOTE]
> Office 365 Connected Yammer Groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network. See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions. 
  
## View guest users

You can view the guest users that are currently in your directory by going to the Microsoft 365 admin center.

- In the admin center, go to the **Users** > **Guest users** page.

If you want to edit any of the guest's information, you can do so in the Azure Active Directory portal. See [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) for information.

   
## Add guests to an Office 365 group from the admin center

If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.
  
1. In the admin center, go to the **Groups** > **Groups** page.
  
2. Select the group you want to add the guest to, and select **View all and manage members** on the **Members** tab. 
  
4. Select **Add members**, and choose the name of the guest you want to add.
    
5. Select **Save**.

If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).
  
### Manage groups guest access

If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.

1. In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.

2. Select **Office 365 Groups**.
  
3. On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.

### Block guest users from a specific group

If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.

You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:

- If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.

- If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.

- If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.

> [!NOTE]
> You must have global admin rights to run these commands. 

Run the following script, changing *<GroupName>* to the name of the group where you want to block guest access.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

To verify your settings, run this command:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

The verification looks like this:
    
    ![The verification](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
### Allow/block guest access based on their domain

You can allow or block guest users who are using a specific domain. For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.

For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

### Add guest to the global address list

By default, guests aren't visible in the Exchange Global Address List. Use the steps listed below to make a guest visible in the global address list.

Find the guest user's ObjectID by running:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## Related articles

[Manage Group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md)
  
[Allow/Deny guest access to Office 365 groups based on their domain](https://go.microsoft.com/fwlink/?linkid=854001)
  
[Azure Active Directory access reviews](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
  
[Migrate distribution lists to Office 365 Groups](../manage/upgrade-distribution-lists.md)

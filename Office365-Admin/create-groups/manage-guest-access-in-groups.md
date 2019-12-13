---
title: "Manage guest access in Office 365 Groups"
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


view guest users
add existing guests to a group
add groups to a guest
invite guests to the directory
edit guest information
Add guest to the global address list

Turn on or off guest access to group files and OneNote
Turn on or off the Sharing option

Manage who can add guest users
Allow or block guest users from a specific group
Allow/block guest access based on their domain




By default, guest access is turned on for your organization. When it's turned on, everyone in your organization can add guest users to an Office 365 Group. The guests will have access to all Group features.
  
Admins can control whether to allow guest access to Groups for their whole organization or for individual groups. They can also control who can allow guests to be added to groups.

Office 365 Connected Yammer Groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network. See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions. 
  

- Owners of an Office 365 group and global admins who are owners of the group can add guest users to groups through Outlook on Web.
    
- Sharing a file with a guest from a SharePoint site or an Office 365 group. See [Share group files](https://support.office.com/article/749bc73b-90c9-4760-9b6f-9aa1cf01b403.aspx).
    
- Adding guests to your organization through Azure active directory B2B collaboration. Azure active directory B2B collaboration allows a company administrator to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2000 lines to the B2B collaboration portal. For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?LinkId=826383).

  
## View guest users

- In the admin center, go to the **Users** > **Guest users** page.
 
::: moniker range="o365-worldwide"   
   
## Add existing guests to an Office 365 Group

> [!NOTE]
> If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.

If the guest already exists in your directory (see above), you can add them to your groups from the Microsoft 365 admin center.
  
1. In the admin center, go to the **Groups** > **Groups** page.
  
2. Select the group you want to add the guest to, and select **View all and manage members** on the **Members** tab. 
  
4. Select **Add members**, and choose the name of the guest you want to add.
    
5. Select **Save**.

::: moniker-end

## Invite guests

You can't invite guests from the Office Admin Center or the Exchange Admin Center at this time. To invite guests centrally you might consider using the Azure Active Directory B2B collaboration preview. For more information, see [About the Azure AD B2B collaboration preview](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).
  
## Edit guest information

Currently you can't add or edit guests from the Office Admin Center or the Exchange Admin Center. To edit guest accounts (such as their display name or profile photo) go to your Azure Active Directory portal. For more information, see [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/article/06a189e7-5ec6-4af2-94bf-a22ea225a7a9).
  
## Manage guest access to Office 365 Groups

### Turn on or off guest access to group files and OneNote

By default, guests can access group files and the group OneNote notebook. To turn off guest access, you need to turn off the SharePoint external sharing setting at the organization level. For the steps, see [Turn external sharing on or off for SharePoint Online](https://support.office.com/article/6288296a-b6b7-4ea4-b4ed-c297bf833e30.aspx#ID0EAABAAA=Office_365_Groups), "Manage external sharing for Office 365 Group site collections."
  
However, even if the SharePoint external sharing setting is turned off, the files from SharePoint sites can still be shared with new guest users based on SharePoint settings. To learn more, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85.aspx).
  
### Turn on or off the Sharing option


By default, the Sharing option in your organization is turned on. This option allows guests to be added to your organization. To turn it off:
  
1. In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.


2. Next to **Sharing**, select **Edit**. 
    
3. Set the On / Off toggle for **Let users add new guests to the organization**.
    
  
### Manage who can add guest users


1. In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page. 
    

2. Select **Office 365 Groups**.
  
3. On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.
 
  

### Allow or block guest users from a specific group


You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to enable this preview of sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites:

- If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.

- If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.

- If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.

    


> [!NOTE]
> You must have global admin rights to run these commands. 


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


> [!NOTE]
> If tenant Guest Access settings are set to False, individual groups cannot be set to True.
  
For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)
  
    

### Add guest to the global address list

By default, guests aren't visible in the Exchange Global Address List. Use the steps listed below to make a guest  visible in the global address list.

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

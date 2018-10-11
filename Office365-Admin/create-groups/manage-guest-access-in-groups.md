---
title: "Manage guest access in Office 365 Groups"
ms.author: dianef
author: dianef77
manager: mnirkhe

ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: "Learn how to add guests to an Office 365 Group, view guest users, and use PowerShell to control guest access."
---

# Manage guest access in Office 365 Groups

By default, guest access is turned on for your organization. When it's turned on, everyone in your organization can add guest users to an Office 365 Group. The guests will have access to all Office 365 Group features.
  
Admins can control whether to allow guest access to Office 365 Groups for their whole organization or for individual Office 365 groups. They can also control who can allow guests to be added to groups.
  
## Manage guest access in the admin portal

### View guest users

1. Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Go to **Users** \> **Guest users**.
    
    ![Expand the Users section on the navigation pane to manage your Guest Users](../media/f16dc4a1-94a4-481f-afe1-58f38eb8b15f.png)
  
### Add existing guests to an Office 365 Group

If the guest already exists in your directory (see above) you can add them to your groups from the Office Admin Center or the Exchange Admin Center.
  
1. Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. Go to **Groups** \> **Groups**.
    
    ![Expand the Groups section on the navigation pane to manage your groups](../media/d0666f42-b4f8-45e9-8c0e-b0f7102377e9.png)
  
3. Select the group you want to add the guest to, and choose **Edit** in the **Members** section. 
    
    ![Click Edit to manage your Group's membership](../media/79ffbf84-5f51-48a5-85be-993057a877cb.png)
  
4. Select the name of the guest you want to add.
    
5. Choose **Save**.
    
### Invite guests

You can't invite guests from the Office Admin Center or the Exchange Admin Center at this time. To invite guests centrally you might consider using the Azure Active Directory B2B collaboration preview. For more information, see [About the Azure AD B2B collaboration preview](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).
  
### Edit guest information

Currently you can't add or edit guests from the Office Admin Center or the Exchange Admin Center. To edit guest accounts (such as their display name or profile photo) go to your Azure Active Directory portal. For more information, see [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/article/06a189e7-5ec6-4af2-94bf-a22ea225a7a9).
  
## Manage guest access to Office 365 Groups

### Turn on or off guest access to group files and OneNote

By default, guests can access group files and the group OneNote notebook. To turn off guess access, you need to turn off the SharePoint external sharing setting at the organization level. For the steps, see [Turn external sharing on or off for SharePoint Online](https://support.office.com/article/6288296a-b6b7-4ea4-b4ed-c297bf833e30.aspx#ID0EAABAAA=Office_365_Groups), "Manage external sharing for Office 365 Group site collections."
  
However, even if the SharePoint external sharing setting is turned off, the files from SharePoint sites can still be shared with new guest users based on SharePoint settings. To learn more, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85.aspx).
  
### Turn on or off the Sharing option
<a name="BKMK_Beforeyoubegin"> </a>

By default, the Sharing option in your organization is turned on. This option allows guests to be added to your organization. To turn it off:
  
1. Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. In the navigation menu, choose **Settings** then **Security &amp; privacy**. 
    
3. Set the On / Off toggle for **Allow adding of new guests to my organization**.
    
    ![Allow adding of guest users to my organization](../media/1d757db1-0c19-4028-a190-50fb41994c98.png)
  
### Manage who can add guest users
<a name="BKMK_UsetheadminCtr"> </a>

1. Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).
    
2. In the navigation menu, choose **Settings** then **Services &amp; add-ins**.
    
3. Choose **Office 365 Groups**.
    
    ![Office 365 groups](../media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  
4. On the **Office 365 Groups** page, set the toggle to **On** or **Off**, depending on whether you want to let people outside your organization access Office 365 group resources.
    
    If you turn this toggle on, you'll see another option to control whether you want to let group owners add people outside your organization to Office 365 groups. Set this toggle to **On** if you want to let group owners add guest users. 
    
    ![Let people outside my organization access Office 365 groups and resources](../media/76c1f529-1b0d-4e9d-907a-2def05e602ad.png)
  
## Use PowerShell to control guest access
<a name="bkmk_UsePowerShell"> </a>

### Install the preview version of the Azure Active Directory PowerShell for Graph

 **IMPORTANT**: You cannot install both the preview and GA versions on the same computer at the same time **.**
  
As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one. 
  
1. Open Windows PowerShell as an administrator:
    
    The Windows PowerShell window will pop open. The prompt C:\Windows\system32 means you opened it as an administrator.
    
    ![What PowerShell looks like when you first open it.](../media/246a4acc-149d-4b96-b8a3-2d702fee1ddc.png)
  
1. In your search bar, type Windows PowerShell.
    
2. Right-click on **Windows PowerShell** and select **Run as Administrator**.
    
    ![Open PowerShell as "Run as administrator."](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
  
2. Check installed module:
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. To uninstall a previous version of AzureADPreview or AzureAD, run this command:
  
```
   Uninstall-Module AzureADPreview
```

or
  
```
   Uninstall-Module AzureAD
```

4. To install the latest version of AzureADPreview, run this command:
  
```
   Install-Module AzureADPreview
```

At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.
  
### Allow or block guest access to all Office 365 groups
<a name="BKMK_UsePowerShellControlGuestAccess"> </a>

1. Did you install the **AzureADPreview** module, as instructed in the above section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"? Not having the most current **preview** version is the #1 reason these steps don't work for people. 
    
2. If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).
    
3. Run the following commands. Press **Enter** after each command. 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```

    In the **Sign in to your Account** screen that opens, enter your Office 365 admin account and password to connect you to your service, and click **Sign in**.
    
    ![Enter your Office 365 credentials](../media/a2b4e2f3-436f-4a6c-b571-1a192698acea.png)
  
4. Run the following command:
    
     `$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified"}`
    
5. See if you already have an AzureADDirectorySetting object, and if so, save the Object ID. Run this command:
    
     `$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id`
    
    IF, and ONLY if, that cmdlet displays an error saying the object doesn't exist, create one using these cmdlets:
    
     `$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified"}`
    
     `$settingsCopy = $template.CreateDirectorySetting()`
    
     `New-AzureADDirectorySetting -DirectorySetting $settingsCopy`
    
     `$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id`
    
6. Copy the AzureADDirectorySetting object back into the local $settingsCopy variable:
    
     `$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID`
    
    This is only a COPY of the settings; changes won't take effect until you copy it BACK to the AzureADDirectorySetting object.
    
7. Set the option to allow guests to access O365 groups:
    
     `$settingsCopy["AllowGuestsToAccessGroups"] = "true"`
    
8. Finally, (as mentioned above) for the change to take effect you must copy the settings BACK to the AzureADDirectorySetting object:
    
     `Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy`
    
9. To verify the change took effect, retrieve the value from the AzureADDirectorySetting object (don't just look at the local copy in $settingsCopy):
    
     `(Get-AzureADDirectorySetting -Id $settingsObjectID).Values`
    
    The results should look like this:
    
    ![AllowGuestsToAccessGroups should be set to True](../media/ece812dc-1bd4-414e-b70d-dd3d726d15b9.png)
  
### Allow guests to be added to all Office 365 groups
<a name="BKMK_UsePowerShellControlAddingGuests"> </a>

1. Did you install the **AzureADPreview** module, as instructed in the above section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"? Not having the most current **preview** version is the #1 reason these steps don't work for people. 
    
2. If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).
    
3. Run the following commands. Press **Enter** after each command. 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```

    In the **Sign in to your Account** screen that opens, enter your Office 365 admin account and password to connect you to your service, and click **Sign in**.
    
    ![Enter your Office 365 credentials](../media/a2b4e2f3-436f-4a6c-b571-1a192698acea.png)
  
4. Run the following command:
    
     `$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified"}`
    
5. See if you already have an AzureADDirectorySetting object, and if so save the Object ID
    
     `$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id`
    
    IF, and ONLY if, that cmdlet displays an error saying the object doesn't exist, create one using these commands:
    
     `$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified"}`
    
     `$settingsCopy = $template.CreateDirectorySetting()`
    
     `New-AzureADDirectorySetting -DirectorySetting $settingsCopy`
    
     `$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id`
    
6. Copy the AzureADDirectorySetting object back into the local $settingsCopy variable:
    
     `$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID`
    
    This is only a COPY of the settings; changes won't take effect until you copy it BACK to the AzureADDirectorySetting object.
    
7. Set the option to allow guests to be added to all O365 groups:
    
     `$settingsCopy["AllowToAddGuests"] = "true"`
    
8. Finally, (as mentioned above) in order for the change to take effect you must copy the settings BACK to the AzureADDirectorySetting object:
    
     `Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy`
    
9. To verify the change took effect, retrieve the value from the AzureADDirectorySetting object (don't just look at the local copy in $settingsCopy):
    
     `(Get-AzureADDirectorySetting -Id $settingsObjectID).Values`
    
### Allow or block guest users from a specific group
<a name="BKMK_UsePowerShellControlAddingGuests"> </a>

> [!NOTE]
> You must have global admin rights to run these commands. 
  
1. Did you install the **AzureADPreview** module, as instructed in the above section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"? Not having the most current **preview** version is the #1 reason these steps don't work for people. 
    
2. If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).
    
3. Run the following commands. Press **Enter** after each command. 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```

    In the **Sign in to your Account** screen that opens, enter your Office 365 admin account and password to connect you to your service, and click **Sign in**.
    
    ![Enter your Office 365 credentials](../media/a2b4e2f3-436f-4a6c-b571-1a192698acea.png)
  
4. Run this command.
    
     `$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}`
    
5. Run this command.
    
     `$settingsCopy = $template.CreateDirectorySetting()`
    
6. Run this command. Set to **False** to block guest access to a specific group. Set to **True** to allow guest access to a specific group. 
    
     `$settingsCopy["AllowToAddGuests"]=$False`
    
7. Run this command.
    
     `$groupID= (Get-AzureADGroup -SearchString "YourGroupName").ObjectId`
    
    Where you would replace **YourGroupName** with something like **Human Resources**. 
    
8. Run this command.
    
     `New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy`
    
    It takes 2-3 minutes to be synced.
    
9. To verify your settings, run this command:
    
     `Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values`
    
    The verification looks like this:
    
    ![The verification](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
### Allow/block guest access based on their domain
<a name="BKMK_UsePowerShellControlAddingGuests"> </a>

You can allow or block guest users who are using a specific domain. For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.
  
For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001)
  
## FAQ
<a name="bkmk_UsePowerShell"> </a>

### Who can add guest users to a group?
<a name="BKMK_Whocanaddguests"> </a>

- An Office 365 Group owner can add guest users if this option has been enabled for your organization.
    
- Global admins can add guest users to any Office 365 groups in the organization.
    
### How can a global admin add a new guest user to the organization?
<a name="BKMK_Whocanaddguests"> </a>

- Owners of an Office 365 group and global admins who are owners of the group can add guest users to Office 365 groups through Outlook on Web.
    
- Sharing a file with a guest from a SharePoint site or an Office 365 group. See [Share group files](https://support.office.com/article/749bc73b-90c9-4760-9b6f-9aa1cf01b403.aspx).
    
- Adding guests to your organization through Azure active directory B2B collaboration. Azure active directory B2B collaboration allows a company administrator to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2000 lines to the B2B collaboration portal. For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?LinkId=826383).
    
### Can global admin block guests in groups and still allow guests to access SharePoint sites?
<a name="BKMK_Whocanaddguests"> </a>

Yes, global admins can use Azure active directory Powershell cmdlets to disable "AllowGuestAccessToGroups" property on Company object, assuming external sharing is turned **On** for SharePoint sites. 
  
### How long until the guest user settings take effect in the Office 365 organization?
<a name="BKMK_Whocanaddguests"> </a>

The guest settings are set in Azure active directory. It takes 2 to 24 hours for the changes to be effective across your Office 365 organization.
  
### Can I share a group document library with an external user who isn't a member of the group?
<a name="BKMK_Whocanaddguests"> </a>

No. You can only share Office 365 Group document library with guests who have been invited to join the group. But individual group files can be still shared with guests users through file sharing from SharePoint Online.
  
### Can I manage SharePoint Online external user settings for the Group connected team site?
<a name="BKMK_Whocanaddguests"> </a>

Yes, read [Manage your group-connected team site](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx) for more details. 
  
### Is there a way to block individual guest users?
<a name="BKMK_Whocanaddguests"> </a>

No, individual guest users can't be blocked.
  
### Can I make guest objects visible in the global address list?
<a name="BKMK_MakeGuestsVisibleGAL"> </a>

Guest objects are not visible in the Exchange Global Address List by default because guest objects can be created by end-user action (e.g. invitation to access a shared document). As a rule, the contents of the Global Address List are controlled by administrators, and many organizations do not want objects created by end-user action to become visible without administrator control.
  
Use the steps listed below to make the guest objects visible in the global address list. This should be used when administrators responsible for end-to-end lifecycle of external users have access to both Azure Active Directory and Exchange Online cmdlets.
  
For example, if a guest object for meganb@contoso.com exists in Azure Active Directory, then Azure Active Directory PowerShell can be used to make meganb@contoso.com visible in the global address List.
  
1.  `Set-AzureADUser -ObjectId <<ObjectIDGuid>> -ShowInAddressList $true`
    
2.  `Set-AzureADUser -ObjectId <<ObjectIDGuid>> -GivenName 'Megan' -Surname 'Bowen' -TelephoneNumber "555-555-5555"`
    
3.  `Set-AzureADUser -ObjectId <<ObjectIDGuid>> -DisplayName "Megan Bowen"`
    
### In a hybrid Office 365 organization, do guest users who are members of an Office 365 Group sync back to on-premises Exchange servers?
<a name="BKMK_MakeGuestsVisibleGAL"> </a>

No guest users who are members of a group aren't synched back to on-premises along with the group.
  
### Can mail contacts be added to groups?
<a name="BKMK_MakeGuestsVisibleGAL"> </a>

Yes, you can. External mail contacts are contacts listed in your company's global address list. An example of this type of contact is a vendor company who regularly provides services to your organization.
  
### Can I add guest users to my Office 365 Connected Yammer Groups?
<a name="BKMK_MakeGuestsVisibleGAL"> </a>

Office 365 Connected Yammer Groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network. See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions. 
  
### Is an additional Office 365 license required for guest access?
<a name="BKMK_MakeGuestsVisibleGAL"> </a>

No. Guest access is included with all Office 365 Business Premium and Office 365 Enterprise subscriptions.
  
### I just migrated my distribution lists to Office 365 groups. Can I add guests to those?
<a name="BKMK_MakeGuestsVisibleGAL"> </a>

Yes. The guests won't receive a welcome email message, but they will have all the privileges of any other guest member. If you've not yet migrated your distribution lists, see [Migrate distribution lists to Office 365 Groups](../manage/upgrade-distribution-lists.md) for instructions. Distribution lists that contain guests can't be migrated. 
  
## See Also
<a name="bkmk_UsePowerShell"> </a>

[Manage Group membership in the Office 365 admin center](add-or-remove-members-from-groups.md)
  
[Allow/Deny guest access to Office 365 groups based on their domain](https://go.microsoft.com/fwlink/?linkid=854001)
  
[Azure Active Directory access reviews](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
  


---
title: "Manage who can create Office 365 Groups"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- IW_Planner
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: "Learn how to control which users can create Office 365 Groups."
---

# Manage who can create Office 365 Groups

  
Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people. Depending on your business, however, you might want to control who has the ability to create groups.
  
This article explains how to disable the ability to create groups **in all Office 365 services that use groups**: 
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams
    
- StaffHub
    
- Planner
    
- PowerBI

- Roadmap
    
You can restrict Office 365 Group creation to the members of a particular security group. To configure this, you use Windows PowerShell. This article walks you through the needed steps.
  
The steps in this article doesn't prevent members of certain roles from creating Office 365 Groups. Office 365 Global admins may create Office 365 Groups via any means, such as the Office 365 Admin center, Planner, Teams, Exchange, and SharePoint Online. Other roles may create Office 365 Groups via limited means, listed below.
        
  - Exchange Administrator: Exchange Admin center, Azure AD
    
  - Partner Tier1 Support: Office 365 Admin center, Exchange Admin center, Azure AD
    
  - Partner Tier2 Support: Office 365 Admin center, Exchange Admin center, Azure AD
    
  - Directory Writers: Azure AD

  - SharePoint Administrator: SharePoint Admin center, Azure AD
  
  - Teams Service Administrator: Teams Admin center, Azure AD
  
  - User Management Administrator: Office 365 Admin center, Azure AD
    
If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.

## Licensing requirements

To manage who creates Office 365 Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:

- The admin who configures these group creation settings
- The members of the security group who are allowed to create Office 365 Groups

The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:

- People who are members of Office 365 groups and who don't have the ability to create other Office 365 groups.

## Step 1: Create a security group for users who need to create Office 365 Groups

Only one security group in your organization can be used to control who is able to create Office 365 Groups. But, you can nest other security groups as members of this group. For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.

Admins in the roles listed above do not need to be members of this group: they retain thier ability to create groups.

> [!IMPORTANT]
> Be sure to use a **security group** to restrict who can create Office 365 groups. If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group. 
    
1. In the Microsoft 365 admin center, create a group of type **Security group**. Remember the name of the group! You'll need it later.
    
    ![Create a security group in the admin center.](../media/bd2b3f5b-6521-4780-b94a-2aea2c18254e.png)
  
2. Add people or other security groups who you want to be able to create Office 365 Groups groups in your org.
    
For detailed instructions, see [Create, edit, or delete a security group in the Office 365 admin center](../email/create-edit-or-delete-a-security-group.md).
  
## Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph

These procedures require the the preview version of the Azure Active Directory PowerShell for Graph. The GA version will not work.

> [!IMPORTANT]
> You cannot install both the preview and GA versions on the same computer at the same time.
  
As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one. 
  
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

Leave the PowerShell window open for Step 3, below.
  
## Step 3: Run PowerShell commands

Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Replace *\<SecurityGroupName\>* with the name of the security group that you created. For example:

`$GroupName = "Group Creators"`

Save the file as GroupCreators.ps1. 

In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").

Run the script by typing:

`.\GroupCreators.ps1`

and sign in with your administrator account when prompted.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

try
    {
        $template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified"}
        $settingsCopy = $template.CreateDirectorySetting()
        New-AzureADDirectorySetting -DirectorySetting $settingsCopy
        $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
    }
catch
    {
        $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id       
    }

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID

$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

If ($GroupName -eq "")
    {
        $SettingsCopy["GroupCreationAllowedGroupId"] = ""
    }
Else
    {
        $SettingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
    }

Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

The last line of the script will display the updated settings:

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.

If you want to turn off the group creation restriction and again allow all users to create groups, set `$GroupName` to "" and `$AllowGroupCreation` to "True" and rerun the script.
    
## Step 4: Verify that it works

1. Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups. That is, they are not a member of the security group you created or an administrator.
    
2. Choose the **Planner** tile. 
    
3. In Planner, in choose **New Plan** to create a plan. 
    
![In Planner, choose New plan.](../media/4cf6163e-bf86-4ece-9cba-409df7f6d193.png)
  
4. You should get a message that you can't create a plan:
    
![Message that you can't create a plan.](../media/9add4ae1-4e3b-4f4f-90ea-5af94d8018d1.png)

Try the same procedure again with a member of the security group.

> [!NOTE]
> If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).
    
## Related articles

[Getting started with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)
  
[Set-ExecutionPolicy](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
---
title: "Manage who can create Office 365 Groups"
ms.author: dianef
author: dianef77
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
description: "Learn how to control the ability to create groups in all Office 365 services, such as Outlook, Yammer, SharePoint, StaffHub, Microsoft Teams, and PowerBI."
---

# Manage who can create Office 365 Groups

  
Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people. Depending on your business, however, you might want to control who has the ability to create groups. [Why control who creates Office 365 Groups?](#why-control-who-creates-office-365-groups)
  
This article explains how to disable the ability to create groups **in all Office 365 services that use groups**: 
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams
    
- StaffHub
    
- Planner
    
- PowerBI
    
 **The best way to do this is to create a security group, and then only the people in that security group will be able to create Office 365 Groups and teams in these apps.** This article walks you through these steps. 
  
To control who creates Office 365 Groups, you use Windows PowerShell, which is a lot like typing commands at the C:\ prompt in the old DOS environment. If you've never used PowerShell, this task is a great introduction to using it. We walk you through what you need to do, step-by-step.
  
## What you need to know before you begin

- Doing the steps in this article requires a subscription to Azure Active Directory (Azure AD) Premium. **The administrator who configures the settings, and the members of the group(s) assigned the self-service creation permission, must have Azure AD Premium licenses assigned to them**. For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-get-started-premium). In addition, see [Learn about Office 365 Groups - Features & Licensing](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2#ID0EAACAAA=Features_&_Licensing) in the section "Granular self-service group creation controls".
    
- Do not try to use the GA version - Azure Active Directory PowerShell for Graph - to perform the steps in this article. It won't work.
    
- The PowerShell commands in this article only change who can create Office 365 Groups. They won't affect the rest of your Office 365 environment.
    
- You apply the steps in this article only once in your organization, for one security group. If you try to applying them again for another security group, you'll get an error that looks like this:
    
  ```
  A conflicting object with one or more of the specified property values is present in the directory.
  ```

- The steps in this article doesn't prevent members of certain roles from creating Office 365 Groups. Office 365 Global admins may create Office 365 Groups via any means, such as the Office 365 Admin center, Planner, Teams, Exchange, and SharePoint Online. Other roles may create Office 365 Groups via limited means, listed below.
        
  - Exchange Administrator: Exchange Admin center, Azure AD
    
  - Partner Tier1 Support: Office 365 Admin center, Exchange Admin center, Azure AD
    
  - Partner Tier2 Support: Office 365 Admin center, Exchange Admin center, Azure AD
    
  - Directory Writers: Azure AD

  - SharePoint Administrator: SharePoint Admin center, Azure AD
  
  - Teams Service Administrator: Teams Admin center, Azure AD
  
  - User Management Administrator: Office 365 Admin center, Azure AD
    
    If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.
    
- It's important that you use a **security group** - as described in Step 1 of this article - to restrict who can create Office 365 groups. Don't try to use an Office 365 Group for this. If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group. 
    
- Setting `Set-MSOLCompanySettings -UsersPermissionToCreateGroupsEnabled $True` only enables permissions for users to create Security groups, not Office 365 groups. For more information about this cmdlet, see [Set-Msolcompanysettings](https://go.microsoft.com/fwlink/?linkid=854599).
    
- Let's say you do the steps in this article and give some people the ability to create Office 365 Groups. But for some reason they still can't create an Office 365 group using Outlook. Check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135). It provides additional controls to block the creation of Office 365 groups using Outlook.
    
## Install the preview version of the Azure Active Directory PowerShell for Graph

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
  
## Step 1: Create a security group for users who need to create Office 365 Groups

Only one security group in your organization can be used to control who is able to create Office 365 Groups. But, you can nest other security groups as members of this group. For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group. 
  
1. In the Office 365 admin center, create a group of type **Security group**. Remember the name of the group! You'll need it later.
    
    ![Create a security group in the admin center.](../media/bd2b3f5b-6521-4780-b94a-2aea2c18254e.png)
  
2. Add people or other security groups who you want to be able to create Office 365 Groups groups in your org.
    
For detailed instructions, see [Create, edit, or delete a security group in the Office 365 admin center](../email/create-edit-or-delete-a-security-group.md).
  
## Step 2: Run PowerShell commands

The most common mistakes are not having the preview module and typos. Instead of typing each command, copy and paste the commands and examples in this article. You can use the left and right arrow keys to move around in a command before you run it, and the up and down arrow keys to scroll back through previous commands. If you make a mistake, you'll get a bunch of red text saying there was an error. Just try typing the command again. If you get stuck, [call us](../contact-support-for-business-products.md)!
  
 **These steps were last tested and verified on 18 April, 2018. Remember, use the AzureADPreview version, not Azure Active Directory PowerShell for Graph.**
  
1. If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).
    
2. Run the following commands. Press **Enter** after each command. 
    
```
Import-Module AzureADPreview
Connect-AzureAD
```

  In the **Sign in to your Account** screen that opens, enter your Office 365 admin account and password to connect you to your service, and click **Sign in**.
 ![Enter your Office 365 credentials](../media/a2b4e2f3-436f-4a6c-b571-1a192698acea.png)
  
3. Find the name of your security group from [Step 1: Create a security group for users who need to create Office 365 Groups](#step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups) by using the following syntax: 
    
```
Get-AzureADGroup -SearchString "<Name of your security group>"
```

For example, I named my group AllowedtoCreateGroups. So I would run:
    
```
Get-AzureADGroup -SearchString "AllowedtoCreateGroups"
```

This will display the properties of my AllowedtoCreateGroups security group.
    
![Group information through Azure AD PowerShell](../media/c68aea8b-53c3-4103-900b-d8e6f9fbf2d7.png)
  
  You can see that the **ObjectID** property value of my AllowedtoCreateGroups group is  `afc88...` You don't need to write down the **ObjectID** of your security group, but you'll need to be able to recognize it in a later step. 
    
4. Run this command:
    
```
$Template = Get-AzureADDirectorySettingTemplate | where {$_.DisplayName -eq 'Group.Unified'}
```

5. Run this command:
    
```
$Setting = $Template.CreateDirectorySetting()
```

6. Run this command:
    
```
New-AzureADDirectorySetting -DirectorySetting $Setting
```

If you get an error like this skip to step 7. The error message means you don't need to do step 6.
    
![If you get an error message, skip to step 7.](../media/f00ddf3f-a58f-4cc0-8d70-8ee60cfc5c92.png)
  
Otherwise, upon successful completion, the cmdlet returns the ID of the new settings object.
    
7. Run this command:
    
```
$Setting = Get-AzureADDirectorySetting -Id (Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ).id
```

8. Run this command:
    
```
$Setting["EnableGroupCreation"] = $False
```

9. Use this syntax:
    
```
$Setting["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString "<Name of your security group>").objectid
```

For example, I named my group AllowedtoCreateGroups, so I would run this command:
    
```
$Setting["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString "AllowedtoCreateGroups").objectid
```

10. Run this command:
    
```
Set-AzureADDirectorySetting -Id (Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ).id -DirectorySetting $Setting
```

11. To verify your security group CAN create groups, and everyone else in your organization can't, run this command:
    
```
(Get-AzureADDirectorySetting).Values
```

The result should look like this (but with the **ID** value for your security group - this is where you need to be able to recognize it): 
    
![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)
  
Only members of the **AllowedtoCreateGroups** security group ( **Afc88abb.....** ) can create groups. No one else can, as indicated by **EnableGroupCreation = False**.
    
## Step 3: Verify that it works

1. Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups. That is, they are not a member of the security group you created.
    
2. Choose the **Planner** tile. 
    
3. In Planner, in choose **New Plan** to create a plan. 
    
![In Planner, choose New plan.](../media/4cf6163e-bf86-4ece-9cba-409df7f6d193.png)
  
4. You should get a message that you can't create a plan:
    
![Message that you can't create a plan.](../media/9add4ae1-4e3b-4f4f-90ea-5af94d8018d1.png)
  
## What should I do if it doesn't work?

Check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).
  
If this doesn't fix the problem, [call us for help](../contact-support-for-business-products.md).
  
## Remove the restriction on who can create groups

Let's say after a while you want to remove the limit you put on who can create groups. Run this command:
  
```
$SettingId = Get-AzureADDirectorySetting -All $True | where-object {$_.DisplayName -eq "Group.Unified"}
Remove-AzureADDirectorySetting -Id $SettingId.Id
```

## More information on managing groups

### Why control who creates Office 365 Groups

All Office 365 users can create Office 365 Groups by default:
  
- Users can create up to 250 Office 365 Groups each.
    
- Office 365 admins have no limit on the number of Office 365 Groups that they can create.
    
- The default maximum number of Office 365 Groups that an Office 365 organization can have is currently 500,000, but can be increased by request. For more information on Office 365 Groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).
    
Several Office 365 services **require** the ability to create Office 365 Groups for specific functions. For example, a group is created automatically when a plan is created using Microsoft Planner. This means users can inadvertently create a lot of groups as they experiment with creating plans. 
  
You might want tighter control of Office 365 Group creation and prefer that not everyone can create them - that only users of Office 365 services that require Office 365 Groups creation are allowed to create them.
  
>[!NOTE]
>Note that while you have the ability to control which users can create Office 365 Groups, it does not impact the ability of all licensed users to participate in group activities, such as creating tasks in Planner or responding to conversations in Outlook. 
  
### Edit an existing Group settings object

If you had previously created a Group settings object, and need to change the value for a setting (for example, specify a different group), you can use the following procedure.
  
1. Open a Windows PowerShell window on your computer and run the following command:
    
```
Import-Module AzureADPreview
Connect-AzureAD
```


In the **Sign in to your Account** screen that opens, enter your credentials to connect you to your service, and click **Sign in**.
    
![Enter your Office 365 credentials](../media/a2b4e2f3-436f-4a6c-b571-1a192698acea.png)
  
2. After connecting to your Office 365 service, you first need to **reference the Group settings object that contains the configuration settings**. To do this, you will need the ObjectId for it. If you don't know the ObjectId, you can search for it by typing and entering the following cmdlet: 
    
```
Get-AzureADDirectorySetting
```

This will display the current Group settings object, including its ObjectId.
    
![Example of values that might appear](../media/619b0a53-1070-43e4-9df6-3970b21a2ce0.png)
  
![Find Group Settings object](../media/064dc2a5-705b-442f-a9d3-3a70491be412.png)
  
3. After finding the ObjectID for the Groups Settings object, you can use it to **select the Group settings object that contains your settings**. Type and enter the following cmdlet: 
    
```
$setting=Get-AzureADDirectorySetting -Id <ObjectId>
```

For example, using the ObjectId in the graphic above
    
```
$setting=Get-AzureADDirectorySetting -id d634c419-bde2-4ebb-880e-a1dc4a1904cb
```

You will be returned to a prompt in the Windows Azure Active Directory Module.
    
4. After selecting the Group settings object, you should **check the current configuration values** by typing and entering the following: 
    
```
$setting.values
```

![Screenshot of list of the current configuration values](../media/4ace7a26-aa9e-481d-8af1-8cce66e75127.png)

This will display the setting values for the Group settings object and will return you to a prompt in the Windows Azure Active Directory Module. In the example above  *GroupCreationAllowedGroupId*  indicates that members of the security group **1f8f32...** can create groups. And because  *EnableGroupCreation*  = "False" no one else in the company can create groups. 
    
5. Now you can **make specific changes to the Group setting values**. As an example, you can use the following cmdlet if you want to point to a different group to allow Group creation: 
    
```
$settings["GroupCreationAllowedGroupId"] = "<object ID for the new group>"
```

For example, let's change from the  *AllowedtoCreateGroups*  group we previously set, to a different group we had created with an ObjectId of **3054dce3-37e6-437a-a817-2363272cac1c**:
  
```
$settings["GroupCreationAllowedGroupId"] = "3054dce3-37e6-437a-a817-2363272cac1c"
```

After configuring your settings, you will be returned to a prompt in the Windows Azure Active Directory Module.
    
6. After configuring your new settings, you can **apply the settings directly to the Group settings object** by typing and entering the following: 
    
```
Set-AzureADDirectorySetting -Id <object ID for the new group> -DirectorySetting $Setting
```

For example, using the ObjectID of the Group settings object we are editing:

```
Set-AzureADDirectorySetting -Id d634c419-bde2-4ebb-880e-a1dc4a1904cb -DirectorySetting $Setting
```

You will be returned to a prompt in the Windows Azure Active Directory Module.
    
7. You can **verify that you Group settings have been updated** by running the $settings.values cmdlet and verifying the values. 
    
  ![Group settings object with changed value](../media/0d0fec8d-28d4-4612-96de-3e416eb2fdd7.png)

  Notice that the  *GroupCreationAllowedGroupId*  setting has changed to your new group. 
    
## Related articles

[Getting started with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Learn about Office 365 Groups](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

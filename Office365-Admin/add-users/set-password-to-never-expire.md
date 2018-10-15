---
title: "Set an individual user's password to never expire"
ms.author: dianef
author: dianef77
manager: mnirkhe

ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466

description: "Learn how to set some individual user passwords to never expire, using Windows PowerShell."
---

# Set an individual user's password to never expire

 *Last updated 4 August, 2017* 
  
|||
|:-----|:-----|
|![I forgot the username or password for the account I use with Office.](../media/d0ee024e-999d-438b-b72d-2e1779cf7f83.png)           <br/> |This article is for people who set password expiration policy for a business, school, or nonprofit.  <br/> **If you're a user, you don't have the permissions to set your password to never expire. Ask your work or school technical support to do the steps in this article for you.** <br/> |
   
If you have company requirements to set some individual user passwords to never expire, you need to use Windows PowerShell. You can't do this in the Office 365 admin center.
  
If you're new to Windows PowerShell, you can do this! The PowerShell commands used in this article will only change a person's password expiration.
  
**Video on how to set up user passwords to never expire**

> [!VIDEO https://www.microsoft.com/videoplayer/embed/f84252d0-e20b-45ed-981c-4c2b69f781de?autoplay=false]
  
Video on how to set up user passwords to never expire
  
> [!IMPORTANT]
> You can only do these steps on user accounts that aren't synchronized through directory synchronization. 
  
## Install the required PowerShell modules

1. Install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Install the 64-bit version of the Windows Azure Active Directory Module for Windows PowerShell with these steps:
    
  - Open the [Azure Active Directory Connection](https://go.microsoft.com/fwlink/?linkid=854265) web page. 
    
  - In **Files in Download** at the bottom of the page, click **Download** for the **AdministrationConfig-V1.1.166.0-GA.msi** file, and then install it. 
    
3. Open Windows PowerShell as an administrator:
    
1. In your search bar, type Windows PowerShell.
    
2. Right-click on **Windows PowerShell** and select **Run as Administrator**.
    
    ![Open PowerShell as "Run as administrator."](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
  
3. The Windows PowerShell window will pop open. The prompt C:\Windows\system32 means you opened it as an administrator.
    
    ![What PowerShell looks like when you first open it.](../media/246a4acc-149d-4b96-b8a3-2d702fee1ddc.png)
  
4. As a best practice, we recommend installing the latest AzureADPreview module. Type the following command at the PowerShell prompt:
    
  ```
  Install-Module AzureADPreview
  ```

5. At the message about an untrusted repository, type **Y**.
    
    If you already have AzureADPreview installed, see the [Update preview version of Azure Active Directory Module for Windows PowerShell](set-password-to-never-expire.md#bkmk_preview) about how to uninstall the old version and get the new one. Otherwise, you're ready to go! 
    
## Set a user's password to never expire
<a name="__toc378845826"> </a>

1. If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).
    
2. Run the following command:
    
  ```
  Connect-MsolService
  ```

3. In the **Sign in to your account** page that opens, sign in with your Office 365 admin account, and click **Sign in**.
    
4. Run the following command to set the password of one user to never expire:
    
  ```
  Set-MsolUser -UserPrincipalName <name of the account> -PasswordNeverExpires $true
  ```

    For example, if the name of the account is Ina@contoso.com, you'd type the command like this:
    
  ```
  Set-MsolUser -UserPrincipalName Ina@contoso.com -PasswordNeverExpires $true
  ```

    If you get a red error message, there's probably a typo or an extra space. Try again! Or, copy and paste the above to the PowerShell prompt, and use the arrow key to erase \<name of the account\> and enter the real name of the account.
    
5. When you're successful, the PowerShell prompt appears for the next command. It doesn't display anything like "done" or "success."
    
## Find out whether a user's password is set to never expire
<a name="__toc378845827"> </a>

1. Run the following command:
    
  ```
  Connect-MsolService
  ```

2. In the **Sign in to your account** page that opens, enter your admin credentials to connect to the service, and click **Sign in**.
    
3. Run the following command:
    
  ```
  Get-MSOLUser -UserPrincipalName <user ID> | Select PasswordNeverExpires
  ```

    For example, to see the status for Ina@contoso.com, you'd type the following:
    
  ```
  Get-MSOLUser -UserPrincipalName Ina@contoso.com | Select PasswordNeverExpires
  ```

    The following picture shows how I set the password to never expire, and then ran the command to verify it is now set to never expire:
    
    ![This picture shows the commands to set the password to never expire, and then verify it was set.](../media/c0972196-5f4c-4f93-9ac9-15321eec5fdb.png)
  
## Update preview version of Azure Active Directory Module for Windows PowerShell
<a name="bkmk_preview"> </a>

The AzureADPreview module is required for a lot of procedures. As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview version and get the latest one before you run PowerShell commands. 
  
1. To uninstall a previous version, run this command:
    
  ```
  Uninstall-Module AzureADPreview
  ```

2. To install the latest version, run this command:
    
  ```
  Install-Module AzureADPreview
  ```

    At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.
    
## Related articles
<a name="bkmk_preview"> </a>

[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md)
  
[Let people reset their own passwords in Office 365](let-users-reset-passwords.md)
  


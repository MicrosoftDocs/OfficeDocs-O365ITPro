---
title: "Get access to and back up a former user's data"
ms.author: twerner
author: twernermsft
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_SCBlockedUserData'
- 'O365M_SCBlockedUserData'
- 'O365E_SCBlockedUserData'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- ScenarioChain
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: "Learn how to preserve an employee's files and emails when the person leaves your organization."
---

# Get access to and back up a former user's data

 
  
When an employee leaves your organization, you probably want to access their data - meaning their documents and emails - and either review it, back it up, or transfer ownership to a new employee.
  
If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.
  
Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. If you already deleted their account, you have **30 days** to [restore](restore-user.md) it. At that point, the data will be available to you even after 30 days. However, if you don't restore the account, after 30 days the OneDrive content is permanently deleted. 
  
To save the content, here's what you do:
  
- To preserve a former employee's OneDrive for Business documents you 1) access the former employee's OneDrive for Business, and then 2) move the files.
    
- To gain access to a former employee's email, you 1) [export the user's Outlook email](#part-2---get-access-to-the-outlook-information-of-the-former-employee) information to a .pst file, and then 2) [import the email](#part-3---give-access-of-former-employees-email-to-another-user) into another employee's Outlook inbox. 
    
## Part 1 - Get access to the former employee's OneDrive for Business documents

1. Sign in to Office 365 with your work or school account. 
    
2. Go to the [Office 365 admin center](../admin-overview/about-the-admin-center.md).
    
3. Go to Active users and select the user.
    
4. Expand **OneDrive Settings** in the user details pane, and then click **Access files**.
    
5. Copy the files to your own OneDrive for Business or a common location.
    
    There are a few ways to copy files in Office 365. See [Video: Set up document storage and sharing in Office 365](https://support.office.com/article/6a41fb61-9c11-4adf-9b98-f7910fe1b0d2.aspx). Or, to sync your files, and then upload those files to your OneDrive for Business or your team site, see [Sync files with the new OneDrive sync client in Windows](https://support.office.com/article/615391c4-2bd3-4aae-a42a-858262e42a49.aspx).
    > [!NOTE]
    > You can move up to 500 MB of files and folders at a time.
    > When you use Move to with documents that have version history, only the latest version is moved. To move earlier versions, you need to restore and move each one. 
    
## Removing Access

1. Sign in to https://admin.microsoft.com as a global or SharePoint admin. (If you see a message that you don't have permission to access the page, you don't have Office 365 administrator permissions in your organization.)

2. In the left pane, under Admin centers, select SharePoint.

3. In the left pane, select user profiles.

4. Under People, select Manage User Profiles.

5. Enter the user's name and select Find.

6. Right-click the user, and then select Manage site collection owners.

7. Remove admins for the OneDrive, and then select OK.
    
## Part 2 - Get access to the Outlook information of the former employee


To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).
  
1. [Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)
    
2. In Outlook, choose **File**.
    
    ![This is what the ribbon looks like in Outlook 2016.](../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Choose **Open &amp; Export** \> **Import/Export**.
    
    ![Import/Export command in the Backstage view](../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Click **Export to a file**, and then click **Next**.
    
    ![Export to a file option in the Import and Export Wizard](../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Click **Outlook Data File (.pst)**, and then click **Next**.
    
6. Select the account you want to export by clicking the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com. If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected. 
    
    > [!NOTE]
    > You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps. 
  
    ![Export Outlook Data File dialog box with top folder selected and Include subfolders checked](../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Click **Next**.
    
8. Click **Browse** to select where to save the Outlook Data File (.pst). Type a  *file name*  , and then click **OK** to continue. 
    
    > [!NOTE]
    > If you've used export before, the previous folder location and file name appear. Type a  *different file name*  before clicking **OK**. 
  
9. If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.
    
10. Click **Finish**.
    
Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.
  
1. If you're creating an Outlook Data File (.pst), an optional password can help protect the file. When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then click **OK**. In the **Outlook Data File Password** dialog box, type the  *password*  , and then click **OK**.
    
2. If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*  , and then click **OK**.
    
Check out [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) for the steps for Outlook 2010. 
  
## Part 3 - Give access of former employee's email to another user
<a name="bkmk_import"> </a>

To give access of the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.
  
1. In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.
    
    This starts the Import and Export Wizard.
    
2. Choose **Import from another program or file**, and then click **Next**.
    
    ![Import and Export Wizard](../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Choose **Outlook Data File (.pst)**, and click **Next**.
    
4. Browse to the .pst file you want to import.
    
5. Under **Options**, choose how you want to deal with duplicates
    
6. Click **Next**.
    
7. If a password was assigned to the Outlook Data File (.pst), enter the password, and then click **OK**.
    
8. Set the options for importing items. The default settings usually don't need to be changed.
    
9. Click **Finish**.
    
 **Tip** If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File, and then, in the navigation pane, click and drag the items from Outlook Data File folders to your existing Outlook folders. 
  
Check out [Import email, contacts, and calendar from an Outlook .pst file](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac.aspx) for the steps for Outlook 2010. 
  
## Related Topics
[Remove a former employee from Office 365](remove-former-employee.md)

[Add and remove admins on a OneDrive account](https://github.com/MicrosoftDocs/OfficeDocs-SharePoint/blob/live/SharePoint/SharePointOnline/manage-user-profiles.md#add-and-remove-admins-on-a-onedrive-account)
  


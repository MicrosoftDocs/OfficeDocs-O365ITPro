---
title: "Remove a former employee from Office 365"
ms.author: kwekua
author: kwekua
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_SCDeleteUserTemp'
- 'O365P_SCDeleteUserBP'
- 'O365P_SCBlockedUsers'
- 'O365M_SCDeleteUserTemp'
- 'O365M_SCDeleteUserBP'
- 'O365M_SCBlockedUsers'
- 'O365E_SCDeleteUserTemp'
- 'O365E_SCDeleteUserBP'
- 'O365E_SCBlockedUsers'
- 'O365E_AdminODSettsSignOut'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Top
- Core_O365Admin_Migration
- MiniMaven
- ScenarioChain
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1

description: "Follow this checklist to remove an employee from Office 365 and secure data. "
---

# Remove a former employee from Office 365

 
  
## Sign out now!


If you need to get an employee out of Office 365 immediately, here's what you do:
  
::: moniker range="o365-worldwide"
1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Office 365 admin center, choose the user, and reset their password (don't send it to them).
    
3. While still at the user's properties page, expand **OneDrive Settings**, and then choose **Initiate**. 
    
    ![Choose Initiate to sign out the user immediately.](../media/7b4c68b9-85a8-4bc9-b00b-4a09852b3253.png)
  
Within an hour - or after they click out of the current Office 365 page they are on - they will be prompted to sign in again. (The refresh token is good for an hour, so the timeline depends on how much time is left on their token and whether they navigate out of their current webpage.)
  
 **CAVEAT**: If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately. As soon as they click a different tile, such as OneDrive, or refresh their browser, the sign out is initiated. 
  
To use PowerShell to sign out a user immediately, see [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) cmdlet. 
  
For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## Overview of all the steps to remove an employee and secure data
<a name="bkmk_now"> </a>

::: moniker range="o365-worldwide"

Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help.

Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end

A question we often get is, "What should I do to protect data when an employee leaves the organization?" This article explains how to block access to Office 365 and the steps you should take to secure your data.
  
> [!NOTE]
> If you are a global administrator you can delete the employee, forward their email, choose what to do with their OneDrive content using the new guided experience. For more information, see [Global admin: Delete a user](remove-former-employee.md). However, we recommend completing all of the additional steps listed here to ensure the employee doesn't have access to your company's data. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Step** <br/> |**Why do this** <br/> |
|1. [Save the contents of a former employee's mailbox](#save-the-contents-of-a-former-employees-mailbox) <br/> |This is useful for the person who is going to take over the employee's work, or in case of litigation.  <br/> |
|2. [Forward a former employee's email to another employee or convert to a shared mailbox](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Wipe and block a former employee's mobile device](#wipe-and-block-a-former-employees-mobile-device) <br/> |Removes your business data from the phone or tablet.  <br/> |
|4. [Block a former employee's access to Office 365 data](#block-a-former-employees-access-to-office-365-data)<br/> |It prevents the person from accessing their old Office 365 mailbox and data.  <br/><br/> **Tip**: When you block a user's access, you're still paying for their license. You have to delete the license from your subscription to stop paying for it (step 5).           |
|5. [Move the employee's OneDrive content](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |If they used a personal computer instead of a company-issued computer to download files from OneDrive and SharePoint, there's no way for you to wipe those files they stored.  <br/><br/> They will continue to have access to any files that were synced to their computer.  <br/> |
|6. [Remove and delete the Office 365 license from a former employee](#remove-and-delete-the-office-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Delete a former employee's user account](#delete-a-former-employees-user-account)<br/> |This removes the account from your Office 365 admin center. Keeps things clean.  <br/> |
   
## Save the contents of a former employee's mailbox
<a name="bkmk_preserve"> </a>

There are two ways you can save the contents of the former employee's mailbox:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    OR
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    Once you convert the mailbox to an "inactive mailbox," administrators, compliance officers, or records managers can use In-Place eDiscovery tools in Exchange Online to access and search the contents.
    
    Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.
    
    To learn how to place a hold on a mailbox, see the TechNet article [Manage inactive mailboxes in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=286939).
    
## Forward a former employee's email to another employee or convert to a shared mailbox
<a name="bkmk_forward"> </a>

In this step, you assign the former employee's email address to another employee, or [convert the user's mailbox to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) that you've created. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- If you set up email forwarding, only  *new*  emails sent to the former employee will now be sent to the current employee. 
    
- Email forwarding requires that the former employee's account has a license.
    
 > [!IMPORTANT] 
 > If you're setting up email forwarding or a shared mailbox, at the end, don't delete the former employee's account. The account needs to be there to anchor the email forwarding or shared mailbox. 
  
::: moniker range="o365-worldwide"  
1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Office 365 admin center, select **Users**. 
    
    ![Click on User.](../media/1596dc50-1d06-4b3a-83c3-2791d0856d6f.png)
  
3. Choose the employee that you want to block.
    
    ![Choose the user you want to block](../media/d14e5265-24df-4fee-80f1-22900521e313.png)
  
4. Click **Mail Settings**. Next to **Email Forwarding** choose **Edit**. 
    
    ![Choose Mail Settings and then choose Edit.](../media/fd3fa81a-e063-44ae-b411-5644365a9982.png)
  
5. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
    
    ![Add the email address of the current employee.](../media/d1525aa0-0c68-4337-ba18-95c40562cc52.png)
  
6. Choose **Save**. 
    
7. Remember, don't delete the former employee's account.
    
## Wipe and block a former employee's mobile device
<a name="bkmk_mobile"> </a>

If your former employee had a organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.
  

::: moniker range="o365-worldwide"
1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Office 365 admin center, in the lower-left navigation pane, expand **Admin centers** and select **Exchange**. 
    
    Your screen might look like one of the following images:
    
    ![Office 365 admin centers](../media/0df0cf37-04b2-4051-8d45-8594587c5fa8.png)
  
3. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**. 
    
4. Select the user, and under **Mobile Devices**, choose **View details**. 
    
5. On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, click **Wipe Data**![Wipe Device](../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then click **Block**. 
    
6. Click **Save**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## Block a former employee's access to Office 365 data
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Blocking an account can take up to 24 hours to take effect. If you need to immediately prevent a user's sign-in access, you should [reset their password](reset-passwords.md) and then initiate a one-time event that will sign them out of Office 365 sessions across all devices. See [Sign out now!](#sign-out-now)
  
To block a user from signing in and accessing Office 365 data:
  

::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Office 365 admin center, select **Users**. 
    
    ![Click on User.](../media/1596dc50-1d06-4b3a-83c3-2791d0856d6f.png)
  
3. Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane. 
    
    ![Choose edit next to Sign-in status](../media/49e2c981-abb8-435b-a977-b2bbc67bdd51.png)
  
4. On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**. 
    
## Block a former employee's access to email (Exchange Online)
<a name="bkmk_block_email"> </a>

If you have Office 365 email as part of your Office 365 subscription, you need to log in to the Exchange admin center to follow these steps to block your former employee from accessing their email.
  

::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Office 365 admin center, in the lower-left navigation pane, expand **Admin centers** and select **Exchange**. 
    
    Your screen might look like one of the following images:
    
    ![Office 365 admin centers](../media/0df0cf37-04b2-4051-8d45-8594587c5fa8.png)
  
3. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**. 
    
4. Double-click the user to open **Mailbox features** page. Under **Mobile Devices**, click **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted. 
    
5. Under **Email Connectivity**, click **Disable** for all protocols, (Outlook on the web, IMAP, POP3 &amp; MAPI) and answer **Yes** to all when prompted. 
    
## Remove and delete the Office 365 license from a former employee
<a name="bkmk_remove"> </a>

So you don't continue paying for a license after someone leaves your organization, you need to remove their Office 365 license and then delete it from your subscription. If you choose not to delete the license from your subscription, you can assign it to another user.
  
When you remove the license, all that user's data is held for 30 days. You can [access](get-access-to-and-back-up-a-former-user-s-data.md) the data, or [restore](restore-user.md) the account if the user comes back. After 30 days, all the user's data (except for documents stored on SharePoint Online) is deleted permanently from Office 365 and can't be recovered. 
  
 
::: moniker range="o365-worldwide"

1. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. In the Office 365 admin center, select **Users**. 
    
    ![Click on User.](../media/1596dc50-1d06-4b3a-83c3-2791d0856d6f.png)
  
3. Select the employee that you want to block, and then choose **Edit** next to **Product licenses** in the user pane. 
    
    ![Choose edit next to Product licenses](../media/5f54ed94-d0f0-4884-86cb-c7a7440d128b.png)
  
4. On the **Product licenses** pane, slide the license indicator to **Off** position and then choose **Assign** to remove the license. 
    
    ![Remove licenses](../media/e4020883-841a-4bfe-a742-41276618a651.png)
  
    The pane will state **Products removed** when the removal is done. 
    
 **To reduce the number of licenses you're paying for** until you hire another person, do the following: 
  
1. In the Office 365 admin center, choose **Billing** \> **Subscriptions**. 
    
2. Choose **Add/Remove** licenses to delete the license so you don't pay for it until you hire another person. 
    
    ![Use the arrows to delete licenses from your subscription.](../media/40b7fdb8-09a9-4b1e-8473-832038a214bf.png)
  
    When you [add](add-users.md) another person to your business, you'll be prompted to buy a license at the same time, with just one click! 
    
For more information about managing user licenses for Office 365 for business, see [Assign licenses to users in Office 365 for business](../subscriptions-and-billing/assign-licenses-to-users.md), and [Remove licenses from users in Office 365 for business](../subscriptions-and-billing/remove-licenses-from-users.md).
  
## How the deleted employee account affects Skype for Business
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## Delete a former employee's user account
<a name="bkmk_delete"> </a>

After you've saved and accessed all the former employee's user data, you can delete the former employee's account.
  
1. Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.
    

::: moniker range="o365-worldwide"

2. Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

2. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

2. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

3. In the Admin center, select **Users**. 
    
    ![Click on User.](../media/1596dc50-1d06-4b3a-83c3-2791d0856d6f.png)
  
4. Select the employee that you want to delete, and then choose **Delete user** in the user pane and then choose **Delete** \> **Close**. 
    
    ![Delete user](../media/f6cf1bfd-e0c3-40f5-8d62-415f2d5eb3c2.png)
  
When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### Does your organization use Active Directory?

If your organization synchronizes user accounts to Office 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service. You can't delete or restore them in Office 365.
  
For instructions, see this TechNet article: [Delete a User Account](https://go.microsoft.com/fwlink/?linkid=841808).
  
If you are using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet. 
  
## What you need to know about terminating an employee's email session
<a name="bkmk_session"> </a>

Here's information about how to get an employee out of email (Exchange).
  
|||
|:-----|:-----|
|**What you can do** <br/> |**How you do it** <br/> |
|Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session  <br/> |Reset password  <br/> |
|Terminate a session and block access to future sessions (for all protocols)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Terminate the session for a particular protocol (such as ActiveSync)  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
The above operations can be done in 3 places:
  
|||
|:-----|:-----|
|**If you terminate the session here** <br/> |**How long it takes** <br/> |
|In the Exchange admin center or using PowerShell  <br/> |Expected delay is within 30 min  <br/> |
|In the Azure Active Directory admin center  <br/> |Expected delay is 60 min  <br/> |
|In an on-premises environment  <br/> |Expected delay is 3 hours or more  <br/> |
   
### How to get fastest response for account termination

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## Related Topics


[Restore a user](restore-user.md)
  

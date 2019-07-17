---
title: "Create a shared mailbox"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_SharedMB'
ms.service: o365-administration
localization_priority: Priority
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: "Create a shared mailbox to enable multiple users in your business to share the responsibility of reading and answering email sent to one address."
---

# Create a shared mailbox

It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.

Shared mailboxes include a shared calendar! A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.

## Create a shared mailbox and add members

> [!VIDEO https://www.microsoft.com/videoplayer/embed/6d993201-a718-4bad-8b4d-2660670aa87d?autoplay=false]

**Try it!**

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end

::: moniker range="o365-worldwide"

1. In the Microsoft 365 admin center, go to **Groups** \> [![Go to shared mailboxes in the admin center.](../media/704ec302-c7c9-4b2c-972f-751df2eb32be.png)](https://admin.microsoft.com/AdminPortal/Home#/homepage?ref=SharedMailbox).

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

2. Sign in with an Office 365 global admin account or Exchange admin account. If you get the message " **You don't have permission to access this page or perform this action**" then you aren't an admin.

3. On the **Add a mailbox** page, enter a name for the shared mailbox. Then the wizard chooses the email address, but you can edit it.

   ![Name your shared mailbox.](../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Click **Add**. It may take a few minutes before you can add members.

5. Under **Next steps**, choose **Add members to this mailbox**. Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.

   ![Choose Add Members](../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Choose the **+Add members** button. Put a check mark next to the people who you want to use this shared mailbox, and click **Save**.

   ![Assign members to the shared mailbox](../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Choose **Close**.

You have a shared mailbox and it includes a shared calendar. Now go on to the next step: block sign-in for the shared mailbox account.

## Block sign-in for the shared mailbox account

Every shared mailbox has a corresponding user account. Notice how you weren't asked to provide a password when you created the shared mailbox? The account has a password, but it's system-generated (unknown). You aren't supposed to use the account to log in to the shared mailbox.

But what if an admin simply resets the password of the shared mailbox user account? Or what if an attacker gains access to the shared mailbox account credentials? This would allow the user account to log in to the shared mailbox and send email. To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.

1. In the Microsoft 365 admin center, select **Users** \> **Active users**.

2. In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.

3. In the properties flyout, click **Block sign-in**.

   ![Account properties in the M365 admin center](../media/m365-account-properties-block-sign-in.png)

   **Note**: If the account was already blocked, the button would say **Unblock sign-in**.

4. In the **Edit sign-in status** flyout, verify that **Block the user from signing in** is selected, click **Save**, and then click **Close**.

   ![Edit sign-in status flyout in the M365 admin center](../media/m365-edit-sign-in-status.png)

For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).

## Allow everyone to see the Sent email (the replies)

By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.

If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and choose **Sent items** \> **Edit**.

![Choose Sent items and then Edit](../media/09e28637-7900-4792-a71e-58248293cc5b.jpg)

## Add the shared mailbox to Outlook

If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.

To learn more, see:

- [Open and use a shared mailbox in Outlook](https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx)

- [Add a shared mailbox to Outlook on the web](https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx)

- [Add a shared mailbox to Outlook mobile](https://support.office.com/en-us/article/f866242c-81b2-472e-8776-6c49c5473c9f)

- [Open a shared folder or mailbox in Outlook for Mac](https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx)

- [Add rules to a shared mailbox](https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx)

## Getting an error message about not having send permissions?

Let's say you create a shared mailbox and then try to send a message from it. But you get this:

*"This message could not be sent. You do not have the permission to send the message on behalf of the specified user."*

This message appears when Office 365 is experiencing a replication latency issue. It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers. Wait an hour and then try again to send a message.

## Use a shared mailbox on a mobile device (phone or tablet)

You can access a shared mailbox on a mobile device in two ways:
- Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>. 
    
    For instructions, see [Add a shared mailbox to Outlook mobile](https://support.office.com/en-us/article/f866242c-81b2-472e-8776-6c49c5473c9f).

- Open your browser, sign in to Office 365, and then go to Outlook on the web. From Outlook on the web you'll be able to access the shared mailbox.

    For instructions, see [Add a shared mailbox in Outlook on the web](https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx).

## Use the shared calendar

When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.

1. In the Outlook app, go to calendar view, and choose the shared mailbox.

   ![Choose the calendar view](../media/0be61a9a-5fa4-4051-9fce-79393eb4e09d.png)

2. When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.

3. Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments. Everyone who is a member of shared mailbox can see their changes to the shared calendar.

## Forward emails that are sent to a shared mailbox

You do not need to assign a license to the shared mailbox in order to forward email that's sent to it. You can forward the messages to any valid email address or distribution list.

<!--There was previously a worldwide monikker for step 1, but nothing for Germany or 21Vianet. Is there a deep link to shared mailboxes for Germany or 21Vianet we can include?-->

1. On the [![Go to shared mailboxes in the admin center](../media/704ec302-c7c9-4b2c-972f-751df2eb32be.png)](https://admin.microsoft.com/AdminPortal/Home#/homepage?ref=SharedMailbox) page choose the shared mailbox you want to edit.

2. Choose **Email forwarding** \> **Edit**.

3. Set the toggle to **On**, and enter 1 email address to forward the messages to. It can be any valid email address. To forward to multiple addresses, you need to create a distribution list of the addresses, and then enter the name of the distribution list.

4. Choose **Save**.

## Send automatic replies from a shared mailbox

<!--There was previously a worldwide moniker for step 1, but nothing for Germany or 21Vianet. Is there a deep link to shared mailboxes for Germany or 21Vianet we can include?-->

1. On the [![Go to shared mailboxes in the admin center.](../media/704ec302-c7c9-4b2c-972f-751df2eb32be.png)](https://admin.microsoft.com/AdminPortal/Home#/homepage?ref=SharedMailbox) page choose the shared mailbox you want to edit.

2. Choose **Automatic replies** \> **Edit**.

3. Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.

4. Enter the reply you want to send to people inside your organization. You can't add images, only text.

5. If you want to *also* send a reply to people outside your organization, choose the check box, who you want to get the reply, and type the text. There's no way to only send to people outside your organization but not to people inside your organization.

6. Choose **Save**.

## Shared mailbox limit: 50GB

Your shared mailbox can store up to 50GB of data without you assigning a license to it. After that, you need to assign a license to the mailbox to store more data. For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#StorageLimits).

When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email. Then, after that, it will stop receiving email. Senders to the mailbox will get a non-delivery receipt.

## Prevent members from deleting messages in a shared mailbox

Unfortunately you can't prevent people from deleting messages in a shared mailbox. For example, let's say you have 5 people using a shared mailbox. One of them deletes an email after reading it. Now the email has been deleted for everyone, even if they hadn't read the message. The only way around this is to create an Office 365 Group instead of a shared mailbox.

A Group in Outlook is like a shared mailbox. For a comparison of the two, see [Compare Groups](../create-groups/compare-groups.md). To learn more about Groups, see [Learn more about Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)

## What else you need to know about shared mailboxes

- You don't need to assign licenses to shared mailboxes that are under 50GB.

- You need to give users permissions (membership) to use the shared mailbox. Only people inside your organization can use a shared mailbox.

- You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox. If you want to do this, consider creating a group for Outlook instead. To learn more, see [Create an Office 365 group in the admin center](../create-groups/create-groups.md).

-  In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app. To learn more, see [Add a shared mailbox to Outlook mobile](https://support.office.com/en-us/article/open-a-shared-mailbox-in-outlook-for-ios-and-android-f866242c-81b2-472e-8776-6c49c5473c9f?). Another option is to create a group for your shared mailbox. To learn more, see [Compare Groups](../create-groups/compare-groups.md).  

- You can't encrypt email sent from a shared mailbox. This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key. If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.

- You can convert user mailboxes to shared mailboxes. See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).

- Users with global admin or Exchange admin roles can create shared mailboxes.

- To create a shared mailbox, you need to subscribe to an Office 365 for business plan that includes email (the Exchange Online service). The Office 365 Business subscription doesn't include email; Office 365 Business Premium does.

- A shared mailbox is not intended for direct sign-in by its associated user account. You should always block sign-in for the shared mailbox account and keep it blocked.

## Fix issues with creating shared mailboxes
<a name="bkmk_Fix"> </a>

- Error message: **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**.

  This issue occurs when you're trying to give the shared mailbox a name that's already in use. For example, let's say you want shared mailboxes named info@domain1 and info@domain2. There are two ways you can do this:

  - Use Windows PowerShell. See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains in Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)

  - Or, name the second shared mailbox something different from the start to get around the error. Then in the [Admin Center](#how-to-create-a-shared-mailbox-in-the-exchange-admin-center), rename the shared mailbox to what you want it to be.

## How automapping works with shared mailboxes
<a name="bkmk_auto"> </a>

Automapping is set on the user's mailbox, not the shared mailbox.

This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work. So, if you want automapping, you have to assign permissions explicitly.

## How to create a shared mailbox in the Exchange Admin Center
<a name="bkmk_EAC"> </a>

Some customers do all their mailbox management in the Exchange Admin Center. Here are instructions for how to create shared mailboxes using that interface.

To see what permissions you need to perform these steps, see the "User mailboxes" entry in [Recipients permissions](https://technet.microsoft.com/en-us/library/dd638132%28v=exchg.160%29.aspx).

1. In the Exchange admin center, go to **Recipients** \> **Shared** \> **Add**.

2. Fill-in the required fields:

   - **Display name**

   - **Email address**

3. To grant Full Access or Send As permissions, click **Add**, and then select the users you want to grant permissions to. You can use the CTRL key to select multiple users. Confused about which permission to use? See [Which permissions should you use?](create-a-shared-mailbox.md#TypesOfPerms)

   > [!NOTE]
   > The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.

4. Click **Save** to save your changes and create the shared mailbox.

### Use the EAC to edit shared mailbox delegation

1. Go to **Recipients** \> **Shared** \> **Edit**.

2. Click **Mailbox delegation**

3. To grant or remove Full Access and Send As permissions, click **Add** or **Remove** and then select the users you want to grant permissions to.

   > [!NOTE]
   > The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.

4. Click **Save** to save your changes.

### Which permissions should you use?
<a name="TypesOfPerms"> </a>

- **Full Access** The Full Access permission lets a user sign in to the shared mailbox and act as the owner of that mailbox. While signed in, the user can create calendar items; read, view, delete, and change email messages; create tasks and calendar contacts. However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.

- **Send As** The Send As permission lets a user impersonate the shared mailbox when sending mail. For example, if Molly signs into the Marketing Department shared mailbox and sends an email, it will look like the Marketing Department sent the email.

  However, she won't be able to see any of the email that is sent to or from the shared address.

- **Send on Behalf** The Send on Behalf permission lets a user send email on behalf of the shared mailbox. For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it look like the mail was sent by "John on behalf of Reception Building 32". You can't use the EAC to grant Send on Behalf permissions, you must use the [Set-Mailbox](https://technet.microsoft.com/en-us/library/bb123981.aspx) cmdlet with the *GrantSendonBehalf*  parameter.

## Use the Exchange Management Shell to create a shared mailbox
<a name="bkmk_EAC"> </a>

Use the [New-Mailbox](https://technet.microsoft.com/en-us/library/aa997663%28v=exchg.160%29.aspx) PowerShell cmdlet to create shared mailboxes. To use this cmdlet, you need to connect to Exchange Online PowerShell.

The following example shows how to create the shared mailbox Sales Department and grants Full Access and Send on Behalf permissions for the security group MarketingSG. Users who are members of the security group will be granted the permissions to the mailbox.

1. Create a mail-enabled security group called MarketingSG. For PowerShell instructions, see [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/?linkid=856792).

2. Connect to [Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=856791).

3. Run the following commands:

   ```
   New-Mailbox -Shared -Name "Sales Department" -DisplayName "Sales Department" -Alias Sales | Set-Mailbox -GrantSendOnBehalfTo MarketingSG
   Add-MailboxPermission -Identity "Sales Department" -User MarketingSG -AccessRights FullAccess -InheritanceType All
   ```

## Should I create a shared mailbox or an Office 365 Group for Outlook?
<a name="bkmk_EAC"> </a>

See [Compare groups](../create-groups/compare-groups.md) for some guidance.

> [!IMPORTANT]
> Currently, it's not possible to migrate a shared mailbox to an Office 365 Group. Is this something you want? Let us know. **[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**!

We use your feedback to prioritize which features we work on.

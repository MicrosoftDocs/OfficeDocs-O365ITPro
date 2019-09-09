---
title: "Message center in Office 365"
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 38fb3333-bfcc-4340-a37b-deda509c2093
description: "Get an overview of Office 365 Message center and its role in change management."
---

# Message center in Office 365

To keep track of upcoming feature releases or issues, go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Message center</a>. That's where we post official announcements about new and changed features to enable you to take a proactive approach to change management. Each post gives you a high-level overview of a planned change and how it may affect your users, and links out to more detailed information to help you prepare.
  
To open the Message center:

::: moniker range="o365-worldwide"

- In the admin center, go to **Health** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Message center</a>.

::: moniker-end

::: moniker range="o365-germany"

- In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to **Health** > **Message center**.

::: moniker-end

::: moniker range="o365-21vianet"
 
- In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to **Health** > **Message center**.

::: moniker-end

You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Message center, which is a great way to stay current with push notifications. 
  
  
### Frequently asked questions

|**Question**|**Answer**|
|:-----|:-----|
|Who can view posts in Message center?  <br/> |Most users who have been assigned any admin role in Office 365 can view Message center posts. [Here's a list](#admin-roles-that-dont-have-access-to-the-message-center) of which admin roles don't have access the Message center. You can also assign the Message center reader role to users who should be able to read and share Message center posts without having any other admin privileges.<br/><br/> Additonally, you can assign the Message Center Privacy reader role to people who should see notifications about data breaches. See [About admin roles](../add-users/about-admin-roles.md) to learn more about what each admin role can do.  <br/><br/>Most Message center posts can be shared through email with non-admin users who may need to take action. This option is not available for data privacy posts that the Message Center Privacy reader views. <br/> |
|Is this the only way Microsoft will communicate changes about Office 365?  <br/> |No, there are many ways that we communicate changes in Office 365. Message center is the primary way that we communicate the timing of individual changes. See [Stay on top of Office 365 changes](stay-on-top-of-updates.md) for information about additional resources.  <br/> |
|How can I see posts in my language?  <br/> |Message center posts are written in English-only due to the timeliness of the information we are posting, but you can control whether, by default, posts are shown in English or are automatically machine-translated to your preferred language. And, no matter which default view you choose, you can select to machine-translate posts to any language we support. See [Language translation for Message center posts](language-translation-for-message-center-posts.md) for more details.  <br/> |
|Can I preview changes or features before they are rolled-out to my organization?  <br/> |Sometimes. Some changes and new features can be previewed by opting in to the Targeted release program. To opt-in, in the admin center, go to **Settings** \> **Organization profile** \> **Release preferences**. You can choose Targeted release for your entire organization, or just for selected users. See [Standard or Targeted release options in Office 365](release-options-in-office-365.md) for more information about the program.  <br/> |
|Can I find out the exact date a change will be available to my organization?  <br/> |Unfortunately, we can't tell you the exact date a change will be made to your organization. In our Message center post, we will give as much information as we can on the timing of the release, based on our confidence level. We understand you want us to be more specific on timing of releases, and we're working on improvements to get better with that level of detail.  <br/> |
|Are these messages specific to my organization?  <br/> |We do our best to make sure that you only see Message center posts that affect your organization. The Microsoft 365 Roadmap includes all of the features we are currently working on and rolling out, but not all of these features apply to every Office 365 organization. For example, if a feature is rolling out only to educational institutions, we will target the Message center post ONLY to those organizations.  <br/> |
|Can I get message center posts emailed instead?  <br/> |Yes! You can select to have a weekly digest emailed to you and up to two email addresses. If you need to have the digest go to more than two more people, you can send to an Office 365 group or distribution list. The emailed weekly digest is turned on by default. If you aren't getting your weekly digests, check your spam folder. See the **Set preferences** section of this article for more information on how to set up the weekly digest.  <br/> |
|How do I stop getting the Message center digest?  <br/> |Go to Message center in the admin center and select **Edit preferences** in the [new admin center](../microsoft-365-admin-center-preview.md) or **Edit Message center preferences** in the old admin center. Turn off the option to **Send a weekly email digest of my messages**. If you also no longer want to receive email about major updates, turn off **Send me emails for major updates**.  <br/> |
|How can I ensure Data Privacy notifications are received by the right contacts in my organization? <br/> |As a global admin you will receive data privacy messages for your organization. Additionally, you can assign the Message Center Privacy reader role to people who should see data privacy messages. Other admin roles with access to Message Center cannot view data privacy messages.   <br/><br/>You can use Message center preferences to control whether you receive email notifications specifically for data privacy messages and to control the visibility of these messages in the Message Center. Note that data privacy messages are not included in the weekly digest.<br/> |

   
  
### Messages

Message center presents a view of all active messages in a table format, by default showing the most recent message at the top of the list. Here's a quick overview of the information you'll see in each column:
  
|**Column**|**Description**|
|:-----|:-----|
|Checkbox  <br/> |Selecting the checkbox in the title row will select all messages currently displayed. Selecting the checkbox next to a single message will open that message for reading. Holding CTRL while you select multiple boxes lets you perform bulk operations on those messages, such as dismissing the messages or marking them as read or unread.  <br/> |
|Act by  <br/> |Most of the time, there won't be anything in this column. We'll only have dates here if we're making a change that requires you to take an action by a certain deadline. Since we rarely use the Act by column, if you see something here, you should pay extra attention to it.  <br/> |
|Category  <br/> | Messages are identified by one of the three following categories:  <br/><br/> **Prevent or fix issues**: These messages inform you of known issues impacting your organization and may require that you take action to avoid disruptions in service. Prevent or fix issues are different than Service health messages because they prompt you to be proactive to avoid issues. <br/> <br/> **Plan for change**: These messages inform you of changes to Office 365 that may require you to act to avoid disruptions in service. For example, we'll let you know about changes to system requirements or about features that are being removed. We try to provide at least 30 days' notice of any change that requires an admin to act to keep the service running normally. <br/> <br/> **Stay informed**: This is where we tell you about new or updated features that we are turning on in your organization. The features are usually announced first in the [Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?linkid=2070821). <br/><br/>Stay informed messages may also let you know about planned maintenance in accordance with our Service Level Agreement. Planned maintenance may result in down time, where you or your users can't access Office 365, a specific feature, or a service such as email or OneDrive for Business.  <br/> |
|Message title  <br/> |Message titles are a brief description of an upcoming change. They are sometimes long and Message center can't display the full title. Hover your cursor over the message title and the entire title will display in a pop-up box.  <br/> |
|Published  <br/> |Date that the message was published. If we make a change to an existing message, it also changes the published date.  <br/> |
|Message ID  <br/> |Microsoft tracks our Message center posts by message ID. You can reference this ID if you want to give feedback or if you call Support about a particular message.  <br/> |
|(No label)  <br/> |Selecting the X in this column will dismiss the message and remove it from view. Don't worry, you can get it back by viewing dismissed messages. In that view, selecting Refresh (![Refresh icon](../media/4565dd14-7d6a-4c42-91b7-91cc34977a43.png)) will restore the message to the active messages view.  <br/> |
   
Head over to [Manage messages in Message center](manage-messages.md) to get more information on the things you can do with messages. 
  
### Major updates

Because **Major updates** are most impactful to your organization, they are highlighted at the top of the Message center as shown in this graphic: 
  
![Major updates section of the Messge Center.](../media/message-center-major-updates.png)
  
Major updates are communicated at least 30 days in advance when an action is required.
  
Major updates are defined as:
  
- ​Changes to daily productivity such as inbox, meetings, delegations, sharing and access
    
- Changes to the themes, web parts, and other components that may affect customized features
    
- Increases or decreases to visible capacity such as storage, number of rules, items or durations
    
- Changes to product branding that may:
    
  - Cause end user confusion,
    
  - Result in changes to help desk processes and reference material, or
    
  - Change a URL
    
- A new service or application
    
- Changes requiring an admin action (exclusive of prevent or fix issues)
    
- Changes to where your data is stored
    
When you open a major update post to read it, you'll see a new gray header that has information specific to this major update, including the current roll-out status. In the following image, the major update has started Targeted release, it applies to targeted release customers only, and there are at least 40 days remaining before the feature moves into general availability.
  
![Major update post opened for reading.](../media/8e1b4527-e68d-4937-9145-c42faf72e08a.png)
  
### Set preferences

If administration is distributed across your organization, you may not want or need to see posts about all Office 365 services. Each admin can:
- Set preferences that control which messages are displayed in Message center.
- Filter messages
- Opt-in to receive a weekly digest of messages in email, to make sure you never miss an important post. 

::: moniker range="o365-worldwide"

#### Use the new admin center to set your Message center preferences 

The new admin center is available to all Microsoft 365 admins. You can opt in by selecting the **Try the new admin center** toggle located at the top of the Home page. For more information, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md).

1. Select **Edit preferences** at the top of Message center. 
    
2. Make sure that the check box is selected for each service that you want to monitor. Clear the check boxes for the services you want to filter out of your Message center view. 
    
3. Digest emails are turned on by default and are sent to your primary email address. To specify other email addresses to which the weekly email summary is sent, verify that **Send a weekly e-mail digest of my messages** is selected. To stop receiving the weekly digest, clear the check box. <br/><br/>Email notification for major updates is a separate control. If you want to receive email notices about major updates, verify that **Send me e-mails for major updates** is selected. Clear the check box to stop getting email about major updates. <br/><br/>You can select or deselect your primary email address, but you can't change it. You can enter other email addresses where you want to have the digest sent. Enter the email address for an Office 365 group or a distribution list if more than two people should get the digest email. 
    
4. Select **Save** to keep your changes.


#### Use the old admin center to set your Message center preferences 
  
::: moniker-end

1. Select **Edit Message center preferences** at the top of Message center. 
    
2. Make sure that the toggle is set to **On** for each service that you want to monitor. Use the toggle to change the setting to **Off** for the services you want to filter out of your Message center view. 
    
3. Digest emails are turned on by default and are sent to your primary email address. To specify other email addresses to which the weekly email summary is sent, verify that **Send a weekly email digest of my messages**, is **On**. To stop receiving the weekly digest, change the setting to **Off**. <br/><br/>Email notification for major updates is a separate control. If you want to receive email notices about major updates, verify that **Send me emails for major updates** is **On**. Change the setting to **Off** to stop getting email about major updates. <br/><br/>You can select or deselect your primary email address, but you can't change it. You can enter other email addresses where you want to have the digest sent. Enter the email address for an Office 365 group or a distribution list if more than two people should get the digest email. 
    
4. Select **Save** to keep your changes.<br/> 
  
We use machine translation to automatically display messages in your preferred language. Read [Language translation for Message center posts](language-translation-for-message-center-posts.md) for more information on how to set your language. 
  
> [!NOTE]
> The weekly digest and any posts that are emailed are sent in English-only. Recipients can use [Translator for Outlook](https://support.office.com/article/3d7e12ed-99d6-406e-a453-b9db0d9653fa.aspx) to read the message in their preferred language. 
  
### Admin roles that don't have access to the Message center
- Compliance administrator
- Conditional access administrator
- Customer lockBox access approver
- Device administrators
- Directory readers
- Directory synchronization accounts
- Directory writers
- Intune service administrator
- Privileged role administrator
- Reports reader

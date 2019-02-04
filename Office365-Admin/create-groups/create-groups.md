---
title: "Create an Office 365 group in the admin center"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_O365GroupsAdmin'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: "Learn to create and delete Office 365 groups, add and remove group members, and customize how the group works."
---

# Create an Office 365 group in the admin center
  
While users can create an Office 365 group from Outlook or other apps, as the global admin, you may need to create or delete groups, add or remove members, and customize how they work. The Office 365 admin center is the place to do this.
  
All Office 365 users can create Office 365 Groups by default:
  
- Users can create up to 250 Office 365 Groups each.
    
- Office 365 admins have no limit on the number of Office 365 Groups that they can create.
    
- The default maximum number of Office 365 Groups that an Office 365 organization can have is currently 500,000, but can be increased by request. For more information on Office 365 Groups limits, see [Office 365 Groups - Admin help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).
    
Several Office 365 services **require** the ability to create Office 365 Groups for specific functions. For example, a group is created automatically when a plan is created using Microsoft Planner. This means users can inadvertently create a lot of groups as they experiment with creating plans. 
  
You might want tighter control of Office 365 Group creation and prefer that not everyone can create them - that only users of Office 365 services that require Office 365 Groups creation are allowed to create them.

- People in the following Office 365 admin roles can create and manage groups in the admin center: global admin, Exchange admin, user management admin.
    
- Group users need an Exchange Online license at minimum (for example, if you don't have an Office 365 business license).
    
- Office 365 Groups must be enabled for your tenant. It is by default, but some organizations disable it.
    
- You can't be a delegated admin (for example, a consultant who is an admin on behalf of).
    
- If you create a security group to manage who can create Office 365 groups, the global admin does not need to be a member. They will still be able to create groups from the admin center. However, they won't be able to create groups from the apps (such as Planner, Outlook). To learn more, see [Manage who can create Office 365 Groups](manage-creation-of-groups.md).
    
- The Group ID is used to determine the alias (also known as the mailNickname) in Exchange. The mailNickname property must be unique across all Office 365 Groups within a tenant.

  
>[!NOTE]
>Note that while you have the ability to [control which users can create Office 365 Groups](manage-creation-of-groups.md), it does not impact the ability of all licensed users to participate in group activities, such as creating tasks in Planner or responding to conversations in Outlook. 

> [!TIP]
> Office 365 connected Yammer groups must be created in Yammer, but can be managed in the Office 365 admin center like other Office 365 groups. To learn more, see [Yammer and Office 365 Groups](https://support.office.com/article/d8c239dc-a48b-47ab-b85e-6b4b8191a869.aspx). 

## Create an Office 365 group

::: moniker range="o365-worldwide"

Go to the [![Go to the Office 365 admin center.](../media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).

::: moniker-end

::: moniker range="o365-germany"

Go to the [Office 365 admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [Office 365 admin center](https://login.partner.microsoftonline.cn).

::: moniker-end

1. Choose **Groups** \> **Groups** in the left navigation pane. 
    
    ![Office 365 Group in admin center.](../media/ee7e3ca0-c5f9-46c9-b525-6524040d0043.png)
  
2. Choose **Add a group**.
    
    ![Create a new Office 365 Group, a new distribution list, or a new security group](../media/a50b372c-feab-4ac5-90c3-e7fcb1ff649a.png)
  
3. Under **Type**, choose **Office 365**.

4. Type a name for the group.
    
5. Type a unique email address for the group.
    
6. Click **Select Owner** and then choose the name of the person who will be designated to manage the group. Anyone who is a group owner will be able to delete email from the Group inbox. Other members won't be able to delete email from the Group inbox. 
    
7. Click **Add**.

8. Click **Close**.
    
## Configure the group

Once the group has been created, you can add members and configure additional settings:
  
### Add members to an Office 365 group

Users can [add themselves or request approval](https://support.office.com/article/Join-a-group-in-Outlook-2e59e19c-b872-44c8-ae84-0acc4b79c45d), or you can add them now.

1. In the Office 365 admin center, refresh the page so your new Office 365 group appears.

2. Click the group that you want to add members to.
    
3. Next to **Members**, choose **Edit**.

4. Click **Add members**.
    
5. Select the users you want to add, and then click **Save**.
    
6. Click **Close** three times. 
    
The Office 365 group will appear in Outlook with members assigned to it.
  
### Send copies of conversations to group members' inboxes

It's important to understand how this setting works, especially if you're using a group inbox for a shared email address such as info@contoso.com.
  
When you use the admin center to create a group, by default users  *will not*  follow the group conversation or get meeting invitations sent to their inboxes. They'll need to go to the group to see conversations and meetings. It's the **Send copies of group conversations and events to the group members' inboxes** option. If you're group will have a lot of meetings, users may not get meeting requests if the don't get conversations in their inboxes. 
  
These settings mean group members will get a copy of the email sent to their Outlook Inbox. They can read and delete this copy of the email and not affect anyone else. In the Group inbox, a copy of the email still exists.

If your group will be having a lot of meetings, you should turn this on so your group members can accept the meeting requests.

If you're creating a group email address such as info@contoso.com,

Group members can opt out of receiving these emails by clicking the unsubscribe link in a group email.
  
1. In the Office 365 admin center groups list, click the group you want to change, and then click **Edit** next to the group name.

2. Turn **Send copies of group conversations and events to group members' inboxes** to **On** if you want members to receive copies of group messages and calendar items in their own inbox.

3. Select **Save**.

### Let people outside the organization email the group

This option is great if you want to have a group email address such as info@contoso.com.
  
1. Refresh your Office 365 admin center page so your new Office 365 group appears.
    
2. Select the group you want to change, and then select **Edit** next to the group name. 
    
3. Set the **Let people outside the organization email the group** toggle to **On**.
    
4. Choose **Save**.

## Who can delete email from the Group Inbox?

The Group owner can delete any emails from the Group Inbox, regardless of whether they were the initial author.
  
A member can delete an email conversation from the Group Inbox if they initiated it, and only using Outlook on the web (right-click the email, then click **Delete**). They can't do it from the Outlook app (Outlook 2016).
  
When an email is deleted from the group mailbox, it is not deleted from any of the group members' personal mailboxes.

## Related topics

[Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)

[Choose the domain to use when creating Office 365 Groups](choose-domain-to-create-groups.md)

[Allow members to send as or send on behalf of an Office 365 Group](allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Manage guest access to Office 365 groups](https://support.office.com/article/7c713d74-a144-4eab-92e7-d50df526ff96.aspx)

[Upgrade distribution lists to Office 365 Groups in Outlook](../manage/upgrade-distribution-lists.md)

[Create a contact group or distribution list in Outlook](https://support.office.com/article/88ff6c60-0a1d-4b54-8c9d-9e1a71bc3023.aspx)
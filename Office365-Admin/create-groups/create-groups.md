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

# Create an Office 365 group in the Microsoft 365 admin center
  
While users can create an Office 365 group from Outlook or other apps, as an admin, you may need to create or delete groups, add or remove members, and customize how they work. The Microsoft 365 admin center is the place to do this. 

> [!TIP]
> Office 365 connected Yammer groups must be created in Yammer, but can be managed in the Microsoft 365 admin center like other Office 365 groups. To learn more, see [Yammer and Office 365 Groups](https://support.office.com/article/d8c239dc-a48b-47ab-b85e-6b4b8191a869.aspx). 

## Create an Office 365 group

::: moniker range="o365-worldwide"

Go to the [Microsoft 365 admin center.](https://admin.microsoft.com).

::: moniker-end

::: moniker range="o365-germany"

Go to the [admin center](https://portal.office.de/adminportal/home).

::: moniker-end

::: moniker range="o365-21vianet"

Go to the [admin center](https://login.partner.microsoftonline.cn).

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
  
### Add members to a group

Users can [add themselves or request approval](https://support.office.com/article/Join-a-group-in-Outlook-2e59e19c-b872-44c8-ae84-0acc4b79c45d), or you can add them now.

1. In the admin center, refresh the page so your new group appears.

2. Click the group that you want to add members to.
    
3. Next to **Members**, choose **Edit**.

4. Click **Add members**.
    
5. Select the users you want to add, and then click **Save**.
    
6. Click **Close** three times. 
    
The group will appear in Outlook with members assigned to it.
  
### Send copies of conversations to group members' inboxes
  
When you use the admin center to create a group, by default users  do not get copies of group emails and meeting invitations sent to their inboxes. They'll need to go to the group to see conversations and meetings. You can change this setting in the admin center.

When you turn this setting on, group members will get a copy of group emails and meeting invitations sent to their Outlook Inbox. They can read and delete this copy of the email and not affect anyone else. In the Group inbox, a copy of the email still exists.

Group members can opt out of receiving these emails by choosing to stop following the group in Outlook.

1. In the Microsoft 365 admin center groups list, select the group you want to change, and then click **Edit** next to the group name.

2. Turn **Send copies of group conversations and events to group members' inboxes** to **On** if you want members to receive copies of group messages and calendar items in their own inbox.

3. Select **Save**.

### Let people outside the organization email the group

This option is great if you want to have a company email address such as info@contoso.com.
  
1. Refresh your admin center page so your new group appears.
    
2. Select the group you want to change, and then select **Edit** next to the group name. 
    
3. Set the **Let people outside the organization email the group** toggle to **On**.
    
4. Choose **Save**.

## Who can delete email from the Group Inbox?

The Group owner can delete any emails from the Group Inbox, regardless of whether they were the initial author.
  
A member can delete an email conversation from the Group Inbox if they initiated it, and only using Outlook on the web (right-click the email, then click **Delete**). They can't do it from the Outlook app (Outlook 2016).
  
When an email is deleted from the group mailbox, it is not deleted from any of the group members' personal mailboxes.

## Related topics

[Manage guest access to Office 365 groups](https://support.office.com/article/7c713d74-a144-4eab-92e7-d50df526ff96.aspx)

[Choose the domain to use when creating Office 365 Groups](choose-domain-to-create-groups.md)

[Allow members to send as or send on behalf of an Office 365 Group](allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Upgrade distribution lists to Office 365 Groups](../manage/upgrade-distribution-lists.md)

[Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)

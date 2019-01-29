---
title: "Create an Office 365 group in the admin center"
ms.author: dianef
author: dianef77
manager: mnirkhe
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
  
**Are you looking for how to create an email group (distribution list) in Outlook?** <br/> If so, see [Create a contact group or distribution list in Outlook](https://support.office.com/article/88ff6c60-0a1d-4b54-8c9d-9e1a71bc3023.aspx).  

   
Because Office 365 groups needs to have a mailbox set up for it, there are a few important steps that you can't complete until after the mailbox is fully set up. See [Next steps](#next-steps) later in this article. 
  
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
  
3. Choose the type of group you want to create, based on what you want to use it for. If you want an email address that customers can contact, such as info@contoso.com, choose Office 365 group. For a detailed comparison of the options and what to choose when, see [Compare groups](compare-groups.md).
    
4. Assign a unique email address for the group.
    
5. Choose **Select Owner** and then choose the name of the person who will be designated to manage the group. Anyone who is a group owner will be able to delete email from the Group inbox. Other members won't be able to delete email from the Group inbox. 
    
6. Choose **Add**.
    
## Next steps

There are a few steps that you can't finish until the group's mailbox is finished setting up:
  
### Add members to an Office 365 group

1. Refresh your Office 365 admin center page so your new Office 365 group appears.
    
2. Select the group you want to add members to.
    
3. Next to **Members**, choose **Edit**.
    
4. Enter the names of the people you want to be members of the group and select their name from the list. Alternatively, you can let individuals add themselves or request approval to join later (see [Join a group](https://support.office.com/article/1470a263-3e01-4633-a7b9-851b786db0d2.aspx#BKMK_JOIN_GROUP)).
    
5. Choose **Save** to update the Office 365 Group. 
    
The Office 365 group will appear in Outlook with members assigned to it.
  
> [!TIP]
> Office 365 connected Yammer groups must be created in Yammer, but can be managed in the Office 365 admin center like other Office 365 groups. To learn more, see [Yammer and Office 365 Groups](https://support.office.com/article/d8c239dc-a48b-47ab-b85e-6b4b8191a869.aspx). 
  
### Send copies of conversations to group members' inboxes

If your group will be having a lot of meetings, you should turn this on so your group members can accept the meeting requests.
  
1. Refresh your Office 365 admin center page so your new Office 365 group appears.
    
2. Select the group you want to change, and then select **Edit** next to the group name. 
    
3. Turn **Send copies of group conversations and events to group members' inboxes** to **On** if you want members to receive messages and calendar items in their own inbox,  *in addition to the group mailbox*  . 
    
  - If you're creating a group email address such as info@contoso.com, it's important you understand how this setting works. See [How following group email works](#how-following-group-email-works).
    
4. Select **Save**.
    
### Let people outside the organization email the group

This option is great if you want to have a group email address such as info@contoso.com.
  
1. Refresh your Office 365 admin center page so your new Office 365 group appears.
    
2. Select the group you want to change, and then select **Edit** next to the group name. 
    
3. Set the **Let people outside the organization email the group** toggle to **On**.
    
4. Choose **Save**.
    
## How following group email works

It's important to understand how this setting works, especially if you're using a group inbox for a shared email address such as info@contoso.com.
  
- When you use the admin center to create a group, by default users  *will not*  follow the group conversation or get meeting invitations sent to their inboxes. They'll need to go to the group to see conversations and meetings. It's the **Send copies of group conversations and events to the group members' inboxes** option. If you're group will have a lot of meetings, users may not get meeting requests if the don't get conversations in their inboxes. 
    
    ![Screen capture: showing create a new group.](../media/10090869-29a2-4488-a98e-5fd3e580f352.png)
  
- Also, if a user creates a group from Outlook, this isn't on by default; they have to choose **Advanced Options** \> **Send all group conversations...**. However, if you turn on **Send copies of group conversations...** for all group members, the members can choose to turn this off using the Outlook setting. 
    
    ![Choose to send group email to users inbox](../media/82b1db3e-7055-4a60-b844-e2d9784a3e3f.png)
  
These settings mean group members will get a copy of the email sent to their Outlook Inbox. They can read and delete this copy of the email and not affect anyone else. In the Group inbox, a copy of the email still exists.
  
In Outlook, they can go to the Group inbox, and opt to stop following so a copy of the email no longer goes to their inbox. They can follow again, too. They'll still be able to access the group email by going to the Group inbox in Outlook.
  
![Users can unsubscribe from a group an no longer get emails sent to their inbox.](../media/87e28a05-ac71-4261-83ef-5a422ee21eda.png)
  
## Who can delete email from the Group Inbox?

The Group owner can delete any emails from the Group Inbox, regardless of whether they were the initial author.
  
A member can delete an email conversation from the Group Inbox if they initiated it, and only using Outlook on the web (right-click the email, then click **Delete**). They can't do it from the Outlook app (Outlook 2016).
  
Let's say the Group owner sends an email to the group, and then deletes it from the Group inbox. The copy that was sent to the members' inbox won't be deleted.
  
## More customization options

- If you want your users to be able to "Send as" or "Send on behalf of" a Group in Outlook, you need to enable it in the Exchange Admin Center. See [Allow members to send as or send on behalf of an Office 365 Group](allow-members-to-send-as-or-send-on-behalf-of-group.md).
    
- If you want to allow people outside your organization (such as partners or consultants) to access groups, see [Manage guest access to Office 365 groups](https://support.office.com/article/7c713d74-a144-4eab-92e7-d50df526ff96.aspx).
    
## Choose the domain to use when creating Office 365 Groups

Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.
  
If your organization needs users to create their groups in domains other than the default accepted domain of your organization, you can allow it by configuring email address policies (EAPs) using PowerShell.
  
For instructions, see [Choose the domain to use when creating Office 365 Groups](choose-domain-to-create-groups.md).
  
## What you need to know about creating groups in the admin center

- People in the following Office 365 admin roles can create and manage groups in the admin center: global admin, Exchange admin, user management admin.
    
- You need an Exchange Online license at minimum (for example, if you don't have an Office 365 business license).
    
- Office 365 Groups must be enabled for your tenant. It is by default, but some organizations disable it.
    
- You can't be a delegated admin (for example, a consultant who is an admin on behalf of).
    
- If you create a security group to manage who can create Office 365 groups, the global admin does not need to be a member. They will still be able to create groups from the admin center. However, they won't be able to create groups from the apps (such as Planner, Outlook). To learn more, see [Manage who can create Office 365 Groups](manage-creation-of-groups.md).
    
- The Group ID is used to determine the alias (also known as the mailNickname) in Exchange. The mailNickname property must be unique across all Office 365 Groups within a tenant.
    
## Articles about managing Office 365 Groups

- [Manage Group membership in the Office 365 admin center](add-or-remove-members-from-groups.md)
    
- [Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540): this article introduces you to key cmdlets and provides examples
    
- [Upgrade distribution lists to Office 365 Groups in Outlook](../manage/upgrade-distribution-lists.md)
    
- [Why you should upgrade your distribution lists to groups in Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)
    
    
- [Manage guest access to Office 365 Groups](https://support.office.com/article/7c713d74-a144-4eab-92e7-d50df526ff96.aspx)
    
- [Create a Distribution Group Naming Policy](https://go.microsoft.com/fwlink/p/?LinkId=616615)
    
- [Create and manage distribution groups in the Exchange admin center](https://technet.microsoft.com/en-us/library/bb124513%28v=exchg.150%29.aspx)
    


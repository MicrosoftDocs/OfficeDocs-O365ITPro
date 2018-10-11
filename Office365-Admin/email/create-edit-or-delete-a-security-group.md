---
title: "Create, edit, or delete a security group in the Office 365 admin center"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_mdmsetupwhatissg'
- 'O365P_ESSecurityGroupSPO'
- 'O365M_mdmsetupwhatissg'
- 'O365M_ESSecurityGroupSPO'
- 'O365M_CreateSecurityGroup'
- 'O365E_mdmsetupwhatissg'
- 'O365E_ESSecurityGroupSPO'
- 'O365E_CreateSecurityGroup'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: "Learn to create, edit,or delete a security group in Office 365. 
"
---

# Create, edit, or delete a security group in the Office 365 admin center

On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online. For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site. Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users-2/assign-admin-roles.md). 
  
There are also [Groups in Exchange Online and SharePoint Online](create-edit-or-delete-a-security-group.md#__groups_in_exchange) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](create-edit-or-delete-a-security-group.md#__groups_in_exchange) that grant users rights and access to sites and site collections. 
  
> [!IMPORTANT]
>  Planning on using site mailboxes? All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint. These users won't be able to access the site mailbox from Outlook. For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx). 
  
## Manage security groups in the Office 365 admin center
<a name="BK_Preview"> </a>

### Add a security group

1. Navigate to **Groups** \> **Groups**.
    
    > [!TIP]
    > You can also enter text similar to add security group into the Tell me what you want to do ... search box and the **New Group** dialog will open if you choose **Add a group** from the Tasks list. 
  
![In the admin center preview choose Groups and then Groups](../media/bb083666-22f7-41c1-b9d8-2b4a878118c4.png)
  
2. On the **Groups** page, choose **Add a group**.
    
3. In the **Type** drop-down, choose Security group 
    
4. Type a name and description for the group, and then choose **Add** \> **Close**. 
    
5. To add members, select the Security group on the **Groups** page and choose ** Edit members ** on the ** Bulk actions for groups selected ** dialog. 
    
    Type the name of the person you want to add in the **Search** box and then choose **Add**.
    
    To remove members choose **Remove** next to their name. 
    
### Edit a security group

1. Navigate to **Groups** \> **Groups**.
    
    > [!TIP]
    > You can also enter text similar to add security group into the Tell me what you want to do ... search box and the **New Group** dialog will open if you choose **Add a group** from the Tasks list. 
  
![In the admin center choose Groups](../media/bb083666-22f7-41c1-b9d8-2b4a878118c4.png)
  
2. On the **Groups** page, select a group, or select multiple groups by selecting the check box next to the Group names. 
    
3. Choose **Edit** in the **Security group** dialog to edit either **Members** or **Details**.
    
    You can edit the security group name and description in the **Details**.
    
4. After you've made changes on the **Details** or **Members** pages, choose **Save and close**.
    
### Delete a security group

1. Navigate to **Groups** \> **Groups**.
    
    > [!TIP]
    > You can also enter text similar to add security group into the **Tell me what you want to do ...** search box and the **New Group** dialog will open if you choose **Add a group** from the Tasks list. 
  
![In the admin center choose Groups](../media/bb083666-22f7-41c1-b9d8-2b4a878118c4.png)
  
2. On the **Groups** page, select a group by clicking on its name. 
    
3. In the **Security group** dialog, choose **Delete group** \> **Delete**.
    
    Choose **Close** once the group is deleted. 
    
## Groups in Exchange Online and SharePoint Online
<a name="__groups_in_exchange"> </a>

If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by clicking **Admin** \> **Exchange** \> **Recipients** \> **Groups**. Next, click **New**![Add](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create: 
  
- **Distribution group**: Used to distribute messages to a group of users. It's also called a  *mail-enabled distribution group*  , or, in Office 365, a  *distribution list*  . For more information, see [Manage Distribution Groups](https://technet.microsoft.com/library/bb124513.aspx).
    
- **Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources. This group is also called a  *mail-enabled security group*  . For more information, see [Manage Mail-Enabled Security Groups](https://technet.microsoft.com/library/bb123521.aspx).
    
- **Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define. For more information, see [Manage Dynamic Distribution Groups](https://technet.microsoft.com/library/bb123722.aspx).
    
After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page. 
  
 SharePoint groups are created automatically when you make a site collection. The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access. For more information, see [Default SharePoint Groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).
  
## How is an Office 365 security group different from security groups I create in SharePoint?
<a name="__groups_in_exchange"> </a>

Office 365 security groups can be used with SharePoint, Exchange, MDM, Windows, and more. A security group you create in SharePoint is only recognized by that SharePoint site collection.
  
## Do I have to use Office 365 security groups for my organization to be secure?
<a name="__groups_in_exchange"> </a>

No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.
  
## Can I send email to an Office 365 security group?
<a name="__groups_in_exchange"> </a>

Yes. But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead. 
  


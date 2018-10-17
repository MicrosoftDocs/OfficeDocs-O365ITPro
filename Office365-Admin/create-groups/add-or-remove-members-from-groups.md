---
title: "Add or remove members from Office 365 groups using the Office 365 admin center"
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
- BSA160
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: "Learn how to add a member to a group, remove member from group, and manage group owner status in the Office 365 admin center."
---

# Add or remove members from Office 365 groups using the Office 365 admin center
  
In Office 365, Group members typically create their own Groups, add themselves to Groups they want to join, or are invited by Group owners. If Group ownership changes, or if you determine that a member should be added or removed, as the admin you can also make that change. [What is an Office 365 Group?](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)
  
 **Tip**: You can also [add or remove members using Outlook](https://support.office.com/article/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de.aspx). 
  
## Add a member to a Group in the Office 365 admin center
<a name="AddMemberPreview"> </a>

1. Sign in to Office 365 using your global admin or Exchange admin account. Browse to the Office 365 admin center. If you're not an admin, you can [add or remove members using Outlook](https://support.office.com/article/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de.aspx). 
    
2. In the left navigation pane, choose **Groups** \> **Groups**.
    
3. Select a Group.
    
4. In the details pane, next to **Members**, click **Edit**.
    
    ![Screen shot with Edit members link highlighted](../media/9a47d6bf-850e-45e6-8aa7-a0c4da878234.png)
  
5. Search for or select the name of the member you want to add.
    
6. Click **Save**.
    
## Remove a member from a Group in the Office 365 admin center
<a name="RemoveMemberPreview"> </a>

> [!NOTE]
> When you remove a member from a private group, it takes 5 minutes for the person to be blocked from the group (after membership changes are fully replicated among domain controllers). 
  
1. Browse to the Office 365 admin center.
    
2. In the left navigation pane, choose **Groups** \> **Groups**.
    
3. Select a Group.
    
4. In the details pane, next to **Members**, click **Edit**.
    
5. Next to the member you want to remove, click **Remove**.
    
6. Click **Save** to remove the member. 
    
## Manage Group owner status
<a name="ManageGroupAdmins"> </a>

By default, the person who created the group is the group owner. Often a group will have multiple owners for backup support or other reasons. Members can be promoted to owner status and owners can be demoted to member status.
  
### Promote a member to owner status in the Office 365 admin center
<a name="PromoteAMemberPreview"> </a>

1. Navigate to the Office 365 admin center.
    
2. In the left navigation pane, choose **Groups** \> **Groups**.
    
3. Select a Group.
    
4. In the **Bulk actions** pane at the right of the screen, click **Edit owners**.
    
5. Search for or select the name of the member you want to add.
    
6. Click **Add** next to the member's name. 
    
7. Click **Save**.
    
### Remove owner status in the Office 365 admin center
<a name="RemoveOwnerPreview"> </a>

1. Navigate to the Office 365 admin center.
    
2. In the left navigation pane, choose **Groups** \> **Groups**.
    
3. Select a Group.
    
4. In the details pane at the right of the screen, click **Edit Owners**.
    
5. Click **Remove** next to the owner's name. 
    
6. Click **Save**.
    
## More on managing membership
<a name="ManageGroupAdmins"> </a>

- [Manage groups dynamically in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): see the section "How can I manage the membership of a group dynamically?"
    
- To add hundreds or thousands of users to Office 365 groups, use the [Add-UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191).
    
- [Control guest access to Office 365 Groups](https://support.office.com/article/7c713d74-a144-4eab-92e7-d50df526ff96.aspx)
    
- [Manage guest access in admin portal](https://support.office.com/article/53abaec2-d84c-4f74-bfeb-f0867456c39e.aspx)
    
- [Assign a new owner to an orphaned group](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732.aspx)
    
## Articles about managing groups
<a name="ManageGroupAdmins"> </a>

- [Create an Office 365 group in the admin center](create-groups.md)
    
- [Upgrade distribution lists to Office 365 Groups in Outlook](../manage/upgrade-distribution-lists.md)
    
- [Why you should upgrade your distribution lists to groups in Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)
    
- [Manage who can create Office 365 Groups in your organization](manage-creation-of-groups.md)
    
- [Manage guest access to Office 365 Groups](https://support.office.com/article/7c713d74-a144-4eab-92e7-d50df526ff96.aspx)
    
- [Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540): this article introduces you to key cmdlets and provides examples
    
- [Multi-domain support for Office 365 groups](choose-domain-to-create-groups.md)
    
- [Create a Distribution Group Naming Policy](https://go.microsoft.com/fwlink/p/?LinkId=616615)
    


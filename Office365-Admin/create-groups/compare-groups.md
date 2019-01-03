---
title: "Compare groups"
ms.author: dianef
author: dianef77
manager: mnirkhe
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365P_TypesOfGroups'
- 'O365P_ESTypesOfGroups'
- 'O365M_TypesOfGroups'
- 'O365M_ESTypesOfGroups'
- 'O365E_TypesOfGroups'
- 'O365E_ESTypesOfGroups'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_UI_Elements
ms.custom:
- Core_O365Admin_Migration
- EmptyState
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: "Create and manage Office 365 groups, shared mailboxes, security groups, and distribution lists."
---

# Compare groups

  
## What to create: Office 365 groups, shared mailboxes, security groups, and distribution lists

In the **Groups** section of the Office 365 admin center, you can create and manage these types of groups: 
  
|||
|:-----|:-----|
|**Option** <br/> |**When to choose** <br/> |
|**Office 365 group**  <br/> |[Create an Office 365 group](create-groups.md) when you want to give people a place to collaborate. When you create a group, you automatically give its members permissions to a shared mailbox, calendar, files, SharePoint site, and more. [Learn about Office 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx).  <br/><br/>   You can also create a group if you want an email address like info@contoso.com.  <br/> <br/>  Advantages of groups:  <br/>  <ul><li>They are easy to create! Users [create them in Outlook](https://support.office.com/article/7124dc4c-1de9-40d4-b096-e8add19209e9.aspx). Admins [create them in the admin center](create-groups.md).  <br/>  You can grant guests outside of your company access to the groups. For example, a partner with a Gmail address. To learn more, see [Guest access in Office 365 Groups](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6.aspx)</li><li> Users can use their mobile device to access/manage email sent to the group. </li><li> People outside your organization can email the group. So you can have an address like info@contoso.com.  </li><li>Messages sent to the group are preserved for everyone, even if one person "deletes" the message after reading it in their Outlook inbox. Only a Group owner can delete a message from the Group inbox. See [How following group email works](create-groups.md#how-following-group-email-works).  </li><li>User's can subscribe and unsubscribe to group email, notifications, etc. See [How following group email works](create-groups.md#how-following-group-email-works).  </li> </ul> Two drawbacks, at least compared to shared mailboxes: If you decide to use a group for something like info@contoso.com ...  <ul><li>You can allow group members to [reply as the group address](allow-members-to-send-as-or-send-on-behalf-of-group.md) instead of their personal email address. BUT, it doesn't do it by default. You have to remind your users to always choose Send As the group mailbox.  </li><li>After you create the group, you have to enable it to [Let people outside the organization email the group](create-groups.md#let-people-outside-the-organization-email-the-group) to your business. </li></ul> <br/> |
|**Shared mailboxes**  <br/> |[Create a shared mailbox](../email/create-a-shared-mailbox.md) when you want a group of people to monitor and send email from a common email address, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.   <br/><br/>Notable benefits of shared mailboxes:  <ul><li>You don't need to assign licenses to mailboxes that are under 50 GB.  </li><li> Users can reply as the shared mailbox address instead of their personal email address.  </li><li> Shared mailboxes include a shared calendar. If you're a small business and you need to keep track of what appointments people are on, this is a good way for everyone to be informed.  </li><li> You can [convert user mailboxes to shared mailboxes](../email/convert-user-mailbox-to-shared-mailbox.md). </li> </ul>  <br/>  A few drawbacks:  <br/> <ul><li> You can't access a shared mailbox from Outlook for iPhone, Android, or Mac. If you want to access a shared mailbox from one of these devices, open a browser and go to Outlook on the web.   </li><li>Unlike Office 365 Groups, only members inside your organization can read or reply to email sent to a shared mailbox. You can't add a partner who has a Gmail address, for example, as a member of a shared mailbox.   </li><li>Say you have 5 people sharing a mailbox. One of them deletes a message after reading it. Now it's been deleted for the other 4 people too, even though they hadn't read the message. To avoid this scenario, use Groups instead; read the section on [How following group email works](create-groups.md#how-following-group-email-works).  <br/> |
|**Distribution list**  <br/> |It's better to create an Office 365 group than a distribution list. The only reason to create a DL now is if your organization has Groups disabled.  <br/><br/> You can [upgrade existing distribution lists to Office 365 Groups in Outlook](../manage/upgrade-distribution-lists.md).  <br/> |
|**Security group**  <br/> |[Create a security group](../email/create-edit-or-delete-a-security-group.md) when you want to grant access permissions to a group of users. For example, you could create a group of designers for a SharePoint Online site and then assign read/write permissions to that group. Everyone in the group will be able to view and edit the site.  <br/><br/> Another example is when setting up mobile device management (MDM), a security group is created for the security policy. Assigning permissions to groups is much faster and more efficient than assigning permissions to individual users one at a time.  <br/><br/> If you have hundreds or thousands of users you're managing, you might be interested in using a security group to assign licenses. See [Assign licenses to users by group membership in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=856227).  <br/> |
|**Mail-enabled security group**  <br/> |If you mail-enable the security group, you can send e-mail to all members of that group. For example, if you create a security group that gives members access to the computers in a specific server lab, you may want to send mail to that group to notify them of a power outage in the lab.  <br/><br/> **Note:** You have to assign Exchange Online licenses to all users who you want to add to a mail-enabled security group.  <br/> <br/>To learn more, see [Manage mail-enabled security groups](https://go.microsoft.com/fwlink/?linkid=856228).  <br/> |
   
> [!Important]
> Currently it's not possible to migrate a shared mailbox to an Office 365 Group. Is this something you want? Let us know. **[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)** ! 
  
We use your feedback to prioritize which features we work on. 
  
## More articles about managing groups

    
- [Plan for governance in Office 365 Groups](Plan-for-groups-governance.md)]
- [Upgrade distribution lists to Office 365 Groups in Outlook](../manage/upgrade-distribution-lists.md)
    
- [Why you should upgrade your distribution lists to groups in Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)
    
- [Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540): this article introduces you to key cmdlets and provides examples
    
- [Create a Distribution Group Naming Policy](https://go.microsoft.com/fwlink/p/?LinkId=616615)
    
- [Manage dynamic distribution groups](https://technet.microsoft.com/en-us/library/bb123722%28v=exchg.150%29.aspx)
    
- [Public folders in Office 365 and Exchange Online](https://technet.microsoft.com/en-us/library/jj200758%28v=exchg.150%29.aspx)
    


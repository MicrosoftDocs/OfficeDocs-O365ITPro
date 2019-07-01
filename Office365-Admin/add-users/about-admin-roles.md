---
title: "About admin roles in the Microsoft 365 admin center"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: overview
f1_keywords:
- 'O365P_AssignAdminRoles'
- 'O365M_AssignAdminRoles'
- 'O365E_AssignAdminRoles'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Top
- Core_O365Admin_Migration
- MiniMaven
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: "Admin roles map to business functions and give permissions to do specific tasks in the admin center. For example, the Service admin opens support tickets with Microsoft.."
---

# About admin roles

Your subscription comes with a set of admin roles that you can [assign](assign-admin-roles.md) to users in your organization. Each admin role maps to common business functions and gives people in your organization permissions to do specific tasks in the Microsoft 365 admin center. 

Go to Roles
  
## Things to consider...

Because admins have access to sensitive data and files, we recommend that you follow these guidelines to keep your organization's data more secure.

| Recommendation                  | Why is this important?                 | 
| :------------------- | :------------------- |
| Have 2 to 4 global admins  | Because only another global admin can reset a global admin's password, we recommend that you have at least 2 global admins in your organization in case of account lockout. But the global admin has almost unlimited access to your org's settings and most of the data, so we also recommend that you don't have more than 4 global admins because that's a security threat. |
| Assign the *least permissive* role              | Assigning the *least permissive* role means giving admins only the access they need to get the job done. For example, if you want someone to reset employee passwords you shouldn't assign the unlimited global admin role, you should assign a limited admin role, like Password admin or Helpdesk admin.  This will help keep your data secure.                 |
| Require multi-factor authentication for admins                  |    It's actually a good idea to require MFA for all of your users, but admins should definitely be required to use MFA to sign in. MFA makes users enter a second method of identification to verify they are who they say they are. Admins potentially have access to a lot of customer and employee data and if you require MFA, even if the admin's password gets compromised, the password is useless without the second form of identification.  When you turn on MFA, the next time the user signs in, they'll need to provide an alternate email address and phone number for account recovery.  <br> [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)          | 
 
## Need more details about what these roles can and cannot do?

In the Microsoft 365 admin center, go to **Roles** > **Roles**, and then select any role to open its detail pane. Select the **Permissions** tab to view the detailed list of what admins assigned that role have permission to do.

If you don’t have access to the Microsoft 365 admin center, or if you’re looking for the cmdlets associated with a role, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
## What about the Azure Active Directory roles?

If you have a large business, there might be roles in Azure Active Directory that will meet your organizational needs, too. A user who is assigned an admin role will have the same permissions across all of the cloud services that your organization has subscribed to, regardless of whether you assign the role in the Microsoft 365 admin center, or in the Azure portal, or by using the Azure AD module for Windows PowerShell.
  
For a list and description of all the Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
## What can the admin roles do in Exchange, SharePoint, and Teams or Skype for Business?

Certain admin roles have a corresponding role in Exchange, SharePoint, and Skype for Business. The table below describes how these roles available in the Microsoft 365 admin center translate into roles in the different Microsoft services.
  
|**Admin role in the Microsoft 365 admin center**|**Translates to this in Exchange Online …**|**Translates to this in SharePoint Online …**|**Translates to this in Skype for Business Online.....**|**Translates to this in the Security &amp; Compliance Center...**|
|:-----|:-----|:-----|:-----|:-----|
|global admin  <br/> |Exchange Online admin  <br/> Company admin  <br/> |SharePoint Online admin  <br/> |Skype for Business admin  <br/> |Security &amp; Compliance Center admin (member of Organization Management role group)  <br/> |
|billing admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|helpdesk <br/> |Help Desk admin\*  <br/> |N/A  <br/> |Help desk admin  <br/> |N/A  <br/> |
|service admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|user admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|Exchange admin  <br/> |Exchange Online admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|SharePoint admin  <br/> |N/A  <br/> |SharePoint Online admin  <br/> |N/A  <br/> |N/A  <br/> |
|Skype for Business administrator  <br/> |N/A  <br/> |N/A  <br/> |Skype for Business admin  <br/> |N/A  <br/> |
|Compliance administrator  <br/> |Organization Management  <br/> |N/A  <br/> |N/A  <br/> |Compliance admin  <br/> |
   
\*People with the helpdesk admin role can do the same tasks as people with the Exchange Help Desk role, however, they can't do message trace.
  
## Delegated administration

If you're working with a Microsoft partner, you can assign them admin roles. They, in turn, can assign users in your company - or their company - admin roles. You might want them to do this, for example, if they are setting up and managing your online organization for you.
  
A partner can assign these roles:
  
- Full administration, which has privileges equivalent to a global admin.
    
- Limited administration, which has privileges equivalent to a helpdesk admin.
    
Before the partner can assign these roles to users, you must add the partner as a delegated admin to your account. This process is initiated by an authorized partner. The partner sends you an email to ask you if you want to give them permission to act as a delegated admin. For instructions, see [Authorize or remove partner relationships](https://support.office.com/article/201ccb3b-6011-4bf1-a6b2-84e7cc1ee2d0.aspx).
  
## Related articles

[Assign admin roles in Office 365](assign-admin-roles.md)
  
[Activity reports in the Microsoft 365 admin center](../activity-reports/activity-reports.md)
  


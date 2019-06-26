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
  
Here are the available roles and what people assigned to them can do.
  
> [!TIP]
> For a detailed list of permission for each of these roles, go to **Roles** > **Roles**, select a role, and then the **Permissions** tab. <br> <br>You can also see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).

## Things to consider...
Because admins have access to customer and employee data and files, we recommend that you follow these guidelines to keep your organization and your customer's data more secure.

| Recommendation                  | Why is this important?                 | 
| :------------------- | :------------------- |
| Have 2 to 4 global admins  | Because only another global admin can reset a global admin's password, we recommend that you have at least 2 global admins in your organization in case of account lockout. But the global admin has almost unlimited access to your org's settings and most of the data, so we also recommend that you don't have more than 4 global admins because that's a security threat. |
| Assign the *least permissive role*                | Assigning the *least permissive role* means giving admins only the access they need to get the job done. For example, if you want someone to reset employee passwords you shouldn't assign the unlimited global admin role, you should assign a limited admin role, like Password admin or Helpdesk admin.  This will help keep your data secure.                 |
| Require multi-factor authentication for admins                  |    It's actually a good idea to require MFA for all of your users, but admins should definitely be required to use MFA to sign in. MFA makes users enter a second method of identification to verify they are who they say they are. Admins potentially have access to a lot of customer and employee data and if you require MFA, even if the admin's password gets compromised, the password is useless without the second form of identification.  When you turn on MFA, the next time the user signs in, they'll need to provide an alternate email address and phone number for account recovery.              | 



## Admin roles
|||
|:-----|:-----|
|**Role** <br/> |**Has access to** <br/> |
|**Global admin** <br/> |Access to all admin features in the for Office 365 and Microsoft 365 suite of services in your plan, including Skype for Business and Teams. By default, the person who signs up to buy Office 365 becomes a global admin.  <br/> Global admins are the only admins who can assign other admin roles, and only global admins can manage the accounts of other global admins. You can have more than one global admin in your organization. **As a best practice**, we recommend that only a few people in your company have this role. It reduces the risk to your business.  <br/><br/> **Tip:** Make sure everyone who is a global admin in your organization has a mobile phone number and alternate email address in their contact info. Check out [Change your organization's address, technical contact email, and other information](../manage/change-address-contact-and-more.md) for more details.  <br/> |
|**Azure Information Protection admin** <br/> |Users with this role have all permissions in the Azure Information Protection service. This role allows configuring labels for the Azure Information Protection policy, managing protection templates, and activating protection. This role does not grant any permissions in Identity Protection Center, Privileged Identity Management, Microsoft 365 admin center Service Health, or the Security and Compliance centers.  <br/> |
|**Billing admin** <br/> |Makes purchases, manages subscriptions, opens and manages support tickets, and monitors service health.  <br/> |
|**Cloud application admin** <br/> |Users in this role have the same permissions as the Application Administrator role, excluding the ability to manage application proxy. This role grants the ability to create and manage all aspects of enterprise applications and application registrations. This role also grants the ability to consent to delegated permissions, and application permissions excluding Microsoft Graph and Azure AD Graph. Users assigned to this role are not added as owners when creating new application registrations or enterprise applications. <br><br> **Important**: This role grants the ability to manage application credentials. Users assigned this role can add credentials to an application, and use those credentials to impersonate the application’s identity. If the application’s identity has been granted access to Azure Active Directory, such as the ability to create or update User or other objects, then a user assigned to this role could perform those actions while impersonating the application. This ability to impersonate the application’s identity may be an elevation of privilege over what the user can do via their role assignments in Azure AD. It is important to understand that assigning a user to the Cloud Application Administrator role gives them the ability to impersonate an application’s identity. |
|**Cloud device admin** <br/> |Users in this role can enable, disable, and delete devices in Azure AD and read Windows 10 BitLocker keys (if present) in the Azure portal. The role does not grant permissions to manage any other properties on the device.  <br/> |
|**Compliance admin** <br/> |Users with this role have permissions to manage compliance-related features in the Microsoft 365 compliance center, Microsoft 365 admin center, Azure, and Office 365 Security & Compliance Center. Users can also manage all features within the Exchange admin center and Teams & Skype for Business admin center and create support tickets for Azure and Microsoft 365. <br/> |
|**Compliance data admin** <br/> |Users with this role have permissions to protect and track data in the Microsoft 365 compliance center, Microsoft 365 admin center, and Azure. Users can also manage all features within the Exchange admin center, Compliance Manager, and Teams admin center and create support tickets for Azure and Microsoft 365.  <br/> |
|**Conditional access admin** <br/> |Users with this role have the ability to manage Azure Active Directory Conditional Access settings. <br><br> **Note:** To deploy the Exchange ActiveSync Conditional Access policy, the user must also be a Global admin.<br/> |
|**Customer Lockbox access approver** <br/> |Manages [Customer Lockbox](../manage/customer-lockbox-requests.md) requests in your organization. They receive email notifications for Customer Lockbox requests and can approve/deny requests from the Microsoft 365 Admin Center. They can also turn on/off the Customer Lockbox feature.  <br/><br/> This role has no access to view, create, or manage support tickets. <br/><br/>Only global admins can reset the passwords of people assigned to this role.  <br/> |
|**[Exchange admin](about-exchange-online-admin-role.md)** <br/> |Manages mailboxes and anti-spam policies for your business, using the Exchange admin center. Can view all the [activity reports](../activity-reports/activity-reports.md) in the Microsoft 365 admin center, manage support tickets, and monitor service health. <br/><br/> Someone with BOTH the Exchange admin role and the user management role can create and manage Office 365 groups.  <br/><br/> To learn more, see [About the Exchange Online admin role](about-exchange-online-admin-role.md).  <br/> |
|**Guest inviter** <br/> |Users in this role can manage Azure Active Directory B2B (business-to-business) guest user invitations when the **Members can invite users** setting is set to **No**. <br><br>For more information, see [What is guest user access in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b). <br/> |
|**Helpdesk admin** <br/> |Users in this role can reset passwords, force users to sign out by invalidating refresh tokens, create and manage service requests, and monitor service health for non-admin users and for admins assigned the Directory reader, Guest inviter, Message Center reader and Reports reader roles.  <br/> |
|**Intune admin** <br/> |Users with this role have global permissions within Microsoft Intune, when the service is present. Additionally, this role contains the ability to manage users and devices in order to associate policy, as well as create and manage groups. <br><br> For more information, see [Role-based access control with Intune](https://docs.microsoft.com/intune/role-based-access-control) <br/> |
|**Kaizala admin** <br/> |Users with this role have full access to Microsoft Kaizala, when the service is present, as well as the ability to manage support tickets and monitor service health. Additionally, the user can access reports related to adoption & usage of Kaizala by organization members and business reports generated using the Kaizala actions.  <br/> |
|**License admin** <br/> |Adds, removes, and updates license assignments for users, groups (using group-based licensing), and manages the usage location of users.  <br/><br/> People in this role can't purchase or manage subscriptions, create or manage groups, or create or manage users beyond the usage location.  <br/><br/>This role has no access to view, create, or manage support tickets. <br/> |
|**Local device admin** <br/> |Users assigned this role become local device admins on all Windows 10 devices joined to Azure AD.  <br/> |
|**Power BI admin** <br/> |A person assigned to the Power BI admin role will have access to Office 365 Power BI usage metrics. They'll also be able to control your organization's usage of Power BI features. To learn more about administering Power BI, see [Administering Power BI in your organization](https://go.microsoft.com/fwlink/p/?LinkId=842955).  <br/> |
|**Reports reader** <br/> |Can view all the [activity reports](../activity-reports/activity-reports.md) in the Microsoft 365 admin center and any reports exposed through the reporting APIs.  <br/> |
|**Message Center privacy reader** <br/> |If your org is affected by a data breach, you'll get an email notification and notifications in the Message Center. Users with this role can view data privacy related posts in the Message center. The Message Center Privacy reader and the global admin can see all notifications in the Message center, but they are the only users who will see messages related to data privacy. <br/> <br/>  By default we also send an email notification for data privacy messages to users assigned the Message Center privacy reader and global admin roles. Each admin can turn off this option by setting their [Message Center preferences](../manage/message-center.md#set-preferences). The email doesn't include any details about the breach only that it can be viewed in the Message center. <br/> <br/>If your organization needs to comply with GDPR or HIPAA regulations, we recommend that the person assigned to this role also be responsible for overseeing your organization's data protection strategy and GDPR/HIPAA compliance implementation. <br><br> Users assigned this role also have read-only access to some admin center resources, such as users, groups, domains, and subscriptions. This role has no access to view, create, or manage support tickets.<br/> <br/>  |
|**Message Center reader** <br/> |Monitors changes to the service and can view all posts to the [Message center in Office 365](../manage/message-center.md) and share Message center posts with others through email. People assigned this role also have read-only access to some admin center resources, such as users, groups, domains, and subscriptions.  <br/> |
|**Password admin** <br/> |Users in this role can reset passwords for non-admin users and users assigned the Directory reader, Guest inviter, and Password admin roles. <br><br> **Important:** Password admins can change passwords for people who might have access to sensitive, private, or critical information. Changing the password of a user provides the potential to assume that user's identity and permissions. <br/> |
|**Power BI admin** <br/> |Users in this role can manage all admin features in Microsoft Power BI, open and manage service requests, and monitor service health.  <br/> |
|**Printer admin** <br/> |Assign this role to users who need to register and unregister printers, configure printer access permissions, set default printer preferences, view and manage printer status and print queues, and accept admin consent privileges on behalf of others in your org.  <br/> |
|**Printer tech** <br/> | Printer techs can register and unregister printers, update basic printer settings, and read all printer and connector properties. <br/> |
|**Privileged role admin** <br/> |Users with this role can manage role assignments in Azure Active Directory, as well as within Azure AD Privileged Identity Management. In addition, this role allows management of all aspects of Privileged Identity Management and administrative units. <br><br>**Important:** This role grants the ability to manage assignments for all Azure AD roles including the Global Administrator role. This role does not include any other privileged abilities in Azure AD like creating or updating users. However, users assigned to this role can grant themselves or others additional privilege by assigning additional roles.  <br/> |
|**Reports reader** <br/> | Users with this role can view usage data and the activity reports in the Microsoft 365 admin center, the Power BI adoption content pack, Azure AD sign-in reports, and data returned by Microsoft Graph reporting API.   <br/> |
|**Search admin** <br/> |Has full access to all Microsoft Search management features in the Microsoft 365 admin center. Search admins can delegate the Search admin and Search editor roles to users, and create and manage content, like bookmarks, Q&A, and locations. Additionally, these users can view the message center, monitor service health, and create service requests. <br/> |
|**Search editor** <br/> |Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center, including bookmarks, Q&As, and locations. <br/> |
|**Security and Compliance centers roles** <br/> |If you have an Microsoft 365 or Office 365 E3 or E5 business subscription, it includes security and compliance tools. In that case, you have access to these additional roles: eDiscovery Manager, Organization management, Reviewer, Service Assurance User, Supervisory Review.  <br/><br/> To learn more about them, see [Permissions in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).  <br/> |
|**Security admin** <br/> |Users with this role can create and manage security policies, review security policies and reports, and monitor the threat landscape.  <br/> |
|**Security reader** <br/> | Assign this role to users who need to view security-related features in the Security center, Azure AD Identity Protection, and Privileged Identity Management, but not edit any settings. Security readers can also view Azure AD sign-in reports and audit logs. <br/> |
|**Service admin** <br/> |Opens support tickets with Microsoft and views the service dashboard and message center. They have "view only" permissions except for opening support tickets and reading them.  <br/><br/> **Tip:** People who are assigned to the Exchange admin, SharePoint admin, and Skype for Business admin roles should also be assigned to the Service admin role. This way they can see important information in the Microsoft 365 admin center, such as the health of the service, and change and release notifications.  <br/> |
|**[SharePoint admin](https://support.office.com/article/f08144d5-9d50-4922-8e77-4e1a27b40705.aspx)** <br/> |Manages file storage for your organization in SharePoint and OneDrive. They do this in the SharePoint admin center. They can also assign other people to be site collection administrators and term store administrators.  <br/><br/> Permissions assigned to SharePoint sites are completely separate from the these roles. You can be a global admin without access to a SharePoint site if you weren't added to it or didn't create the site.  <br/><br/> People in this role can also view all the [activity reports](../activity-reports/activity-reports.md) in the Microsoft 365 admin center, create and manage all Office 365 groups, open and manage service requests, and monitor service health.  <br/><br/> To learn more, see [About the SharePoint admin role](https://support.office.com/article/f08144d5-9d50-4922-8e77-4e1a27b40705.aspx).  <br/> |
|**[Skype for Business admin](https://support.office.com/article/aeb35bda-93fc-49b1-ac2c-c74fbeb737b5)** <br/> |Configures Skype for Business for your organization and can view all the [activity reports](../activity-reports/activity-reports.md) in the Microsoft 365 admin center. Can open and manage support tickets. <br/><br/> To learn more, see [About the Skype for Business admin role](https://support.office.com/article/aeb35bda-93fc-49b1-ac2c-c74fbeb737b5).  <br/> |
|**Teams admin** <br/> |Can manage all aspects of Microsoft Teams except license assignment. This includes policies for calling, messaging, and meetings; use of call analytics tools to troubleshoot telephony issues, and management of users and their telephony settings.  This role additionally grants the ability to create and manage all Office 365 Groups, manage support tickets, and monitor service health. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**Teams communications admin** <br/> |Can manage calling and meeting features of Microsoft Teams, including phone number assignments and meeting policies. They can also use call analytics tools to troubleshoot issues. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**Teams communications support engineer** <br/> |Can troubleshoot communication issues in Teams using call analytics tools, and can view full call record information for all participants involved. <br/><br/>This role has no access to view, create, or manage support tickets. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**Teams communications support specialist** <br/> |Can troubleshoot communication issues in Teams using call analytics tools, and can view call record information for the specific user being searched for. <br/><br/>This role has no access to view, create, or manage support tickets. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**User admin** <br/> |Resets passwords, monitors service health, adds and deletes user accounts, manages support tickets, adds and removes members from Office 365 groups. The user management admin can't delete a global admin, create other admin roles, or reset passwords for global, billing, Exchange, SharePoint, Compliance, and Skype for Business admins. This role also includes the ability to update license assignments for users and for groups (using group-based licensing), and manage the usage location of users. <br/><br/> Someone with BOTH the Exchange admin role and the user management role can create and manage Office 365 groups in the Microsoft 365 admin center.  <br/> |
|**Dynamics 365 admin** <br/> |When a person is assigned to the Global admin role, they are automatically assigned to the **System Administrator security role** in Dynamics 365 (online).  <br/><br/> A person assigned to the System Administrator security role in Dynamics 365 can assign other people to Dynamics 365 security roles. With the **System Administrator security role**, you can manage all aspects of Dynamics 365. To learn more, see [Manage subscriptions, licenses, and user accounts](https://technet.microsoft.com/en-us/library/jj191604.aspx).  <br/> |
| **Dynamics 365 admini** <br/> |Use this new role to assign users to manage Dynamics 365 at the tenant level without having to assign the more powerful Office 365 global admin privileges. A Dynamics 365 service admin can sign in to the Dynamics 365 admin center to manage instances. A person with this role cannot do functions restricted to the Office 365 global admin such as manage user accounts, manage subscriptions, access settings for Office 365 apps like Exchange or SharePoint.  <br/><br/> To learn more, see [Use the Dynamics 365 service admin role to manage your tenant](https://technet.microsoft.com/library/mt793847.aspx).  <br/> |

   
## Need more details about what these roles can and cannot do?

In the Microsoft 365 admin center, go to **Roles** > **Roles**, and then select any role to open its detail pane. Select the Permissions tab to view the detailed list of what admins assigned that role have permission to do.

For a detailed list of what tasks each of these roles can do, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
## What about the Azure Active Directory roles?

If you have a large business, you'll want to set roles in Azure Active Directory, too. A user who is assigned an admin role will have the same permissions across all of the cloud services that your organization has subscribed to, regardless of whether you assign the role in the Microsoft 365 admin center, or in the Azure classic portal, or by using the Azure AD module for Windows PowerShell.
  
For a list and description of all the Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
## What can the admin roles do in Exchange Online, SharePoint Online, and Skype for Business Online?

Certain admin roles have a corresponding role in Exchange, SharePoint, and Skype for Business. The table below describes how these roles available in the Microsoft 365 admin centertranslate into roles in the different Microsoft services.
  
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
  


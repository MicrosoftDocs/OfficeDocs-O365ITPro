---
title: "About Office 365 admin roles"
ms.author: dianef
author: dianef77
manager: mnirkhe
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365P_AssignAdminRoles'
- 'O365M_AssignAdminRoles'
- 'O365E_AssignAdminRoles'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
description: "Admin roles map to business functions and give permissions to do specific tasks in the admin center. For example, Service admin opens support tickets with Microsoft."
---

# About Office 365 admin roles

 
  
Office 365 comes with a set of admin roles that you can [assign](assign-admin-roles.md) to users in your organization. Each admin role maps to common business functions, and gives people in your organization permissions to do specific tasks in the Office 365 admin center. 
  
Here are the available roles and what people assigned to them can do.
  
> [!TIP]
> For a detailed list of what tasks each of these roles can and cannot do, and how they overlap with roles in other Microsoft services, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
|||
|:-----|:-----|
|**Role** <br/> |**What they do in Office 365** <br/> |
|![Global admin](../media/cbdb29d5-8d68-452a-8ccd-b337e5c86cec.png) **Global administrator** <br/> |Accesses all administrative features in the Office 365 suite of services in your plan, including Skype for Business. By default the person who signs up to buy Office 365 becomes a global admin.  <br/> Global admins are the only admins who can assign other admin roles, and only global admins can manage the accounts of other global admins. You can have more than one global admin in your organization. **As a best practice** we recommend that only a few people in your company have this role. It reduces the risk to your business.  <br/><br/> **Tip:** Make sure everyone who is a global admin in your organization has a mobile phone number and alternate email address in their contact info. Check out [Change your organization's address, technical contact email, and other information](../manage/change-address-contact-and-more.md) for more details.  <br/> |
|![Credit card](../media/d00b0009-51f5-410b-bb0b-7ab36102b03c.png) **Billing administrator** <br/> |Makes purchases, manages subscriptions, manages support tickets, and monitors service health.  <br/> |
|![Customer Lockbox access approver](../media/649cfe55-9b3f-434d-8630-01ac80a52a12.png)           <br/> **Customer Lockbox access approver** <br/> |Manages [Customer Lockbox](../manage/customer-lockbox-requests.md) requests in your organization. They receive email notifications for Customer Lockbox requests and can approve/deny requests from the Microsoft 365 Admin Center. They can also can turn on/off the Customer Lockbox feature.  <br/><br/> Only global admins can reset the passwords of people assigned to this role.  <br/> |
|![Exchange Online](../media/4e3ecf0d-8366-4a96-9f39-9faa46543cf3.png) **[Exchange administrator](about-exchange-online-admin-role.md)** <br/> |Manages mailboxes and anti-spam policies for your business, using the Exchange admin center. Can view all the [activity reports](../activity-reports/activity-reports.md) in the Office 365 admin center.  <br/><br/> Someone with BOTH the Exchange admin role and the user management role can create and manage Office 365 groups in the Office 365 admin center.  <br/><br/> To learn more, see [About the Exchange Online admin role](about-exchange-online-admin-role.md).  <br/> |
|![Credit card](../media/d00b0009-51f5-410b-bb0b-7ab36102b03c.png) **License administrator** <br/> |Adds, removes, and updates license assignments for users, groups (using group based licensing), and manages the usage location of users.  <br/><br/> People in this role can't purchase or manage subscriptions, create or manage groups, or create or manage users beyond the usage location.  <br/> |
|![Key, permissions](../media/3bacb7b2-49c1-4f61-81a4-4e55769ed149.png) **Password administrator** <br/> |Resets passwords, manages support tickets, and monitors service health. Password admins are limited to resetting passwords for users.  <br/> |
|**Power BI administrator** <br/> |A person assigned to the Power BI admin role will have access to Office 365 Power BI usage metrics. They'll also be able to control your organization's usage of Power BI features. For more information about administering Power BI, see [Administering Power BI in your organization](https://go.microsoft.com/fwlink/p/?LinkId=842955).  <br/> |
|![Reporting reader admin](../media/9370edc6-4a93-48d3-b829-c826db15813a.png) **Reports reader** <br/> |Can view all the [activity reports](../activity-reports/activity-reports.md) in the Office 365 admin center and any reports exposed through the reporting APIs.  <br/> |
|**Message Center reader** <br/> |Monitors changes to the service and can view all posts to the [Message center in Office 365](../manage/message-center.md) and share Message center posts with others through email. Users assigned this role also have read-only access to some admin center resources, such as users, groups, domains, and subscriptions  <br/> |
|**Security and Compliance center roles** <br/> |If you have an Office 365 E3 or E5 business subscription, it includes security and compliance tools. In that case, you have access to these additional roles: Compliance administrator, eDiscovery Manager, Organization management, Reviewer, Security Administrator, Security Reader, Service Assurance User, Supervisory Review.  <br/><br/> To learn more about them, see [Permissions in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).  <br/> |
|![Headset](../media/296dc11d-9974-4a19-b551-1acdb94a65ec.png) **Service administrator** <br/> |Opens support tickets with Microsoft, and views the service dashboard and message center. They have "view only" permissions except for opening support tickets and reading them.  <br/><br/> **Tip:** People who are assigned to the Exchange Online, SharePoint Online, and Skype for Business admin roles should also be assigned to the Service admin role. This way they can see important information in the Office 365 admin center, such as the health of the service, and change and release notifications.  <br/> |
|![SharePoint admin](../media/7c4a9fc4-27bb-4a14-bc2f-31c3e2f09ff9.png) **[SharePoint administrator](https://support.office.com/article/f08144d5-9d50-4922-8e77-4e1a27b40705.aspx)** <br/> |Manages file storage for your organization in SharePoint Online and OneDrive. They do this in the SharePoint admin center. They can also assign other people to be site collection administrators and term store administrators.  <br/><br/> Permissions assigned to SharePoint sites are completely separate from the Office 365 global admin role. You can be a global admin without access to a SharePoint site if you weren't added to it or didn't create the site.  <br/><br/> People in this role can also can view all the [activity reports](../activity-reports/activity-reports.md) in the Office 365 admin center.  <br/><br/> To learn more, see [About the SharePoint admin role](https://support.office.com/article/f08144d5-9d50-4922-8e77-4e1a27b40705.aspx).  <br/> |
|![Skype for Business Online](../media/837fa4b8-4f62-4ff2-b664-53167e941a4d.png) **[Skype for Business admin](https://support.office.com/article/aeb35bda-93fc-49b1-ac2c-c74fbeb737b5)** <br/> |Configures Skype for Business for your organization and can view all the [activity reports](../activity-reports/activity-reports.md) in the Office 365 admin center.  <br/><br/> To learn more, see [About the Skype for Business admin role](https://support.office.com/article/aeb35bda-93fc-49b1-ac2c-c74fbeb737b5).  <br/> |
|**Teams service admin** <br/> |Can manage all aspects of Microsoft Teams except license assignment. This includes policies for calling, messaging, and meetings; use of call analytics tools to troubleshoot telephony issues, and management of users and their telephony settings.  They can also manage Office 365 Groups. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**Teams communications admin** <br/> |Can manage calling and meeting features of Microsoft Teams, including phone number assignments and meeting policies. They can also use call analytics tools to troubleshoot issues. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**Teams communications support engineer** <br/> |Can troubleshoot communication issues in Teams using call analytics tools, and can view full call record information for all participants involved. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|**Teams communications support specialist** <br/> |Can troubleshoot communication issues in Teams using call analytics tools, and can view call record information for the specific user being searched for. To learn more, see [Use Microsoft Teams admin roles to manage Teams](/microsoftteams/using-admin-roles).  <br/> |
|![User](../media/f5d707c1-8e3a-4009-a217-452331464ed5.png) **User management administrator** <br/> |Resets passwords, monitors service health, adds and deletes user accounts, manages support tickets, adds and removes members from Office 365 groups. The user management admin can't delete a global admin, create other admin roles, or reset passwords for global, billing, Exchange, SharePoint, Compliance and Skype for Business admins.  <br/><br/> Someone with BOTH the Exchange admin role and the user management role can create and manage Office 365 groups in the Office 365 admin center.  <br/> |
|![Icon for Dynamics 365](../media/6d3a509f-c8e2-45c1-8f02-b8eb49adfd4a.png) **Dynamics 365 (online)** <br/> |When a person is assigned to the Office 365 global administrator role, they are automatically assigned to the **System Administrator security role** in Dynamics 365 (online).  <br/><br/> A person assigned to the System Administrator security role in Dynamics 365 can assign other people to Dynamics 365 security roles. With the **System Administrator security role**, you can manage all aspects of Dynamics 365. To learn more, see [Manage subscriptions, licenses, and user accounts](https://technet.microsoft.com/en-us/library/jj191604.aspx).  <br/> |
|![Icon for Dynamics 365](../media/52b7d433-f42b-4db7-911b-f252c0e8a8fb.png)           <br/> **Dynamics 365 service administrator** <br/> |Use this new role to assign users to manage Dynamics 365 at the tenant level without having to assign the more powerful Office 365 global admin privileges. A Dynamics 365 service admin can sign in to the Dynamics 365 admin center to manage instances. A person with this role cannot do functions restricted to the Office 365 global admin such as manage user accounts, manage subscriptions, access settings for Office 365 apps like Exchange or SharePoint.  <br/><br/> To learn more, see [Use the Dynamics 365 service admin role to manage your tenant](https://technet.microsoft.com/library/mt793847.aspx) to learn more.  <br/> |

   
## Need more details about what these roles can and cannot do?

For a detailed list of what tasks each of these roles can and cannot do, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
## What about the Azure Active Directory roles?

If you have a large business, you'll want to set roles in Azure Active Directory, too. A user who is assigned an admin role will have the same permissions across all of the cloud services that your organization has subscribed to, regardless of whether you assign the role in the Office 365 admin center, or in the Azure classic portal, or by using the Azure AD module for Windows PowerShell.
  
For a list and description of all the Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=862394).
  
## What can the Office 365 admin roles do in Exchange Online, SharePoint Online, and Skype for Business Online?

Certain admin roles in Office 365 have a corresponding role in Exchange Online, SharePoint Online, and Skype for Business Online. The table below describes how these Office 365 admin roles translate into roles in the different Office 365 services.
  
|**Office 365 admin role**|**Translates to this in Exchange Online …**|**Translates to this in SharePoint Online …**|**Translates to this in Skype for Business Online.....**|**Translates to this in the Security &amp; Compliance Center...**|
|:-----|:-----|:-----|:-----|:-----|
|global admin  <br/> |Exchange Online admin  <br/> Company admin  <br/> |SharePoint Online admin  <br/> |Skype for Business admin  <br/> |Security &amp; Compliance Center admin (member of OrganizationManagement role group)  <br/> |
|billing admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|password admin  <br/> |Help Desk admin\*  <br/> |N/A  <br/> |Help desk admin  <br/> |N/A  <br/> |
|service admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|user management admin  <br/> |N/A  <br/> |N/A  <br/> |Skype for Business admin  <br/> |N/A  <br/> |
|Exchange administrator  <br/> |Exchange Online admin  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |
|SharePoint administrator  <br/> |N/A  <br/> |SharePoint Online admin  <br/> |N/A  <br/> |N/A  <br/> |
|Skype for Business administrator  <br/> |N/A  <br/> |N/A  <br/> |Skype for Business admin  <br/> |N/A  <br/> |
|Compliance administrator  <br/> |Organization Management  <br/> |N/A  <br/> |N/A  <br/> |Compliance admin  <br/> |
   
\*People with the password admin role can do the same tasks as people with the Exchange Help Desk role, however, they can't do message trace.
  
## Delegated administration

If you're working with a Microsoft partner, you can assign them admin roles. They in turn can assign users in your company - or their company - admin roles. You might want them to do this, for example, if they are setting up and managing Office 365 for you.
  
A partner can assign these roles:
  
- Full administration, which has privileges equivalent to a global admin.
    
- Limited administration, which has privileges equivalent to a password admin.
    
Before the partner can assign these roles to users, you must add the partner as a delegated admin to your Office 365 account. This process is initiated by an authorized partner. The partner sends you an email to ask you if you want to give them permission to act as a delegated admin. For instructions, see [Authorize or remove partner relationships](https://support.office.com/article/201ccb3b-6011-4bf1-a6b2-84e7cc1ee2d0.aspx).
  
## Related articles

[Assign admin roles in Office 365](assign-admin-roles.md)
  
[Activity reports in the Office 365 admin center](../activity-reports/activity-reports.md)
  


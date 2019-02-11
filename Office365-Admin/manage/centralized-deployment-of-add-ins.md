---
title: "Determine if Centralized Deployment of add-ins works for your organization"
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: "Determine if your Office 365 tenant and users meet the requirements, so that you can use Centralized Deployment to deploy Office add-ins."
---

# Determine if Centralized Deployment of add-ins works for your organization

Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your Office 365 organization. If you're an Office 365 admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.
  
It can take up to 24 hours for an add-in to show up for client for all users.
  
## Requirements

Centralized deployment of add-ins requires that the users have Exchange Online, and active Exchange Online mailboxes, and Office 365 ProPlus. Specifically the following are the requirements necessary to use the Centralized Deployment feature:
  
- Your users must be using Office ProPlus 2016 on the following operating systems:
    
  - On Windows: Office build 16.0.8067 or later
    
  - On Mac: Office build 15.34.17051500 or later
    
- For Outlook they must use one of the following versions:
    
  - 2013 Click to Run version: 15.0.4819.1000 or later
    
  - 2013 MSI version: 15.0.4937.1000 or later\*
    
  - 2016 Click to Run version: 16.0.7726.5702 or later
    
  - 2016 MSI version: 16.0.4494.1000 or later\*
    
    \*In MSI version of Outlook, admin-installed add-ins will show in the appropriate ribbon in Outlook but doesn't show the add-in in 'My add-ins' section
    
- Your directory must be federated to Azure Active Directory.
    
- Your users must sign into Office 2016 using their Organizational ID.
    
- Your user's Exchange mailbox must be OAuth enabled.
    
Centralized Deployment doesn't support the following:
  
- Add-ins that target Word, Excel, or PowerPoint in Office 2013
    
- An on-premises directory service
    
- Add-in deployment to SharePoint
    
- Add-in deployment to Office Online Server
    
- Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins
    
- Deployments of Office 365 that do not include Exchange such as Office 365 Business
    
### Client requirements

The following table shows the clients that currently support the Centralized Deployment feature.
  
|**Office application**|**2016 - Windows**|**Office Online**|**2016 - Mac**|
|:-----|:-----|:-----|:-----|
|Word  <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |
|Excel  <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |
|PowerPoint  <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |
|Outlook  <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |![checkmark](../media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)           <br/> |
   
Office Online is supported for all Office 365 business plans. Office 365 ProPlus deployments are supported for desktop clients only. To use Office 365 ProPlus, a user must have an Office 365 account and been assigned a license. For more information, see [Overview of Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).
  
### Office 365 Centralized Deployment Compatibility Checker

Using the Office 365 Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint. The Compatibility Checker is not required for Outlook support. Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### Run the compatibility checker
  
1. Start an elevated PowerShell.exe window.
    
2. Run the `\<Import-Module O365CompatibilityChecker\>` command without the brackets.
    
3. Run the `\<Invoke-CompatibilityCheck\>` command without the brackets, which prompts you for  `_TenantDomain_` (for example, `TailspinToysIncorporated.onmicrosoft.com`) and  `_TenantAdmin_` credentials, and then requests consent. 
    
> [!NOTE]
> Depending on the number of users in your tenant, the checker could complete in minutes or hours. 
  
When the tool finishes running, it produces an output file in comma-separated (.csv) format. The file is saved to `C:\windows\system32` by default. The output file contains the following information:
  
- User Name
    
- User ID (User's email address)
    
- Centralized Deployment ready - If the remaining items are true
    
- Office plan - The plan of Office they are licensed for
    
- Office Activated - If they have activated Office
    
- Supported Mailbox - If they are on an OAuth-enabled mailbox
    
### Find out if Office 365 ProPlus is installed

The simplest way to detect if a user has Office 365 ProPlus installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Office 365 admin center. The report provides a list of all users who have activated Office 365 ProPlus within the last 7 days, 30 days, 90 days, or 180 days. For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report. You can export the report to Excel. For more information about the report, see [Office 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).
  
If you don't want to use the Activations report, you can ask a user to open on their machine an Office application, such as Word, and then choose **File** \> **Account**. Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.

![Product information in an Office application](../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
For help with Office 365 ProPlus, see [Troubleshooting tips for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).
  
### Exchange requirements

Microsoft Exchange stores the add-in manifests within your organization's tenant. The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Server that supports OAuth authentication. By default, Exchange Multi-Tenant and Dedicated VNext deployments support OAuth. Exchange Dedicated Legacy and hybrid on-premises deployments can be configured to support OAuth; however, it isn't the default configuration.
  
Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet. 
  
## User and group assignments

The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Office 365 Groups, distribution lists, and security groups.
  
> [!NOTE]
> Non-mail enabled security groups are not currently supported. 
  
The following table shows what assignments are supported within Centralized Deployment, assuming the users support the client and server requirements mentioned earlier. Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.
  
|**Assignment to add-in**|**Supported**|
|:-----|:-----|
|User via direct assignment  <br/> |Yes  <br/> |
|User via group assignment  <br/> |Yes, if group is a top-level group (has no parent groups)  <br/> No, if the group is a nested group (has parent groups)  <br/> |
|Everyone in the tenant  <br/> |Yes  <br/> |
   
Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.
  
![Diagram of sales department](../media/683094bb-1160-4cce-810d-26ef7264c592.png)
  
|**User**|**How admin assigns the add-in**|**Assigned to an add-in?**|
|:-----|:-----|:-----|
|Joe  <br/> |Via Sales Department group  <br/> |Yes, Sales Department has no parent groups  <br/> |
|Bob  <br/> |Via Sales Department group  <br/> |Yes, Sales Department has no parent groups  <br/> |
|Sandra  <br/> |Direct assignment of user  <br/> |Yes  <br/> |
|Sheila  <br/> |Direct assignment of user  <br/> |Yes  <br/> |
|Bert  <br/> |Assignment not possible  <br/> |No, West Coast Sales Department is nested  <br/> |
|Fred  <br/> |Assignment not possible  <br/> |No, West Coast Sales Department is nested  <br/> |
   
### Find out if a group contains nested groups

The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook. If you enter the group name within the **To** field of an email and then click the group name when it resolves, it will show you if it contains users or nested groups. In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups. 
  
![Members tab of Outlook contact card](../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group. 
  
![Membership tab of the Outlook contact card](../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### Contacting Microsoft for support

If you or your users encounter problems loading the add-in while using Office Online apps (Word Online, Excel Online, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)). Provide the following information about your Office 365 environment in the support ticket.
  
|**Platform**|**Debug information**|
|:-----|:-----|
|Office Online  <br/> | Charles/Fiddler logs  <br/>  Tenant ID ( [learn how](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))  <br/>  CorrelationID. View the source of one of the office pages and look for the Correlation ID value and send it on:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Rich clients (Windows, Mac)  <br/> | Charles/Fiddler logs  <br/>  Build numbers of the client app (preferably as a screenshot from **File/Account**)  <br/> |
   


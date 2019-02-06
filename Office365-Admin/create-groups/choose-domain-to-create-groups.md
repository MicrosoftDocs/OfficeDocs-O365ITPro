---
title: "Choose the domain to use when creating Office 365 Groups"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: Admin
ms.topic: article
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
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: "Learn to choose the domain to use when creating Office 365 groups by configuring email address policies using PowerShell. "
---

# Choose the domain to use when creating Office 365 Groups

 Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.
  
If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.
  
Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization. Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).
  
## Example scenarios

Let's say your business's main domain is Contoso.com. But your organization's default accepted domain is service.contoso.com. This means Office 365 groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).
  
Let's say you also have sub-domains configured in your organization. You want Office 365 groups to be created in these domains, too:
  
- students.contoso.com for students
    
- faculty.contoso.com for faculty members
    
The following two scenarios explain how you would accomplish this.
  
> [!NOTE]
> When you have mulitple EAPs, they are evaluated in the order of priority. A value of 1 means the highest priority. Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the Office 365 group are as per the matched EAP. > If no EAPs match the specified criteria, then the Office 365 group gets provisioned in the organization's default accepted domain. Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain. 
  
### Scenario 1

The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### Scenario 2

Let's say you want to control what sub-domains Office 365 groups are created in. You want:
  
- Office 365 groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain. Use this command:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Office 365 groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain. Use this command:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- All other users in the groups.contoso.com domain. Use this command:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## Change email address policies

To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Changing an EAP has no impact on the groups that have already been provisioned.
  
## Delete email address policies

To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.
  
```
Remove-EmailAddressPolicy -Name StudentsGroups
```

Changing an EAP has no impact on the groups that have already been provisioned.
  
## Hybrid requirements

If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups. 
  
## Additional info about using email address policies for Office 365 groups:

There are a few more things to know:
  
- How fast groups are created depends on the number of EAPs configured in your organization.
    
- Users will not be able to modify domains when they create Office 365 groups. Only admins can specify the domain that the group can be created in.
    
- Group of users is determined using the standard queries (User properties) that are already available. Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties. 
    
- If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.
    
- If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.
    
- A maximum limit of 100 email address policies can be configured for an organization.
    
## See Also

[Create an Office 365 group in the admin center](create-groups.md)
  


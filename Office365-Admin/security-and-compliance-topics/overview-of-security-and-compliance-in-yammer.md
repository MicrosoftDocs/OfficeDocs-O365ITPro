---
title: "Overview of security and compliance in Yammer"
ms.author: v-irpast
author: v-irpast
manager: scotv
ms.date: 4/17/2018
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Adm_Yammer
search.appverid:
- MOE150
- YAE150
ms.assetid: a2c84111-1da6-4c70-8646-bfe585b93c90
description: "Find answers to questions about Yammer security, management, and deployment."
---

# Overview of security and compliance in Yammer

Yammer Enterprise administrative tools help you protect your Yammer data and comply with legal and regulatory standards.
  
For information about policies, tools, and best practices for all of Office 365, see [Overview of security and compliance in Office 365](https://support.office.com/article/dcb83b2c-ac66-4ced-925d-50eb9698a0b2).
  
Yammer Enterprise offers admins security and compliance tools that are not part of the free Yammer Basic. Items marked with an asterisk (*) are not available inYammer Basic. The [Security FAQ](overview-of-security-and-compliance-in-yammer.md#Security) section of this article describes security, privacy, and business continuity features that apply to both Yammer Basic and Yammer Enterprise. 
  
## Security Admin Features

|||
|:-----|:-----|
|**Task** <br/> |**How To** <br/> |
|Set password policies and logical firewalls  <br/> |[Manage Yammer security settings](manage-yammer-security-settings.md) \*  <br/> |
|Manage users  <br/> |[Add, block, or remove Yammer users](../user-topics/add-block-or-remove-yammer-users.md) \*  <br/> [Enforce office 365 identity for Yammer users](../user-topics/enforce-office-365-identity-for-yammer-users.md) \*  <br/> |
|Manage device access  <br/> |[Monitor account activity and device usage for a single user](../user-topics/add-block-or-remove-yammer-users.md#AccountActivity)\*  <br/> [Manage Yammer with Microsoft Intune](manage-yammer-with-microsoft-intune.md) \*  <br/> |
|Use multiple levels of admin roles  <br/> |[Manage Yammer admins](../user-topics/manage-yammer-admins.md) \*  <br/> |
|Control external network access  <br/> |[Manage Yammer security settings](manage-yammer-security-settings.md) \*  <br/> |
|Track changes to users, groups,  <br/> |[Track Yammer Events in the Office 365 Audit log and with the Management Activity API](track-yammer-events-in-the-office-365-audit-log-and-with-the-management-activity.md) \*  <br/> |
   
## Compliance Admin Features

|||
|:-----|:-----|
|**Task** <br/> |**How To** <br/> |
|Set up a usage policy  <br/> |[Set up a Yammer usage policy](set-up-a-yammer-usage-policy.md) \*  <br/> |
|Control data retention policies, discovery  <br/> |[Manage Yammer data compliance](manage-yammer-data-compliance.md) \*  <br/> |
|Monitor keywords  <br/> |[Monitor Keywords](manage-yammer-data-compliance.md#MonitorKeywords)\*  <br/> |
|Export data  <br/> |[Export data from Yammer](export-data-from-yammer-enterprise.md) \*  <br/> |
|Prevent specific data from being sent to external participants  <br/> |[Control external messaging in a Yammer network with Exchange Transport Rules](../external-messaging-topics/control-external-messaging-in-a-yammer-network-with-exchange-transport-rules.md) \*  <br/> |
|Keep content appropriate and intervene if necessary  <br/> |[Manage Yammer data compliance](manage-yammer-data-compliance.md) \*  <br/> [Monitor private content in Yammer (Verified Admins)](monitor-private-content-in-yammer-verified-admins.md) \*  <br/> |
   
## Security FAQ
<a name="Security"> </a>

### Q: Who can access the Yammer network?

A: Only users with a valid and verified company email address can join your Yammer network. Yammer has functionality to create external networks to collaborate securely with third parties.
  
### Q: Where is the data hosted?

A: Yammer data is hosted in Microsoft managed datacenters. See [Where is your data located](https://go.microsoft.com/fwlink/?LinkId=869423) to find the data centers for the country in which your company is located. Yammer is operated out of Microsoft's global network of data centers with 24/7/365 video surveillance, biometric and pin-based locks, strict personnel access controls and detailed visitor entry logs. 
  
### Q: What is Yammer's privacy policy? How do you treat my data?

A: Our privacy policy is publicly shared and available here, as part of the: [Microsoft Online Services Privacy Statement](https://go.microsoft.com/fwlink/?LinkID=331314).
  
### Q: What is Yammer's security policy?
<a name="SecurityPolicy"> </a>

A: Yammer is included in the [Office 365 Trust Center](https://go.microsoft.com/fwlink/?LinkID=715692).
  
### Q: Who has access to the data?
<a name="SecurityPolicy"> </a>

A: Only employees with a legitimate business need can access customer data, and all access is on an approval‐only basis. All access is logged and regularly audited.
  
### Q: Is the data encrypted?
<a name="SecurityPolicy"> </a>

A: All data in transit into and out of the production environment is encrypted at all times. Communication with Yammer is over HTTPS (TLS 1.2 supported) regardless of user endpoint (web, desktop app, mobile app, API). In addition to being encrypted in transit, Yammer data is encrypted at rest with AES-256 bit key encryption.
  
### Q: What is Yammer's architecture?
<a name="SecurityPolicy"> </a>

A: Yammer's architecture is driven by the needs of an Enterprise Social Network (ESN). An ESN is successful only if users adopt and engage with the platform. As such, Yammer is architected and developed in a way to support adoption and engagement, allowing rapid iterations of technology.
  
Yammer is a set of loose components, coupled with APIs. These are developed and released independently using a variety of different best-in-class codes and technologies. Yammer is a public cloud, SaaS, multitenant architecture only. We use a data-driven, rapidly iterating development approach to measure the success of the platform using the key metrics of end-user engagement and adoption.
  
### Q: Who owns the data posted in the Yammer network?
<a name="SecurityPolicy"> </a>

A: Data posted into a free Yammer Basic network is owned by the individuals posting that data. Those users are the data controllers for their content. Under Yammer Enterprise, the company is the data controller, and ownership of all data transfers to the company. Yammer is a data processor and has no rights to any content or responsibilities for the data posted within a Yammer network.
  
### Q: Do you comply with the data protection act in my country?
<a name="SecurityPolicy"> </a>

A: It is the data controller's responsibility to comply with the data protection legislation that affects them. Yammer has controls in place to facilitate data controllers' (individuals and companies) compliance with their data protection legislation.
  
### Q: Can we perform an on‐site visit or audit of your facilities?
<a name="SecurityPolicy"> </a>

A: Yammer does not permit customers to perform on‐site audits. With over 200,000 customers, this is not feasible, and it is also a risk to the security of the service. We will answer any security questions openly and transparently.
  
### Q: Do you conduct third‐party audits or testing?
<a name="SecurityPolicy"> </a>

A: Penetration tests of the Yammer infrastructure are conducted yearly as part of Office 365.
  
### Q: How is data separated from other customers?
<a name="SecurityPolicy"> </a>

A: Yammer is a true multi-tenant model. As such, customers' data is logically separated with strict controls to ensure separation of tenant data. The web application servers of Yammer are physically and logically separated from servers that store customer data. 
  
### Q: What is the difference between the security of an enterprise social network and Facebook?
<a name="SecurityPolicy"> </a>

A: Your Yammer network is private to your company. Only users with a valid and verified email address for your company can join your Yammer network. Yammer was built from the ground up as an Enterprise Social Network with security built‐in at every level and a high degree of control available as well as integration with corporate security systems such as Active Directory and single sign-on.
  
### Q: What is the difference between security of Yammer Basic and Yammer Enterprise?
<a name="SecurityPolicy"> </a>

A: The underlying security of both is identical. Yammer Enterprise brings more administrative control and provides the ability to integrate with other systems (e.g. Active Directory, Active Directory Federation Services, SharePoint, Microsoft Dynamics CRM, Salesforce).
  
For details of the security-related administrative controls available in Yammer Enterprise, see the tables at the beginning of this article.
  
### Q: Does Yammer sell our data?
<a name="SecurityPolicy"> </a>

A: No. Yammer does not mine or sell any customer data. All data belongs to the customer (either the user or the organization, dependent on the Yammer version in use).
  
### Q: Can I export all my data?
<a name="SecurityPolicy"> </a>

A: In Yammer Enterprise, verified admins can export messages and uploaded files, along with their metadata. The data export can also include any content that has been deleted, if the **Soft Delete** data retention option has been configured. 
  
### Q: What are Yammer's business continuity features?
<a name="SecurityPolicy"> </a>

A: Your data is backed up multiple times a day and protected with strong encryption on disk. Backups are transferred off-site over SSH and properly deleted after six months.
  
### Q: Is Yammer covered under the materials in the Office 365 Trust Center?
<a name="SecurityPolicy"> </a>

A: Yes it is. See [Office 365 Trust Center](https://go.microsoft.com/fwlink/?LinkID=715692).
  
### Q: Is Yammer security independently verified?
<a name="SecurityPolicy"> </a>

A: Yes. [ISO27001](https://go.microsoft.com/fwlink/?LinkID=615104) is the global standard in information security. Independent auditors have verified that Yammer meets the rigorous set of physical, logical, process, and management controls defined by the ISO 27001 standard. 
  
Yammer participates in the [Microsoft Online Services Bug Bounty](https://go.microsoft.com/fwlink/?LinkID=615101), which allows thousands of security researchers to test Yammer and help make our products even safer for users. 
  
## User Management FAQs
<a name="Management"> </a>

### Q: Can I enforce multifactor authentication?

A: For Yammer Enterprise, if you enforce Office 365 identity in Yammer. For more information, see [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6) and [Enforce office 365 identity for Yammer users](../user-topics/enforce-office-365-identity-for-yammer-users.md).
  
### Q: How do I manage Yammer on mobile devices?

A: Yammer is available for all major mobile platforms, including Windows Phone, iPhone, iPad, and Android. Users can install the Yammer application from their respective app store. 
  
Yammer Enterprise offers session management capabilities so that a user or administrator can end any Yammer session on any device if required.
  
Yammer Enterprise devices can be managed with Microsoft Intune. For more information, see [Manage Yammer with Microsoft Intune](manage-yammer-with-microsoft-intune.md).
  
### Q: How can I manage my users?

A: Only users with a valid and verified company email address can join your Yammer network.
  
In a free Yammer Basic network, users can invite their colleagues with the same email address suffix to collaborate. Users can also suspend other users from having access to the Yammer network.
  
In Yammer Enterprise, administrators can provision and remove users in bulk using a .csv file and also to synchronize with Azure Active Directory to automatically add users who are not already on Yammer and remove users from Yammer if their Active Directory account is disabled or deleted. 
  
For more information, see [Manage Yammer users across their lifecycle from Office 365](../user-topics/manage-yammer-users-across-their-lifecycle-from-office-365.md) and [Bulk update users by importing a .CSV file](../user-topics/add-block-or-remove-yammer-users.md#BulkUpdateUsers).
  
### Q: How can users without email addresses access Yammer?

A: Yammer works with many large organizations where it is important to hear the voice of all workers, including those without email addresses. In this case, Yammer can grant these users access based on a unique identifier.
  
## See also
<a name="Management"> </a>

#### Other Resources

[Yammer - Admin Help](https://support.office.com/article/e1464355-1f97-49ac-b2aa-dd320b179dbe)
  
[Manage Yammer security settings](manage-yammer-security-settings.md)
  
[Manage Yammer data compliance](manage-yammer-data-compliance.md)


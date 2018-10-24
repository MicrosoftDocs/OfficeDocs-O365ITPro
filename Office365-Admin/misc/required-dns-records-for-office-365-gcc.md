---
title: "Required DNS Records for Office 365 GCC High"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom: Core_O365Admin_Migration
search.appverid:
- MET150
- MOE150
ms.assetid: 5cb45d81-fdcf-4fde-8601-a09666353cc4
description: "Learn about the DNS records required for Office 365 U.S. Government GCC High. "
---

# Required DNS Records for Office 365 GCC High

As part of onboarding to Office 365 U.S. Government GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant. **You'll do this using the New-MsolDomain cmdlet in Azure AD PowerShell** to start the process of adding the domain and proving ownership. 
  
Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below. You may need to modify the below table to fit your organization's needs with respect to the inbound MX record(s) and any existing Autodiscover record(s) you have in place.
  
## Exchange Online

|**Type**|**Priority**|**Hostname**|**Points to address or value**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|MX  <br/> |0  <br/> |@  <br/> |\<tenant-name-here\>.mail.protection.office365.us  <br/> |1 Hour  <br/> |
|TXT  <br/> |-  <br/> |@  <br/> |v=spf1 include:spf.protection.office365.us -all  <br/> |1 Hour  <br/> |
|CNAME  <br/> |-  <br/> |autodiscover  <br/> |autodiscover.office365.us  <br/> |1 Hour  <br/> |
   
## Exchange Online MX Record

The MX record value for your accepted domains follows a standard format as noted above tenant.mail.protection.office365.us, replacing tenant with the first part of your default tenant name. 
  
For example, if your tenant name is contoso.onmicrosoft.com, you'd use:
  
 **contoso.mail.protection.office365.us**
  
## Skype for Business Online

|**Type**|**Priority**|**Hostname**|**Points to address or value**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|CNAME  <br/> |-  <br/> |sip  <br/> |sipdir.online.gov.skypeforbusiness.us  <br/> |1 Hour  <br/> |
|CNAME  <br/> |-  <br/> |lyncdiscover  <br/> |webdir.online.gov.skypeforbusiness.us  <br/> |1 Hour  <br/> |
   
|**Type**|**Service**|**Port**|**Protocol**|**Weight**|**Priority**|**TTL**|**Name**|**Target**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SRV  <br/> |_sip  <br/> |_tls  <br/> |443  <br/> |1  <br/> |100  <br/> |1 Hour  <br/> |@  <br/> |sipdir.online.gov.skypeforbusiness.us  <br/> |
|SRV  <br/> |_sipfederationtls  <br/> |_tcp  <br/> |5061  <br/> |1  <br/> |100  <br/> |1 Hour  <br/> |@  <br/> |sipfed.online.gov.skypeforbusiness.us  <br/> |
   
## Additional Office 365 Records

|**Type**|**Priority**|**Hostname**|**Points to address or value**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|
|CNAME  <br/> |-  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |1 Hour  <br/> |
   


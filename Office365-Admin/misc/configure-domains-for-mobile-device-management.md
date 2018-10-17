---
title: "Configure domains for Mobile Device Management for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_MDMConfigDomains'
- 'O365E_MDMConfigDomains'
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6186b4f-d673-4a1c-989e-9cbc6055dfb8
description: "Learn to manage Windows Phone devices with your Office 365 custom domain by adding DNS records. "
---

# Configure domains for Mobile Device Management for Office 365

 If you have a custom domain associated with Office 365 and you want to manage Windows Phone devices, you'll need to add DNS records for the domain at your DNS host. If you've added the records already, you're all set. After you add these records, Office 365 users in your organization who sign in on their mobile device with an email address that uses your custom domain can then be redirected to enroll in MDM for Office 365. 
  
Find your domain registrar in the list provided in [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx) and select the registrar name to go to step-by-step instructions how to create DNS records. Use the instructions for creating CNAME records to add the following records at your registrar: 
  
|**Host name**|**Record type**|**Address**|**TTL**|
|:-----|:-----|:-----|:-----|
|EnterpriseEnrollment  <br/> |CNAME  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |3600  <br/> |
|EnterpriseRegistration  <br/> |CNAME  <br/> |EnterpriseRegistration.windows.net  <br/> |3600  <br/> |
   
If your registrar or DNS host isn't listed, follow the general steps in [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/e21a9a4a-7b14-42cb-b39b-03aee92da95f).
  
## Next steps

After you add the two records, you'll need to complete [setting up Mobile Device Management for Office 365](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx). Although Mobile Device Management is available in Office 365, it is a separate online service. You can navigate to it two ways:
  
- From the Office 365 admin center, navigate to **Admin Centers** \> **Security &amp; Compliance Center**. Then navigate to **Security policies** \> **Device management** and click **Let's get started**.
    
    ![Set up Mobile Device Management for Office 365](../media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
- Or in the Office 365 admin center \> **Home** page, type mobile device management in the **Search** box. 
    
    ![Search for mobile device management in the admin center](../media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)
  
## See also

[Set up Mobile Device Management (MDM) in Office 365](https://support.office.com/article/dd892318-bc44-4eb1-af00-9db5430be3cd)


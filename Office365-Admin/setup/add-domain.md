---
title: "Add a domain to Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_SupportHm_AddDomain'
- 'O365P_DomainVerify_TXTRecordNoEffect'
- 'O365P_DomainsWizard_NoNSRedirect'
- 'O365P_DomainsVerify_RecordExplain'
- 'O365P_DomainsSetup_ExplainEmailUpdate localOnly'
- 'O365P_DomainsMainUI_AddDomain'
- 'O365P_DomainsMain_NoRedelegation'
- 'O365P_DomainsMain_AddDomain'
- 'O365P_1stExplainEmailUpdate'
- 'O365M_DomainVerify_TXTRecordNoEffect'
- 'O365M_DomainsWizConfig_ConfigDNS'
- 'O365M_DomainsWizAdd_SpecServices'
- 'O365M_DomainsWizAdd_ConfigDNS'
- 'O365M_DomainsVerify_RecordExplain'
- 'O365M_DomainsSetup_ExplainEmailUpdate'
- 'O365M_DomainsMain_SetUpDomain'
- 'O365M_DomainsMain_AddDomain'
- 'O365M_DomainsDNSSettings_ConfigDNS'
- 'O365E_DomainVerify_TXTRecordNoEffect'
- 'O365E_DomainsWizConfig_ConfigDNS'
- 'O365E_DomainsWizAdd_SpecServices'
- 'O365E_DomainsWizAdd_ConfigDNS'
- 'O365E_DomainsMain_SetUpDomain'
- 'O365E_DomainsMain_AddDomain'
- 'O365E_DomainsDNSSettings_ConfigDNS'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_Top
- Adm_UI_Elements
- strat_admin_top
ms.custom:
- Adm_O365_FullSet
- Adm_O365_Setup
- Adm_O365_Top
- Core_O365Admin_Migration
- domainstoptier
- MiniMaven
- SaRA
- strat_admin_top
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: "Add your domain to Office 365 in the admin center by adding a DNS record at your DNS host. The setup wizard walks you through the process."
---

# Add a domain to Office 365

 **[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for. 
  
 *To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to do these changes.*  
::: moniker range="o365-worldwide"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

1. In the Admin center, go to the [Domains](https://go.microsoft.com/fwlink/p/?linkid=834818) page, or choose **Setup** \> **Domains**.
    
    If you're using Office 365 Germany, go to this [Domains](https://go.microsoft.com/fwlink/p/?linkid=854615) page. 
    
    If you're using Office 365 operated by 21Vianet, go to this [Domains](https://go.microsoft.com/fwlink/p/?linkid=2007048) page. 
    
2. Choose **Add domain**.
    
3. Enter the name of the domain you want to add, then choose **Next**.
    
4. Choose how you want to verify that you own the domain.
    
    ![Choose your verification method](../media/92003868-53ed-4817-8f9b-19fdf73ac9c3.png)
  
    1. If your domain is registered at GoDaddy or 1&amp;1, choose **Sign in** and Office 365 [will set up your records automatically](../get-help-with-domains/domain-connect.md).
    
    2. You can have an email sent to the registered contact for the domain with a verification code. If you don't recognize or have access to the email on record, you can use option 3.
    
    3. You can use a TXT record to verify your domain. Select this and choose **Next** to see instructions for how to add this DNS record to your registrar's website. This can take up to 30 minutes to verify after you've added the record. 
    
5. Choose how you want to make the DNS changes required for Office to use your domain.
    
    1. Choose **Add the DNS records for me** if you want Office to configure your DNS automatically. 
    
    ![Add records for me](../media/030dc259-bd34-4a53-ab4e-c29b09c9322b.png)
  
    2. Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later. 
    
    ![Add records myself](../media/272f600f-5266-40c9-ac4b-d85b130abbc8.png)
  
    Choose this option if you know exactly what you're doing.
    
6. If you chose to  *add DNS records yourself*  , choose **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain. 
    
    ![Add these records](../media/81862586-7393-4ad3-9d4e-d7183e91b1b9.png)
  
    If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need. 
    
    If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).
    
    If you want to wait for later, scroll to the bottom and choose **Skip this step**.
    
7. Click **Finish** - you're done! 

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end
---
title: "Gather the information you need to create Office 365 DNS records"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365_Domain_Core
- Adm_O365_Setup
- Adm_O365_Top
- strat_admin_top
ms.custom:
- Adm_O365_FullSet
- Adm_O365_Setup
- Adm_O365_Top
- Core_O365Admin_Migration
- domainstoptier
- MiniMaven
- strat_admin_top
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: "Learn to find the values/information you need to create DNS records for Office 365. "
---

# Gather the information you need to create Office 365 DNS records

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
### Step 1: Find the TXT record value and verify

1. In the admin center, go to the [Domains](https://go.microsoft.com/fwlink/p/?linkid=834818) page, or choose **Setup** \> **Domains**.
    
    If you're using Office 365 Germany, go to this [Domains](https://go.microsoft.com/fwlink/p/?linkid=854615) page. 
    
    If you're using Office 365 operated by 21Vianet, go to this [Domains](https://go.microsoft.com/fwlink/p/?linkid=2007048) page. 
    
2. On the **Domains** page, choose your domain, then choose **Start setup**. You'll go back to the domains setup wizard to see the specific value you need to add.
    
3. On the **Verify domain** page, choose **Add a TXT record instead**, then choose **Next**.
    
4. Copy the **TXT value** shown. It looks like this: **MS=msXXXXXXXX**. 
    
5. Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.
    
6. Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.

7. Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.
    
### Step 2: Find the MX record value for email and more

1. In the admin center, go to the [Domains](https://go.microsoft.com/fwlink/p/?linkid=834818) page, or choose **Setup** \> **Domains**.
    
    If you're using Office 365 Germany, go to this [Domains](https://go.microsoft.com/fwlink/p/?linkid=854615) page. 
    
    If you're using Office 365 operated by 21Vianet, go to this [Domains](https://go.microsoft.com/fwlink/p/?linkid=2007048) page. 
    
2. On the **Domains** page, choose your domain. 
    
3. Under **Required DNS settings**, you'll see the DNS records to add.
    
    You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.
    
    The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.
    
4. Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.
    
5. Follow the steps for creating the records at your DNS host.

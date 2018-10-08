---
title: "Find your domain registrar for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_EditNSRecs_LocateDNS'
- 'O365P_DomainsVerify_WhereDNS'
- 'O365P_1stUI_LocateDNS'
- 'O365P_1stRun_LocateDNSProvider'
- 'O365M_DomainsVerify_WhereDNS'
- 'O365M_1stRun_LocateDNSProvider'
- 'O365E_DomainsVerify_WhereDNS'
- 'O365E_1stRun_LocateDNSProvider'
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: "Learn to find your domain registrar and DNS hosting provider using  InterNIC search."
---

# Find your domain registrar for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
## [Domain registrar](#tab/registrar)
  
### Find your domain name registrar

 **Note:** Domain names ending with two-letter combinations (like  *.ca*  or  *.jp*  ) won't work with this tool. 
  
1. On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.* 
    
2. Select the **Domain** option, and then click **Submit**.
    
3. On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain. 
    
## [DNS hosting provider](#tab/dnshost)
  
### Find your DNS hosting provider

 **Note:** Domain names ending with two-letter combinations (like  *.ca*  or  *.jp*  ) won't work with this tool. 
  
1. On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com. 
    
2. Select the **Domain** option, and then click **Submit**.
    
3. On the **Whois Search Results** page, locate the first **Name Server** entry. 
    
4. Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then click **Submit**.
    
5. On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain. 
    
---

## Still need help?

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
To set up a domain in Office 365 you must own one and change some of the DNS records for your domain.
  
If you don't already own a domain, you can [buy one from Office 365](buy-a-domain-name.md).
  
[![Get help from the Office 365 community forums](../media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![Admins: Sign in and create a service request](../media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![Admins: Call Support](../media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  


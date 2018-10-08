---
title: "Create DNS records for Office 365 when you manage your DNS records"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.date: 2/26/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365M_Troubleshoot_CreateDNSRecords'
- 'O365M_DomainWizard_DNS_StepByStep2'
- 'O365M_DomainWizard_DNS_StepByStep1'
- 'O365M_DomainWizard_DNS_StepByStep'
- 'O365M_DomainsDNSSettings_CreateDNSRecords'
- 'O365M_DNSMgr_CustomDNS'
- 'O365M_ConfigWiz_Step1_CreateDNS'
- 'O365E_Troubleshoot_CreateDNSRecords'
- 'O365E_DomainWizard_DNS_StepByStep2'
- 'O365E_DomainWizard_DNS_StepByStep1'
- 'O365E_DomainWizard_DNS_StepByStep'
- 'O365E_DomainsDNSSettings_CreateDNSRecords'
- 'O365E_DNSMgr_CustomDNS'
- 'O365E_ConfigWiz_Step1_CreateDNS'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
description: "Learn to create DNS records for Office 365 operated by 21Vianet when your manage your DNS records. "
---

# Create DNS records for Office 365 when you manage your DNS records

For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, click the link for your DNS hosting provider. 
  
||||
|:-----|:-----|:-----|
|[22.cn](create-dns-records-at-22-cn.md) <br/> [35COM](create-dns-records-at-35com.md) <br/> [BIZCN](create-dns-records-at-bizcn.md) <br/> [CNDNS](create-dns-records-at-cndns.md) <br/> [DNSCOM](create-dns-records-at-dnscom.md) <br/> [DNSPod](create-dns-records-at-dnspod.md) <br/> |[East.net](create-dns-records-at-east-net.md) <br/> [E-Business Services](create-dns-records-at-e-business-services.md) <br/> [ENAME](create-dns-records-at-ename.md) <br/> [HiChina](create-dns-records-at-hichina.md) <br/> [IDC1](create-dns-records-at-idc1.md) <br/> [NowCn](create-dns-records-at-now-cn.md) <br/> |[Oray](create-dns-records-at-oray.md) <br/> [SUNDNS](create-dns-records-at-sundns.md) <br/> [West263](create-dns-records-at-west263.md) <br/> [Xinnet](create-dns-records-at-xinnet.md) <br/> [ZGSJ](create-dns-records-at-zgsj.md) <br/> |
   
More options and some things to be aware of:
  
- Don't worry if your DNS hosting provider isn't listed — you can follow the [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/e21a9a4a-7b14-42cb-b39b-03aee92da95f).
    
-  If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](https://support.office.com/article/98b6bfa3-1b0b-4484-8a12-02061cc9f9c3). For descriptions of what the DNS records do, see [DNS basics](https://support.office.com/article/a95f7b01-c5b4-4fce-8371-4ce359351126).
    
-  Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) to a [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
    
- To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e). For descriptions of what the DNS records do, see [DNS basics](https://support.office.com/article/a95f7b01-c5b4-4fce-8371-4ce359351126).
    


---
title: "Change nameservers to set up Office 365 with HiChina"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_HiChina1'
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
- GEA150
ms.assetid: 3c28f260-4814-432c-bc2e-9dade767a88d
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when HiChina is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with HiChina

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at HiChina](create-dns-records-at-hichina.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-hichina.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-hichina.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domaina and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
2. In the left pane, click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/ad8821b9-d7a7-4915-9aec-255e4c5bed93.png)
  
3. Click **新增解析** (add a record). 
    
    ![Click "新增解析"](../media/438d0bda-f2ff-46b6-a5c0-ca89315908f0.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **记录类型** (record type): **TXT**
    
  - **主机记录(RR)** (host name): **@**
    
  - **解析线路** (network): Use the default value 
    
  - **记录值** (record value): Paste **Destination or Points to Address** value that you just copied. 
    
  - **TTL**: **10分钟** (10 minutes) 
    
    ![Add TXT record](../media/246931a5-7541-4524-9912-a672f46c5d01.png)
  
5. Click **保存** (save). 
    
To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to [HiChina domain management system](http://dmp.www.net.cn) and sign in with your domaina and password. 
    
    ![Sign in to HiChina domain management system](../media/dbac5fb1-cc3e-4c93-956f-1d89f71cab96.png)
  
    ![Click "域名DNS修改"](../media/d9ac9e9c-fc10-4c61-9bef-3e922490e904.png)
  
2. In the left pane, click **域名DNS修改** (change name servers). 
    
    ![Change name servers](../media/c244d5de-6769-4cdf-9fb1-c331de5be0a2.png)
  
3. In the first box, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
4. In the second box, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
5. Click **确认** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


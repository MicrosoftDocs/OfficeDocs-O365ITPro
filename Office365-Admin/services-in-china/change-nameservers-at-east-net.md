---
title: "Change nameservers to set up Office 365 with East.net"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_East1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: 136102cb-46fe-4100-8c60-e05aa97a6414
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when East.net is the DNS hosting provider."
monikerRange: 'o365-21vianet'
---

# Change nameservers to set up Office 365 with East.net

Follow the instructions below if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at east.net](create-dns-records-at-east-net.md).)
  

## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
    ![Sign in to east.net](../media/62d3e9d5-1fdc-45b9-bc72-0bde89168377.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
    ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析" (domain name resolution)](../media/88907339-c195-41a0-9ac1-f903d2812af9.png)
  
4. In the **新增解析记录** (add a DNS record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): Leave the box blank 
    
  - **类型** (type): **TXT**
    
  - **值** (value): Paste **Destination or Points to Address** value that you just copied. 
    
    ![Select "TXT"](../media/67d6d897-0696-4f3c-a5bf-596132dc676e.png)
  
5. Click **新增** (add). 
    
    ![Add TXT record](../media/a8c12de1-34ad-42c1-b6cd-f1285c9a5f43.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    
  
## Change your domain's name servers
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to [your domains list at east.net](http://www.east.net/service/domain/user) and sign in. 
    
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **域名管理** (domain management). 
    
    ![Click "域名管理" (domain management) for your domain](../media/1c27e199-e615-4971-b985-57572ed0f4c5.png)
  
3. Click the **修改DNS** (change name servers) tab. 
    
    ![Click "修改DNS"](../media/4035ed04-a3fd-4981-affc-ce03e1b40769.png)
  
4. In the **主域名DNS** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/45293a44-d8a3-499b-83ed-1cd47847069c.png)
  
5. In the **辅域名DNS** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **修改** (change). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


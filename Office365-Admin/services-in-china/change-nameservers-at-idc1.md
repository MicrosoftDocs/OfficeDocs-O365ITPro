---
title: "Change nameservers to set up Office 365 with IDC1"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_IDC1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
- httpsfix
search.appverid:
- MET150
- GEA150
ms.assetid: 0f3e7bbb-1ee7-46cf-994e-db4228198e2c
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when IDC1 is the DNS hosting provider."
monikerRange: 'o365-21vianet'
---

# Change nameservers to set up Office 365 with IDC1

Follow the instructions below if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at IDC1](create-dns-records-at-idc1.md).)

    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [IDC1 DNS management system](https://go.microsoft.com/fwlink/?linkid=838716).
    
2. In the **域名** (domain name) box, type the name of the domain that you want to update. 
    
3. In the **管理密码** (administration password) box, type the administration password for your domain name. 
    
4. Click **登录** (sign in). 
    
    The DNS records page for your domain opens.
    
    ![Sign in to DNS management system](../media/8562d0bc-dde7-4fdb-b4dc-78f57fa159b8.png)
  
5. On the **新建子域名** (add new subdomain) tab, in the **指向类型** (record type) drop-down list, select **TXT 记录** (TXT record). 
    
    ![Add TXT record](../media/342ff242-c2c7-4d60-8421-5387e0b8d7a8.png)
  
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **子域名** (subdomain): Leave the box blank. 
    
  - **域名** (points to domain): Paste **Destination or Points to Address** value that you just copied. 
    
  - **TTL**: **3600**
    
7. Click **增加** (add). 
    
8. Click **重启EDNS服务器** (restart EDNS server) for the changes to take effect across the Internet. 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to [IDC1 domain control panel](https://go.microsoft.com/fwlink/?linkid=838717) and sign in with your domain name and password. 
    
    ![Sign in to IDC1 domain control panel](../media/1e394e99-db79-4a39-bed9-07ffab124013.png)
  
2. In the left pane, click **修改DNS服务器** (change name servers). 
    
    ![Click "修改DNS服务器"](../media/b6959c5d-22de-4866-af10-c5138e978daa.png)
  
3. In the **主DNS服务器** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/ef3f7c8a-23f2-4940-87d1-0b8a2dd766e9.png)
  
4. In the **辅DNS服务器** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
5. Select **我已经知道修改DNS服务器存在24-48小时缓冲.并已经在新dns服务器作好了解析** (I understand that it might take 24-48 hours for the DNS server change to propagate through the DNS system). 
    
6. Click **修改DNS** (change). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


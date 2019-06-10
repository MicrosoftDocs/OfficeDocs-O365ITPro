---
title: "Change nameservers to set up Office 365 with 22.cn"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: acdd92ba-13b2-4264-b532-ccd3d266860b
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when 22.cn is the DNS hosting provider."
monikerRange: 'o365-21vianet'
---

# Change nameservers to set up Office 365 with 22.cn

Follow the instructions below if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at 22.cn](create-dns-records-at-22-cn.md).) 
  
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [your domains list at 22.cn](https://www.22.cn/) and sign in. 
    
    ![Sign in to 22.cn](../media/6aeb0d2e-4844-499d-9cdf-278c5490e40b.png)
  
2. In the right pane, click the name of the domain that you want to update.
    
    ![Click the domain you want to update](../media/9118a9a5-0815-4254-be7e-fbfb3570af0e.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/2fd80f2c-30ad-4ba3-a376-4afb54ae3ced.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (type): **TXT**
    
  - **IP地址/主机名** (value): Paste **Destination or Points to Address** value that you just copied. 
    
  - **线路类型** (network): Use the default value. 
    
    ![Click "TXT"](../media/58ad8a10-fac6-4231-aca4-c7763873a8ef.png)
  
5. Click **添加一条** (add). 
    
    ![Add TXT record](../media/f8755878-41aa-4c92-a409-8ebbb3c271f3.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to the [your domains list at 22.cn](https://www.22.cn/) and sign in. 
    
    ![Sign in to 22.cn](../media/6aeb0d2e-4844-499d-9cdf-278c5490e40b.png)
  
2. In the right pane, click the name of the domain that you want to update.
    
    ![Click the domain you want to update](../media/9118a9a5-0815-4254-be7e-fbfb3570af0e.png)
  
3. Click the **DNS管理** (DNS management) tab. 
    
    ![Click "DNS管理"](../media/ed7571ab-ff3c-4614-9d50-bd0ff31fbe61.png)
  
4. In the **请选择DNS** (specify DNS hosting provider) row, click **第三方DNS** (third-party DNS hosting provider). 
    
5. In the **DNS1** row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/24401480-320a-4ad9-8e02-9e1bd886e9f6.png)
  
6. In the **DNS2** row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
7. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


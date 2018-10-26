---
title: "Change nameservers to set up Office 365 with Xinnet"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Xinnet1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: acc7a119-8ba9-4ff0-aeab-6fd91b037ccc
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when Xinnet is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with Xinnet

Follow the instructions below if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at Xinnet](create-dns-records-at-xinnet.md).)

    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [Xinnet website](http://www.xinnet.com) and sign in. 
    
    ![Sign in to Xinnet](../media/c9d2c80e-0458-4131-88f3-9e1b094d0823.png)
  
2. In the upper-right corner, click **进入我的账户** (access my account). 
    
    ![Click "进入我的账户'](../media/4fbb122f-a08b-4c93-9bfa-f1d059201d6b.png)
  
3. In the left navigation pane, click **我的产品** (my products). 
    
    ![Click "域名管理"](../media/ffc1dfdd-f291-4645-9030-ef84d76edbef.png)
  
4. In the **常规管理** (general management) section, click **域名管理** (domain management). 
    
5. In the right pane, click the **我的域名** (my domains) tab. 
    
    ![Click "我的域名"](../media/b0bfbada-6e17-4857-b718-31a3fab89588.png)
  
6. Select the check box next to the domain that you want to update.
    
    ![Click "mydns解析设置"](../media/07417e01-a4a7-4f74-a444-0bc80b9fb72d.png)
  
7. Click **mydns解析设置** (DNS settings). 
    
    The DNS records page for your domain opens.
    
8. In the **文本记录 (TXT)** section, click **添加新的文本记录** (add a TXT record). 
    
    ![Click "添加新的文本记录"](../media/d859335c-ea0e-4a00-8217-2ed504d2cdaf.png)
  
9. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **文本记录 (TXT)**: Leave the box blank.
    
  - **文本内容** (value): Paste **Destination or Points to Address** value that you just copied. 
    
  - **TTL**: Use the default value.
    
    ![Add TXT record](../media/fbbfa817-2a12-43c4-99b9-0e6ef76e9905.png)
  
10. Click **提交** (submit). 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's name servers
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to the [Xinnet website](http://www.xinnet.com) and sign in. 
    
    ![Sign in to Xinnet](../media/c9d2c80e-0458-4131-88f3-9e1b094d0823.png)
  
2. In the upper-right corner, click **进入我的账户** (access my account). 
    
    ![Click "进入我的账户'](../media/4fbb122f-a08b-4c93-9bfa-f1d059201d6b.png)
  
3. In the left navigation pane, click **我的产品** (my products). 
    
    ![Click "域名管理"](../media/ffc1dfdd-f291-4645-9030-ef84d76edbef.png)
  
4. In the **常规管理** (general management) section, click **域名管理** (domain management). 
    
    ![Click "我的域名"](../media/b0bfbada-6e17-4857-b718-31a3fab89588.png)
  
5. In the right pane, click the **我的域名** (my domains) tab. 
    
    ![Click "管理"](../media/c35373b6-2480-4f2b-b82f-e7d141b286cf.png)
  
6. In the **操作** (actions) column for the domain that you want to update, click **管理** (management). 
    
    ![Click "域名管理"](../media/07b7b3d7-3a81-429a-9875-b63790d65f66.png)
  
7. Click **域名管理** (domain management). 
    
    ![Click '修改域名DNS'](../media/50b0784b-4d1b-4c9e-809a-ffbb776f992e.png)
  
8. Click **修改域名DNS** (change name servers). 
    
    ![Change name servers](../media/8f072572-7679-4f05-8881-13ca1de3ceba.png)
  
9. In the **主域名服务器名字** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
10. In the **辅域名服务器名字** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
11. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


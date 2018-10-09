---
title: "Change nameservers to set up Office 365 with SUNDNS"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_SUNDNS1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: a9891ca0-0d20-4614-b77c-9a7a5c7e4b54
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when SUNDNS is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with SUNDNS

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at SUNDNS](create-dns-records-at-sundns.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-sundns.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-sundns.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [SUNDNS website](http://www.sundns.com/login.php) and sign in. 
    
    ![Sign in to SUNDNS](../media/2e45a261-18c2-4244-817a-ca3eb9f8a369.png)
  
2. On the left navigation tree, under **我的业务** (my business), click **我的DNS** (my DNS). 
    
    ![Click "我的DNS"](../media/6ca2c8a9-6427-4f87-97d5-aadb2c217ee2.png)
  
3. In the right pane, in the **管理** (manage) column for the domain that you want to update, click **管理** (manage). 
    
    The DNS records page for your domain opens.
    
    ![Click "管理"](../media/bf345b18-d27f-40d9-bebc-f23559ec65ec.png)
  
4. In the **文本记录(TXT记录)** (TXT record) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - ** 主机名 ** (host name): Leave the box blank. 
    
  - **文本内容** (value): Paste **Destination or Points to Address** value that you just copied. 
    
    ![Add TXT record](../media/76d547b9-38a5-4eae-943a-e4fcf6f0f4b2.png)
  
5. Click **添加** (add). 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** * **domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to the [SUNDNS website](http://www.sundns.com/login.php) and sign in. 
    
    ![Sign in to SUNDNS](../media/2e45a261-18c2-4244-817a-ca3eb9f8a369.png)
  
2. On the left navigation tree, under **我的业务** (my business), click **我的域名** (my domains). 
    
    ![Click "我的域名"](../media/37846a20-e4e7-4169-8a11-62fb687fd13c.png)
  
3. In the **管理** (manage) column for the domain that you want to update, click **详情** (details). 
    
    ![Click "详情"](../media/d9aa03e7-122e-4d79-84c0-18026bcd8bfe.png)
  
4. Click **修改域名DNS** (change name servers). 
    
    ![Click "修改域名DNS"](../media/3e2ddcf9-22f8-4c25-98bb-91b7b1cdcdce.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


---
title: "Change nameservers to set up Office 365 with 35COM"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_35COM1'
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
- GEA150
ms.assetid: d1b5cc0d-47a2-46d7-a5ad-cb6a4b864e3b
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when 35COM is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with 35COM

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at 35COM](create-dns-records-at-35com.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-35com.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-35com.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [35COM domain management system](https://www.dns-diy.net/home.aspx ) and sign in with your domain name and password. 
    
    ![Sign in to 35COM DNS-DIY system](../media/f40bf946-ee14-43fb-8714-278b89904ee2.png)
  
2. On the **DNS服务在线协议** (DNS service agreement) page, read the agreement and click **同意** (agree). 
    
    The DNS records page for your domain opens.
    
    ![Click "同意"](../media/d2e57676-77f8-4dff-9650-2532dbc83d47.png)
  
3. In the empty record, make sure that the fields are set to precisely the following values:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **类型** (type): **TXT**
    
  - **IP地址/主机名** (points to): Paste **Destination or Points to Address** value that you just copied. 
    
  - **优先级** (priority): Leave the box blank. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/ef04f942-9e42-4815-96d2-931b274aa557.png)
  
4. Click **新增** (add). 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's DNS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's DNS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to the [35COM website](https://www.35.com/login_form.php) and sign in. 
    
    ![Sign in to 35COM](../media/84d8a42c-4edd-4432-a2d6-e836f27ae523.png)
  
2. Click **域名** (domains). 
    
    ![Click "域名"](../media/a08ee508-5a64-4b11-8a6c-cd5ac8e112e6.png)
  
3. In the **操作** (actions) column for the domain that you want to update, click **详细信息** (details). 
    
    ![Click "详细信息"](../media/42c77dbf-0dd5-495d-baf4-749a39c1828e.png)
  
4. In the **域名DNS信息** (name server information), click **修改** (change). 
    
    ![Click "域名DNS信息"](../media/3bb1c778-76d7-4bf8-81f8-074231206a0a.png)
  
5. In the **DNS1** box, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/49650678-734f-46c4-ac8e-df24233017c3.png)
  
6. In the **DNS2** box, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
7. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


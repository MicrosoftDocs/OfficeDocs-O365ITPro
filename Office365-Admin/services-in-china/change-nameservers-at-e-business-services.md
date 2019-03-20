---
title: "Change nameservers to set up Office 365 with E-business Services"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_EBus1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: b3cd782f-3553-4bad-b7bc-fb7e64832e9e
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when E-business Services is the DNS hosting provider."
monikerRange: 'o365-21vianet'
---

# Change nameservers to set up Office 365 with E-business Services 

Follow the instructions below if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at E-business Services](create-dns-records-at-e-business-services.md).)

## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at E-business Services by using [this link](https://www.eb.com.cn/login?oauth_callback=https://www.eb.com.cn/user). You'll be prompted to sign in.
    
    ![Sign in to domain control panel](../media/1095c6f1-a37f-40b7-bedb-674f3378cd57.png)
  
2. Click **DNS解析管理** (DNS record management). 
    
    ![Click "DNS解析管理"](../media/2e7f43fc-12bc-48e8-80eb-3d6524ab3251.png)
  
3. In the **高级解析** (advanced DNS settings) section, click **文本记录(TXT记录)** (TXT record). 
    
    ![Click "文本记录(TXT记录)"](../media/5a473b8a-7b49-46d3-b8e6-b67b34364244.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **内容** (value): Paste **Destination or Points to Address** value that you just copied. 
    
5. Click **增加** (add). 
    
    ![Add TXT record](../media/2570ded3-e7e4-4456-b425-a31d859fbe14.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** * **domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. To get started, go to your domains page at E-business Services by using [this link](https://www.eb.com.cn/login?oauth_callback=https://www.eb.com.cn/user). You'll be prompted to sign in.
    
    ![Sign in to domain control panel](../media/1095c6f1-a37f-40b7-bedb-674f3378cd57.png)
  
2. Click **查看域名信息** (domain information). 
    
    ![Click "查看域名信息"](../media/76d16520-d1ef-4278-a7b0-c0684ba7b6d8.png)
  
3. Click **修改DNS** (change name servers). 
    
4. In the **DNS服务器1** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/3724473b-87b0-4e4f-af76-96646957951c.png)
  
5. In the **DNS服务器2** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **确认提交** (submit). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


---
title: "Change nameservers to set up Office 365 with ENAME"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_ENAME1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: aa17fe0b-bfa7-41b8-a145-25dbc7c375a3
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when ENAME is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with ENAME

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at ENAME](create-dns-records-at-ename.md).)
  
Here's what you need to do:
  
- [Add a record to verify your domain](change-nameservers-at-ename.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-ename.md#BKMK_change_your_domain_s_1)
    
## Add a record to verify your domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at ENAME](https://www.ename.net/manage/domainlist) and sign in. 
    
    ![Sign in to ENAME](../media/6d6c0ca0-576f-4112-bf02-173caa62cba2.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/93ce0fff-1ab3-4d3f-8861-291fe16b85a3.png)
  
3. Click **域名解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析 "](../media/660a9979-53bb-43b9-a1e3-5fccffd1a6c5.png)
  
4. Click **添加记录** (add a record). 
    
    ![Click "添加记录"](../media/518c8698-c209-4237-8d20-a3a0cf1d7c68.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host name): Leave the box blank. 
    
  - **记录类型** (record type): **TXT**
    
  - **记录值(IP/域名)** (value): Paste **Destination or Points to Address** value that you just copied. 
    
  - **线路类型** (network): Use the default value. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/2f9119ef-46de-4ba5-adbc-1bec5fbe24ea.png)
  
6. Click **保存** (save). 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to [your domains list at ENAME](https://www.ename.net/manage/domainlist) and sign in. 
    
    ![Sign in to ENAME](../media/6d6c0ca0-576f-4112-bf02-173caa62cba2.png)
  
2. In the right pane, in the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/93ce0fff-1ab3-4d3f-8861-291fe16b85a3.png)
  
3. Click **修改DNS** (change name servers). 
    
    ![Click "修改DNS"](../media/18bab1aa-9943-486f-83b7-0500e41247e1.png)
  
4. In the **DNS1** row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
5. In the **DNS2** row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **确认修改** (change). 
    
![Change name servers](../media/3fda4a62-a469-4df3-a6c3-d101e95ca48f.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


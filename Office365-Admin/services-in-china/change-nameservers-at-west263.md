---
title: "Change nameservers to set up Office 365 with West263"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_West2631'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 4453dad6-79c1-4bfc-9d3b-771a328793a2
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when West263 is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with West263

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at West263](create-dns-records-at-west263.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-west263.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-west263.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [your domains list at WEST263](http://west263.com/manager/domain) and sign in. 
    
    ![Sign in to WEST263](../media/c1042b3b-9560-4383-ba24-ae1f522b17c5.png)
  
2. In the right pane, in the **管理** ( management) column for the domain that you want to update, click **管理** ( management). 
    
    ![Click "管理"](../media/a1fc5365-da24-4d6f-b51b-706485e1a065.png)
  
3. Click the **域名解析** (domain name resolution) tab. 
    
    The DNS records page for your domain opens.
    
    ![Click "域名解析"](../media/5263e2de-81f1-4cdf-805e-4e2d0ce62bae.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): Leave the box blank. 
    
  - **解析类型** (type): **TXT记录**
    
  - ** 对应值 ** (value): Paste **Destination or Points to Address** value that you just copied. 
    
  - ** TTL **: **3600**
    
    ![Select "TXT记录"](../media/5e34c5cd-72d0-46dd-9c8c-05258d1108d0.png)
  
5. Click **确定添加** (add). 
    
    ![Add TXT record](../media/6d00a4e5-d332-4514-b7c1-1a0267c7516d.png)
  
6. In the confirmation dialog box, click **OK**.
    
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
  
1. In your browser, go to the [your domains list at WEST263](http://west263.com/manager/domain) and sign in. 
    
    ![Sign in to WEST263](../media/c1042b3b-9560-4383-ba24-ae1f522b17c5.png)
  
2. In the right pane, in the **管理** ( management) column for the domain that you want to update, click **管理** ( management). 
    
    ![Click "管理"](../media/a1fc5365-da24-4d6f-b51b-706485e1a065.png)
  
3. Click the **修改域名的DNS** (change name servers) tab. 
    
    ![Click "修改域名的DNS"](../media/43305c70-75d6-4db4-b1df-c27420c1e6fe.png)
  
4. In the **DNS使用** (name servers to be used) row, click **使用自定义** (use other name servers). 
    
5. In the **域名DNS1** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/749209fe-cc79-4967-8da1-1a3f090c3b9c.png)
  
6. In the **域名DNS2** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
7. Click **确定提交** (submit). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


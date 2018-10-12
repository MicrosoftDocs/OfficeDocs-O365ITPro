---
title: "Change nameservers to set up Office 365 with DNSCOM"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DNSCOM1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 3450a7bb-e3de-4b2c-b71a-aa1f80c03c93
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when DNSCOM is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with DNSCOM

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at DNSCOM](create-dns-records-at-dnscom.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-dnscom.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-dnscom.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [DNSCOM domain management system](http://mgt.dns.com.cn/index.php) and sign in with your domain name and password. 
    
    ![Sign in to DNSCOM domain management system](../media/e1714e30-2f91-4987-b0bc-647145d854b4.png)
  
2. Click **MyDNS功能** (MyDNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "MyDNS功能"](../media/a407306f-4d10-429b-812a-5f31153c61a5.png)
  
3. On the DNSCOM website, open the DNS records page for your domain. 
    
4. In the **纯域名列表** (domain list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **类型** (type): **TXT**
    
  - **指向** (point to): Paste **Destination or Points to Address** value that you just copied. 
    
    ![Add TXT record](../media/39e6d11c-3a2b-4a01-bb84-bd00916523dd.png)
  
5. Click **保存** (save). 
    
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
  
1. In your browser, go to [DNSCOM domain management system](http://mgt.dns.com.cn/index.php) and sign in with your domain name and password. 
    
    ![Sign in to DNSCOM domain management system](../media/e1714e30-2f91-4987-b0bc-647145d854b4.png)
  
2. Click **修改域名DNS** (change name servers). 
    
    ![Click "修改域名DNS"](../media/2db20d3c-2237-419f-bcb7-c4bcfb312370.png)
  
3. Select **填写具体信息** (specify name servers) 
    
    ![Change name servers](../media/001741b4-0e45-47ce-b046-98d85718e51a.png)
  
4. In the **域名服务器名字1** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
5. In the **域名服务器名2** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


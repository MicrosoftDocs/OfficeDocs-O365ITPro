---
title: "Change nameservers to set up Office 365 with BIZCN"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_BIZCN1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: cb9ac07b-71d8-4448-8b13-cf7f0bd87e00
description: "Learn how you can set up Office 365 to manage your DNS records, when BIZCN is the DNS hosting provider."
monikerRange: 'o365-21vianet'
---

# Change nameservers to set up Office 365 with BIZCN

Follow the instructions below if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at BIZCN](create-dns-records-at-bizcn.md).)

    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Click **增加TXT记录** (add a TXT record). 
    
    ![Click "增加TXT记录"](../media/2d797e07-dff8-46ee-b63d-48680c18e18b.png)
  
7. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机名** (host name): **@**
    
  - **字符串记录** (value): Paste **Destination or Points to Address** value that you just copied. 
    
    ![Add TXT record](../media/5999218d-4d02-41ea-b0df-ab5f7059f0e3.png)
  
8. Click **增加** (add). 
    
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
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to the [BIZCN website](https://www.bizcn.com) and sign in. 
    
    ![Sign in to BIZCN](../media/6fa4422d-8220-401c-a529-39de15d230ef.png)
  
2. In the left navigation pane, in the **域名服务** (domain service) section, click **域名列表** (domain list). 
    
    ![Click "域名列表"](../media/c087367c-fc85-4689-809c-90c0947fabfb.png)
  
3. Set the search conditions, and then click **查询** (search). 
    
    ![Search for your doamin](../media/d0d22c7e-d619-401c-b6ef-4183820e72fa.png)
  
4. Click the name of the domain that you want to update.
    
    ![Click the name of your domain](../media/378482f2-4d75-4790-b10c-9ad429a59d60.png)
  
5. Click **DNS解析管理** (DNS settings). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理 "](../media/ca896bc3-67a4-41b3-ac7f-1d930af77ca0.png)
  
6. Click **修改域名的DNS** (change name servers). 
    
    ![Click "修改域名的DNS"](../media/82ac70b1-dd5d-4c1e-8de5-748aef096381.png)
  
7. Select **自定义DNS** (specify name servers). 
    
    ![Change name servers](../media/eb0f5386-0396-418c-ab29-53e2863b484c.png)
  
8. In the **自定义DNS1** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
9. In the **自定义DNS2** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
10. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


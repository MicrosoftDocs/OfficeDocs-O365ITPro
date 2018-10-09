---
title: "Change nameservers to set up Office 365 with Now.cn"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Now1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 39751f12-6a14-4dfc-b665-c988f93ffb3d
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when Now.cn is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with Now.cn

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at Now.cn](create-dns-records-at-now-cn.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-now-cn.md#BKMK_add_a_record)
    
- [Change your domain's name servers](change-nameservers-at-now-cn.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to **http://www.now.cn/user/login.php?1&amp;page=%2Fdomain-admin%2Fdomain_list.php** and sign in. 
    
    ![Sign in to Now.cn](../media/7525bdbc-9624-4eb5-be0a-87fa9e3fb9d2.png)
  
2. In the **功能管理** (management) column for the domain that you want to update, click **VDNS 解析** (VDNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "VDNS 解析"](../media/32ce15a4-2764-4d1e-af54-b653d5ae95b3.png)
  
3. In the **Type** drop-down list, select **TXT**.
    
    ![Select "TXT"](../media/262f0e29-3dfb-4749-bd3a-8cb4a831a43a.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - ** Prior **: Use the default value.
    
  - ** \*.\*.\*.\* **: Paste **Destination or Points to Address** value that you just copied. 
    
    ![Add TXT record](../media/493bc4c7-c870-445e-9f6d-addb636448a7.png)
  
5. Click **Add Subdomain**.
    
6. Click **Restart VDNS** for the changes to take effect across the Internet. 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** * **domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's name servers
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to your domains list at Now.cn ( **http://www.now.cn/user/login.php?1&amp;page=%2Fdomain-admin%2Fdomain_list.php** ) and sign in. 
    
    ![Sign in to Now.cn](../media/7525bdbc-9624-4eb5-be0a-87fa9e3fb9d2.png)
  
2. In the **功能管理** (management) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/2c0b906f-888b-4b98-bff2-934fd4a084d4.png)
  
3. Click **修改域名服务器** (change name servers). 
    
    ![Click "修改域名服务器"](../media/b2eb2058-bad2-4cdd-a63d-47aa6a6001b4.png)
  
4. In the **域名服务器 1** (primary name server) row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/8db18717-7196-4f7e-ae28-4f564c7ce357.png)
  
5. In the **域名服务器 2** (secondary name server) row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **修改** (change). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


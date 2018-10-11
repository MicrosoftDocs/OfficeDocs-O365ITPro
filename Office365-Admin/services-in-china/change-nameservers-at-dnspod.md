---
title: "Change nameservers to set up Office 365 with DNSPod"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_DNSPod1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: fe56c6c8-6b67-4fc4-a9c4-ddc572351e5d
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when DNSPod is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with DNSPod

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at DNSPod](create-dns-records-at-dnspod.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-dnspod.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-dnspod.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. On the DNSPod website, open the DNS records page for your domain. 
    
4. Click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
5. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **主机记录** (host): **@**
    
  - ** 记录类型 ** (record type): **TXT**
    
  - **线路类型** (network): Use the default value. 
    
  - **记录值** (record value): Paste **Destination or Points to Address** value that you just copied. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/c9a54892-c7f9-400b-b49a-631854077365.png)
  
6. Click **保存** (save). 
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Add this TXT record to show you own** * **domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to [your domains list at DNSPod](https://www.dnspod.cn/Domain#all) and sign in. 
    
    ![Sign in to DNSPod](../media/39cce6fa-a662-4735-9e6a-6f05c0140c5e.png)
  
2. In the right pane, in the **全部域名** (all domains) section, click the name of the domain that you want to update. 
    
    The DNS records page for your domain opens.
    
    ![Click the domain you want to update](../media/4abaa5e9-b430-4832-a8b0-47932713775d.png)
  
3. On the DNSPod website, open the DNS records page for your domain. 
    
4. Click **添加记录** (add a DNS record). 
    
    ![Click "添加记录"](../media/988b7551-4ac5-478f-9400-5c9bbcb79748.png)
  
5. Create two name server records, or edit the existing name server records to match the following values:
    
  - **ns1.dns.partner.microsoftonline.cn**
    
  - **ns2.dns.partner.microsoftonline.cn**
    
6. Save your changes.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


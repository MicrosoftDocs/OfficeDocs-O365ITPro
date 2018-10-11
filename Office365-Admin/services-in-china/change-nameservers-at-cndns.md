---
title: "Change nameservers to set up Office 365 with CNDNS"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_CNDNS1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: c279f6dd-d38a-48a8-bbb0-b014aa9adcda
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when CNDNS is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with CNDNS

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at CNDNS](create-dns-records-at-cndns.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-cndns.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-cndns.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to [your domains list at CNDNS](http://www.cndns.com/userpanel/dme_mng/dme_lst.asp) and sign in. 
    
    ![Sign in to CNDNS](../media/e9a982be-5751-49ca-a6e5-c227eedffc7e.png)
  
2. In the **操作** (actions) column for the domain that you want to update, click **解析** (domain name resolution). 
    
    The DNS records page for your domain opens.
    
    ![Click "解析"](../media/4613ead0-8c68-44d6-8708-b87bb5a778f7.png)
  
3. In the **域名解析记录列表** (DNS record list) section, make sure that the fields are set to precisely the following values for the empty record: 
    
  - **主机名** (host name): **@**
    
  - **记录类型** (record type): **TXT记录** (TXT record) 
    
  - **记录值** (value): Paste **Destination or Points to Address** value that you just copied. 
    
    ![Add TXT record](../media/6b20a743-1d8b-463f-978a-d48f21846001.png)
  
4. Click **立即添加** (add). 
    
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
  
1. In your browser, go to [your domains list at CNDNS](http://www.cndns.com/userpanel/dme_mng/dme_lst.asp) and sign in. 
    
    ![Sign in to CNDNS](../media/e9a982be-5751-49ca-a6e5-c227eedffc7e.png)
  
2. In the **操作** (actions) column for the domain that you want to update, click **管理** (manage). 
    
    ![Click "管理"](../media/147aaab8-f9ac-43ca-a6da-142558e4019e.png)
  
3. Click the **修改DNS** (change name servers) tab. 
    
    ![Click "修改域名DNS"](../media/8da03250-378f-42ae-b009-d1e38882a781.png)
  
4. In the **DNS1** row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/17c62d01-416b-4815-8a8f-0b13879aaace.png)
  
5. In the **DNS2** row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


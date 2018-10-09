---
title: "Change nameservers to set up Office 365 with ZGSJ"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_ZGSJ1'
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- GEA150
ms.assetid: 992a2ba5-77f6-4286-8907-039e3c3f575c
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when ZGSJ is the DNS hosting provider."
---

# Change nameservers to set up Office 365 with ZGSJ

Follow these instructions if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at zgsj](create-dns-records-at-zgsj.md).)
  
Here's what you need to do:
  
- [Add a TXT record to verify that you own the domain](change-nameservers-at-zgsj.md#BKMK_add_a_record)
    
- [Change your domain's nameserver records](change-nameservers-at-zgsj.md#BKMK_change_your_domain_s_1)
    
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. In your browser, go to the [zgsj website](http://www.zgsj.com) and sign in. 
    
    ![Sign in to zgsj](../media/25f81db6-5dd4-4895-817a-5ff33ddc394d.png)
  
2. In the left pane, in the **产品管理** (product management) section, click **域名管理** (domain management). 
    
    ![Click "域名管理"](../media/0934df0b-1dc5-4560-9d8e-ac18df6c55e2.png)
  
3. In the right pane, in the **控制面板** (control panel) column for the domain that you want to update, click **登录解析**(sign in).
    
    ![Click "登录解析"](../media/c184cca7-145d-4052-9922-a69387129813.png)
  
4. In the control panel for your domain, in the left pane, click **DNS解析管理** (DNS management). 
    
    The DNS records page for your domain opens.
    
    ![Click "DNS解析管理"](../media/fff3ce9f-1b40-4ae9-80e6-0208121226b2.png)
  
5. In the right pane, click **增加TXT** (add a TXT record). 
    
6. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **智能DNS** (network): Use the default value. 
    
    ![Click "增加TXT"](../media/9ac6b204-a5d9-48ac-ba11-82c1dee9620a.png)
  
  - ** 主机名 ** (host name): Leave the box blank. 
    
  - ** 值 ** (value): Paste **Destination or Points to Address** value that you just copied. 
    
    ![Add TXT record](../media/94520f94-5625-48e7-816e-34873243a0cc.png)
  
7. Click **增加** (add). 
    
8. In the confirmation dialog box, click **OK**.
    
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
  
1. In your browser, go to the [zgsj website](http://www.zgsj.com) and sign in. 
    
    ![Sign in to zgsj](../media/25f81db6-5dd4-4895-817a-5ff33ddc394d.png)
  
2. In the left pane, in the **产品管理** (product management) section, click **域名管理** (domain management). 
    
    ![Click "域名管理"](../media/0934df0b-1dc5-4560-9d8e-ac18df6c55e2.png)
  
3. In the right pane, in the **控制面板** (control panel) column for the domain that you want to update, click **登录解析**(sign in).
    
    ![Click "登录解析"](../media/c184cca7-145d-4052-9922-a69387129813.png)
  
4. In the control panel for your domain, in the left pane, click **修改域名DNS** (change name servers). 
    
    ![Click "修改域名DNS"](../media/c8fb18fa-cdfc-4614-9b1a-690889a05661.png)
  
5. In the first box (primary name server), type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/375f358b-6f90-4a38-8947-ebaeb527f21a.png)
  
6. In the second box (secondary name server), type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
7. Click **确定** (OK). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


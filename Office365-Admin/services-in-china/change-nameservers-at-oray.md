---
title: "Change nameservers to set up Office 365 with Oray"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Oray1'
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- domainsgallatin
search.appverid:
- MET150
- GEA150
ms.assetid: a97682c3-fa3b-457b-9bf1-ea8b7490941a
description: "Learn how you can set up Office 365 operated by 21Vianet to manage your DNS records, when Oray is the DNS hosting provider."
monikerRange: 'o365-21vianet'
---

# Change nameservers to set up Office 365 with Oray

Follow the instructions below if you want Office 365 operated by 21Vianet to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your DNS records at Oray](create-dns-records-at-oray.md).)

    
## Find your DNS records at Oray
<a name="BKMK_find_your_dns"> </a>

Use the steps in the following table to get to the right spot in the Oray website to edit your DNS records.
  
|**Task**|**What you'll see**|
|:-----|:-----|
|1.  Go to the page that has the DNS records for your domain.  <br/><br/>2.  In your browser, go to [your domains list at Oray](https://console.oray.com/domain/root) and sign in.  <br/><br/>3. In the right pane, in the **解析设置** (DNS record management) column for the domain that you want to update, click **DNS解析设置** (DNS record management).  <br/> <br/> The DNS records page for your domain opens.  <br/> |![Sign in to Oray](../media/b55798c7-e143-454f-a3d3-7fd8733cba46.png)           <br/> ![Click "DNS解析设置"](../media/90257c23-ac07-4fab-83e7-7ae96693f667.png)           <br/> |
   
## Add a TXT record to verify that you own the domain
<a name="BKMK_add_a_record"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. On the Oray website, open the DNS records page for your domain. 
    
    To find the DNS records page for your domain, see [Find your DNS records at Oray](#find-your-dns-records-at-oray).
    
2. In the **域名解析设置** (DNS record management) list, click the **@** subdomain name. 
    
    ![Click "@'](../media/4deba23f-034c-42dc-8cae-29009e6229d9.png)
  
3. Click the **TXT记录** (TXT record) tab. 
    
    ![Click "TXT记录"](../media/85379c31-da07-4dc5-ac4e-0e6cb9a99957.png)
  
4. Make sure that the fields are set to precisely the following values for the empty record:
    
  - **说明** (value): Paste **Destination or Points to Address** value that you just copied. 
    
  - **TTL**: **3600**
    
    ![Add TXT record](../media/5681f501-bccd-4b3d-8e5b-55272b01b833.png)
  
5. Click **增加** (add). 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Manage domains** page, in the **Action** column for the domain you are verifying, choose **Start setup**.
    
    
  
3. On the **Add this TXT record to show you own** ***domain_name*** page, choose **Okay, I've added the record** and then, in the confirmation dialog box, choose **Finish**.
    
    
  
## Change your domain's nameserver records
<a name="BKMK_change_your_domain_s_1"> </a>

To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 operated by 21Vianet primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Lync, and your public website work with your domain, and you'll be all set.
  
> [!CAUTION]
> When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*.com) will start coming to Office 365 after you make this change. 
  
1. In your browser, go to [your domains list at Oray](https://console.oray.com/domain/root) and sign in. 
    
    ![Sign in to Oray](../media/b55798c7-e143-454f-a3d3-7fd8733cba46.png)
  
2. Click name of the domain that you're changing.
    
    ![Click the domain name](../media/66511199-21a4-4e45-ae0b-7a114560c13b.png)
  
3. Click **DNS管理** (DNS management). 
    
    ![Click "DNS管理"](../media/c6f4431d-1585-4b58-9998-c7feff929ec7.png)
  
4. In the **NS1** row, type or paste **ns1.dns.partner.microsoftonline.cn**. 
    
    ![Change name servers](../media/6a727037-5665-4fd9-af68-435f2dcaed75.png)
  
5. In the **NS2** row, type or paste **ns2.dns.partner.microsoftonline.cn**. 
    
6. Click **保存** (save). 
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain. 
  


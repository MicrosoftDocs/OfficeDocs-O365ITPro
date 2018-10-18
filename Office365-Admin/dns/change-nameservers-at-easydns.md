---
title: "Change nameservers to set up Office 365 with easyDNS"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: 833129de-9f9f-4390-a82c-4c61c7d79c72
description: "Learn how you can set up Office 365 to manage the DNS records of your custom domain at easyDNS."
---

# Change nameservers to set up Office 365 with easyDNS

[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
When you redelegate your domain to Office 365 by changing your nameserver records, Office 365 configures all of your DNS records for you. Follow the instructions below to verify your domain and repoint your NS records.
  
## Verify that you own the domain with a TXT record

1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **dns.**
    
3. Under the **TXT records** heading, click the edit button (wrench icon). 
    
4. Enter the following records in the text fields:
   

|**Host**|**Text**|
|:-----|:-----|
|@  <br/> |MS=msXXXXXXXX (Use the value provided to you on the Admin Center Domains page)  <br/> |
   
5. Choose **NEXT**. 
    
6. Check to make sure the record is correct, and then choose **CONFIRM**. 
    
7. Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. In the Admin Center, choose **Setup** \> **Domains**
    
10. On the **Domains** page, choose the domain that you are verifying. 
    
11. On the **Setup** page, choose **Start setup.**
    
12. On the **Verify domain** page, choose **Verify**. 
    
## Change your NS records

1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **nameservers**. 
    
3. Delete the existing nameserver records (if there are any) and add the following:

|||
|:-----|:-----|
|**Nameserver 1**  |     ns1.bdm.microsoftonline.com    |
|**Nameserver 2**    |      ns2.bdm.microsoftonline.com   |
|**Nameserver 3 (optional)**   |    ns3.bdm.microsoftonline.com     |
|**Nameserver 4 (optional)** |    ns4.bdm.microsoftonline.com     |


   
4. Choose **NEXT**. 
    
5. Check to make sure the record is correct, and then choose **CONFIRM**. 
    


---
title: "Create DNS records at easyDNS for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
ms.assetid: f1951923-6f81-4e06-9744-0dd214a8bd69
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at easyDNS for Office 365."
---

# Create DNS records at easyDNS for Office 365

[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
You'll need to add all of the following DNS records at your registrar's website to route mail to Office 365, use your domain for Teams and Skype for Business, and so on.
  
> [!NOTE]
> SRV Records are currently NOT available under all easyDNS service packages. You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Office 365 Skype for Business. 
  
## Verify that you own the domain with a TXT record

1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **dns.**
    
    ![Click dns to view DNS associated to the domain](../media/7c6e10d5-3f53-4a60-980e-ea1c5b030bd3.png)
  
3. Under the **TXT records** heading, click the edit button (wrench icon). 
    
    ![Click the wrench icon to edit the DNS settings](../media/eca85ee8-1359-4563-ad89-75bc82099d9f.png)
  
4. Enter the following records in the text fields:
    
1. 

|**Host**|**Text**|
|:-----|:-----|
|@  <br/> |MS=msXXXXXXXX (Use the value provided to you on the Admin Center Domains page)  <br/> |
   
5. Choose **NEXT**. 
    
    ![Next](../media/171f96a6-d577-47e8-9e8a-8f684ffedb78.png)
  
6. Check to make sure the record is correct, and then choose **CONFIRM**. 
    
    ![Confirm](../media/4316875b-ebed-46ed-8f0a-d9b6978b2a2d.png)
  
7. Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Office 365.
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. In the Admin Center, choose **Setup** \> **Domains**
    
10. On the **Domains** page, choose the domain that you are verifying. 
    
11. On the **Setup** page, choose **Start setup.**
    
12. On the **Verify domain** page, choose **Verify**. 
    
## Add an MX record to route email to Office 365

1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **dns.**
    
    ![Click dns to view DNS associated to the domain](../media/7c6e10d5-3f53-4a60-980e-ea1c5b030bd3.png)
  
3. Under the **MX records** heading, click the edit button (wrench icon). 
    
    ![Click the wrench icon to edit the DNS settings](../media/eca85ee8-1359-4563-ad89-75bc82099d9f.png)
  
4. Enter the following records in the text fields:
    
1. 

|**MAIL FOR ZONE**|**MAIL SERVER**|**PREF**|
|:-----|:-----|:-----|
|@  <br/> |\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the Admin Center Domains page)  <br/> |0  <br/> |
   
2. If you want to save your other MX records for backup purposes, copy them down somewhere. Before moving on, remove all other MX records here.
    
5. Choose **NEXT**. 
    
    ![Next](../media/171f96a6-d577-47e8-9e8a-8f684ffedb78.png)
  
6. Check to make sure the record is correct, and then choose **CONFIRM**. 
    
    ![Confirm](../media/4316875b-ebed-46ed-8f0a-d9b6978b2a2d.png)
  
## Add the required CNAME records

1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **dns.**
    
    ![Click dns to view DNS associated to the domain](../media/7c6e10d5-3f53-4a60-980e-ea1c5b030bd3.png)
  
3. Under the **CNAME/Alias records** heading, click the edit button (wrench icon). 
    
    ![Click the wrench icon to edit the DNS settings](../media/eca85ee8-1359-4563-ad89-75bc82099d9f.png)
  
4. Enter the following records in the text fields:
    
1. 

|**HOST**|**Address (Must end with a ".")**|
|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
|sip  <br/> |sipdir.online.lync.com.  <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
|msoid  <br/> |clientconfig.microsoftonline-p.net.  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> |
   
5. Choose **NEXT**. 
    
    ![Next](../media/171f96a6-d577-47e8-9e8a-8f684ffedb78.png)
  
6. Check to make sure the record is correct, and then choose **CONFIRM**. 
    
    ![Confirm](../media/4316875b-ebed-46ed-8f0a-d9b6978b2a2d.png)
  
## Add a TXT record for SPF to help prevent email spam

1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **dns.**
    
    ![Click dns to view DNS associated to the domain](../media/7c6e10d5-3f53-4a60-980e-ea1c5b030bd3.png)
  
3. Under the **TXT records** heading, click the edit button (wrench icon). 
    
    ![Click the wrench icon to edit the DNS settings](../media/eca85ee8-1359-4563-ad89-75bc82099d9f.png)
  
4. Enter the following records in the text fields:
    
1. 

|**Host**|**Text**|
|:-----|:-----|
|@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Choose **NEXT**. 
    
    ![Next](../media/171f96a6-d577-47e8-9e8a-8f684ffedb78.png)
  
6. Check to make sure the record is correct, and then choose **CONFIRM**. 
    
    ![Confirm](../media/4316875b-ebed-46ed-8f0a-d9b6978b2a2d.png)
  
## Add the two SRV records that are required for Office 365

> [!NOTE]
> SRV Records are currently NOT available under easyDNS' Domain Plus service level. You may need to upgrade to a higher service level with easyDNS to add SRV records. 
  
1. Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials. 
    
2. Under the **all domains** heading, click on **dns.**
    
    ![Click dns to view DNS associated to the domain](../media/7c6e10d5-3f53-4a60-980e-ea1c5b030bd3.png)
  
3. Under the **SRV records** heading, click the edit button (wrench icon). 
    
    ![Click the wrench icon to edit the DNS settings](../media/eca85ee8-1359-4563-ad89-75bc82099d9f.png)
  
4. Enter the following records in the text fields:
    
1. 

|**SERVICE**|**PROTO**|**HOST**|**PRI**|**WGT**|**PORT**|**TARGET(Must end with a ".")**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
|_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Choose **NEXT**. 
    
    ![Next](../media/171f96a6-d577-47e8-9e8a-8f684ffedb78.png)
  
6. Check to make sure the record is correct, and then choose **CONFIRM**. 
    
    ![Confirm](../media/4316875b-ebed-46ed-8f0a-d9b6978b2a2d.png)
  


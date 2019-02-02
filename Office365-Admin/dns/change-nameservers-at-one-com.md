---
title: "Change nameservers to set up Office 365 with One.com"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 536db9ab-a307-462c-b66f-6967a23330f0
description: "Learn to set up your Office 365 custom domain with One.com if you want Office 365 to manage your DNS records. "
---

# Change nameservers to set up Office 365 with One.com

[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If One.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you change your NS records at One.com, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. You'll be prompted to log in. To get started, go to your domains page in One.com by using [this link](https://login.one.com/cp/). 
    
    ![One_login](../media/3645c056-6581-450a-b142-1c6c8d59287d.png)
  
2. Select **DNS**.
    
    ![One_DNS](../media/b25fa282-8be5-466d-ad1b-0002bbab52bb.png)
  
3. On the **DNS page**, choose **Web DNS**.
    
    ![One_WebDNS](../media/a675d000-c681-4bbb-b0ac-4cf74a12ab86.png)
  
4.     
    In the **Personal web DNS settings** section, enter the new TXT record.
    
    (If records already exist, use the last row of boxes to enter the new record.)
    
    Under **Type**, choose **TXT**, and then type or copy and paste the values from the table below into the boxes for the new record.
    
|**Domain**|**Type**|**TTL**|**Priority**|**Value**|
|:-----|:-----|:-----|:-----|:-----|
|( leave blank )  <br/> |TXT  <br/> |3600 (seconds)  <br/> |( leave blank )  <br/> |MS=msXXXXXXX  <br/> **Note**: This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)
    
![One_VerificationTXT_values](../media/66589927-98e2-4acb-a333-baadf473db2b.png)
  
5. Select the green **+** icon to save the record. 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Change nameservers

1. Log in to your One.com control panel
    
2. Click **DNS**.
    
3. Click **Name servers** in the menu. 
    
4. Select **custom name servers** and enter the following values: 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3 (optional)** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4 (optional)** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
5. Click **Save**. 
    
    This change can take up to 24 hours to take effect.
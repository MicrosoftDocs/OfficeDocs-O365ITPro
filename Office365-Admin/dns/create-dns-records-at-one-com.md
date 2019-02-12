---
title: "Create DNS records at One.com for Office 365"
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
ms.assetid: a185414d-a469-4366-acbe-33880dfee05c
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at One.com for Office 365."
---

# Create DNS records at One.com for Office 365

[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If One.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](#add-a-txt-record-for-verification)
    
- [Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Add the CNAME records that are required for Office 365](#add-the-cname-records-that-are-required-for-office-365)

- [Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
After you add these records at One.com, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="bkmk_txt"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. You'll be prompted to log in. To get started, go to your domains page in One.com by using [this link](https://login.one.com/cp/). 
    
    ![One_login](../media/3645c056-6581-450a-b142-1c6c8d59287d.png)
  
2. Select **DNS**.
    
    ![One_DNS](../media/b25fa282-8be5-466d-ad1b-0002bbab52bb.png)
  
3. On the **DNS** page, choose **Web DNS**.
    
    ![One_WebDNS](../media/a675d000-c681-4bbb-b0ac-4cf74a12ab86.png)
  
4. In the **Personal web DNS settings** section, enter the new TXT record. 
    
    (If records already exist, use the last row of boxes to enter the new record.)
    
    Under **Type**, choose **TXT**, and then copy and paste the values from the table below into the boxes for the new record.
    
    |**Domain**|**Type**|**TTL**|**Priority**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |( leave blank )  <br/> |TXT  <br/> |3600 (seconds)  <br/> |( leave blank )  <br/> |MS=msXXXXXXX  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)   |
   
    ![One_VerificationTXT_values](../media/66589927-98e2-4acb-a333-baadf473db2b.png)
  
5. Select the green **+** icon to save the record. 
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="bkmk_mx"> </a>

1. You'll be prompted to log in. To get started, go to your domains page in One.com by using [this link](https://login.one.com/cp/). 
    
    ![One_login](../media/3645c056-6581-450a-b142-1c6c8d59287d.png)
  
2. Select **DNS**.
    
    ![One_DNS](../media/b25fa282-8be5-466d-ad1b-0002bbab52bb.png)
  
3. On the **DNS** page, choose **Web DNS**.
    
    ![One_WebDNS](../media/a675d000-c681-4bbb-b0ac-4cf74a12ab86.png)
  
4. Delete any existing MX records by choosing the red **-** icon next to each record. 
    
5. In the **Personal mail DNS settings** section, enter the new MX record. Under **Type**, choose **MX**, and then type or copy and paste the values from the table below into the boxes for the new record.
    
    |**Domain﻿**|**Type﻿**|**Priority﻿**|**Server﻿**|
    |:-----|:-----|:-----|:-----|
    |(your domain)  <br/> |MX  <br/> |10  <br/> For more information about priority, see [What is MX priority](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)?  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 account.   [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![One_MX_values](../media/03515b54-5b05-4f37-9261-7d5cafe3fb4d.png)
  
6. Select the green **+** icon to save the record. 
    
## Add the CNAME records that are required for Office 365
<a name="bkmk_cname"> </a>

1. You'll be prompted to log in. To get started, go to your domains page in One.com by using [this link](https://login.one.com/cp/). 
    
    ![One_login](../media/3645c056-6581-450a-b142-1c6c8d59287d.png)
  
2. Select **DNS**.
    
    ![One_DNS](../media/b25fa282-8be5-466d-ad1b-0002bbab52bb.png)
  
3. On the **DNS** page, choose **Web DNS**.
    
    ![One_WebDNS](../media/a675d000-c681-4bbb-b0ac-4cf74a12ab86.png)
  
4. In the **Personal mail DNS settings section**, enter the new CNAME records. 
    
    Under **Type**, choose **CNAME**, and then type or copy and paste the values from the table below into the boxes for the new record.
    
    > [!NOTE]
    > If records already exist in the **Personal web DNS settings** section, use the last row of boxes to enter a new record. 
  
    |**Domain (Hostname)**|**Type**|**Value (Destination)**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
       
     ![One_CNAME_values](../media/6177025e-408b-44a6-9ab8-3f6406828abe.png)
  
5. Select the green **+** icon to save the record. 
    
6. Repeat the previous steps to create the other five CNAME records. For each record, type of copy and paste the values from the next row of the table above into the boxes for that record.
    
## Add a TXT record for SPF to help prevent email spam
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. You'll be prompted to log in. To get started, go to your domains page in One.com by using [this link](https://login.one.com/cp/). 
    
    ![One_login](../media/3645c056-6581-450a-b142-1c6c8d59287d.png)
  
2. Select **DNS**.
    
    ![One_DNS](../media/b25fa282-8be5-466d-ad1b-0002bbab52bb.png)
  
3. On the **DNS** page, choose **Web DNS**.
    
    ![One_WebDNS](../media/a675d000-c681-4bbb-b0ac-4cf74a12ab86.png)
  
4. In the **Personal web DNS settings** section, enter the new TXT record. Under **Type**, choose **TXT**, and then type or copy and paste the values from the table below into the boxes for the new record.
    
    > [!NOTE]
    > If records already exist in the **Personal web DNS settings** section, use the last row of boxes to enter a new record. 
  
    |**Domain**|**Type**|**TTL**|**Priority**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |(leave blank)  <br/> |TXT  <br/> |3600 (seconds)  <br/> |(leave blank)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
       
     ![One_TXT_SPF_values](../media/3c60057e-9a2f-4ebc-8b9d-6c37f54d6236.png)
  
5. Select the green **+** icon to save the record. 
    
## Add the two SRV records that are required for Office 365
<a name="bkmk_srv"> </a>

1. You'll be prompted to log in. To get started, go to your domains page in One.com by using [this link](https://login.one.com/cp/). 
    
    ![One_login](../media/3645c056-6581-450a-b142-1c6c8d59287d.png)
  
2. Select **DNS**.
    
    ![One_DNS](../media/b25fa282-8be5-466d-ad1b-0002bbab52bb.png)
  
3. On the **DNS** page, choose **Web DNS**.
    
    ![One_WebDNS](../media/a675d000-c681-4bbb-b0ac-4cf74a12ab86.png)
  
4. In the **Personal web DNS settings** section, enter the new SRV record. Under **Type**, choose **SRV**, and then type or copy and paste the values from the table below into the boxes for the new record.
    
    > [!NOTE]
    > If records already exist in the **Personal web DNS settings** section, use the last row of boxes to enter a new record. 
  
    |**Domain**|**Type**|**TTL**|**Priority**|**Value (Destination)**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV (Service)  <br/> |3600 (seconds)  <br/> |100  <br/> |1 443 sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV (Service)  <br/> |3600 (seconds)  <br/> |100  <br/> |1 5061 sipfed.online.lync.com  <br/> |
       
    ![One_SRV_values](../media/630e5c17-8971-471f-9f00-2b5f0e038b5c.png)
  
5. Select the green **+** icon to save the record. 
    
6. Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

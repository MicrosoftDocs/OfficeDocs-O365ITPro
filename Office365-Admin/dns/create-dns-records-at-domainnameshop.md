---
title: "Create DNS records at Domainnameshop for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 152a58aa-6974-43a3-819f-9cf4f3f13376
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Domainnameshop for Office 365."
---

# Create DNS records at Domainnameshop for Office 365

[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If Domainnameshop is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at Domainnameshop, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="bkmk_txt"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Domainnameshop by using [this link](https://www.domainnameshop.com/login). You'll be prompted to log in. 
    
    ![Login screen in Domainnameshop](../media/94d9df22-d43e-4f12-910c-33df1dd772af.png)
  
2. Choose **My Domains**. 
    
    ![My domains tab selected in Domainnameshop](../media/642a86bc-6c4a-4e39-9639-99513dab9444.png)
  
3. Choose the domain that you want to edit. 
    
    ![Active domain selected in Domainnameshop](../media/a16c33b3-21e4-4112-a4b0-a703a3958601.png)
  
4. Choose the **DNS records** tab. 
    
    ![DNS records tab highlighted in Domainnameshop](../media/9387965e-b467-451a-9311-8a17a09f3546.png)
  
5. Choose **Show advanced settings**. 
    
    ![Show advanced settings in Domainnameshop](../media/b3ed8d12-ba67-4610-bd4b-3c1d0a1db3c8.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Host name**|**TTL**|**RR Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(leave blank)  <br/> |1 hour  <br/> |TXT  <br/> |MS=msXXXXXXXX  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![TXT record in Domainnameshop](../media/f2ec5943-5b8d-4028-90f8-4a1344264e68.png)
  
7. Choose the **+** (Add) button. 
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
## Add an MX record so email for your domain will come to Office 365
<a name="bkmk_mx"> </a>

1. To get started, go to your domains page in Domainnameshop by using [this link](https://domainnameshop.com/login). You'll be prompted to log in. 
    
    ![Login screen in Domainnameshop](../media/ed048ac8-7953-46af-943b-7648b98ecb37.png)
  
2. Choose **My Domains**. 
    
    ![My domains in Domainnameshop](../media/666a470a-eb65-443b-8853-19ca5b5a19ca.png)
  
3. Choose the domain that you want to edit. 
    
    ![A domain selected in My domains in Domainnameshop](../media/02b88edb-a70d-44c5-a9e0-3aec288fdaa7.png)
  
4. Choose the **DNS records** tab. 
    
    ![DNS records tab in Domainnameshop](../media/3059be18-e092-407c-ab15-158001f2dced.png)
  
5. Choose **Show advanced settings**. 
    
    ![Show advanced settings for DNS records in Domainnameshop](../media/ee3d46b1-493e-415d-9d09-f6b988a8bea3.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Host name**|**TTL**|**RR Type**|**Parameters (Priority)**|**Data (Target)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(leave blank)  <br/> |1 hour  <br/> |MX (Mail Exchanger)  <br/> |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MX record in Domainnameshop](../media/0062bbcb-afb0-4a77-9d9c-c595ab4027d4.png)
  
7. Choose the **+** (Add) button. 
    
    ![Add MX record in Domainnameshop](../media/60ea145e-b643-4cae-80ac-e16cd0262410.png)
  
8. If there are any other MX records in the list, delete each one by choosing the trash can icon next to it.
    
## ﻿Add the CNAME records that are required for Office 365
<a name="bkmk_cname"> </a>

1. To get started, go to your domains page in Domainnameshop by using [this link](https://www.domainnameshop.com/login). You'll be prompted to log in. 
    
    ![Login screen in Domainnameshop](../media/62dda950-a075-474e-9902-46f74fdd9aea.png)
  
2. Choose **My Domains**. 
    
    ![My domains tab in Domainnameshop](../media/fad88b50-eae9-42ff-9e37-dd00900e3738.png)
  
3. Choose the domain that you want to edit. 
    
    ![Domain name selected in Domainnameshop](../media/ec784c3f-9c5a-4353-8bc6-eab757b55732.png)
  
4. Choose the **DNS records** tab. 
    
    ![Domainnameshop DNS records tab](../media/a4c45521-ec29-4ca4-9167-a3585c70b1b4.png)
  
5. Choose **Show advanced settings**. This link toggles between two modes: normal settings and advanced settings. If you see **Show normal settings**, you are already in the advanced settings mode.
    
    ![Show advanced settings in Domainnameshop](../media/57c2f122-19a3-4242-ad0b-50812dea4485.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Host name**|**TTL**|**RR Type**|**Data (Target)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |1 hour  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |autodiscover  <br/> |1 hour  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |autodiscover  <br/> |1 hour  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |msoid  <br/> |1 hour  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    |enterpriseregistration  <br/> |1 hour  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |1 hour  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![RR record values in Domainnameshop](../media/71bfc469-23a9-4805-b64b-28098f9757e8.png)
  
7. Choose the **+** (Add) button. 
    
8. Repeat the previous steps to create the other five CNAME records. For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.
    
## Add a TXT record for SPF to help prevent email spam
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. To get started, go to your domains page in Domainnameshop by using [this link](https://www.domainnameshop.com/login). You'll be prompted to log in. 
    
    ![Login screen in Domainnameshop](../media/80d1916c-46bc-496f-890c-a80a2f13931c.png)
  
2. Choose **My Domains**. 
    
    ![My domains in Domainnameshop](../media/7ea2a147-b12e-49ad-8fe3-ceb34240d640.png)
  
3. Choose the domain that you want to edit. 
    
    ![Domain name selected in Domainnameshop](../media/f3663ae9-d39e-43b8-ab34-fafd8b10b601.png)
  
4. Choose the **DNS records** tab. 
    
    ![DNS records tab in Domainnameshop](../media/151432dd-a18f-4db6-9e73-f42aa7027869.png)
  
5. Choose **Show advanced settings**. This link toggles between two modes: normal settings and advanced settings. If you see **Show normal settings**, you are already in the advanced settings mode. 
    
    ![Show advanced settings for DNS records in Domainnameshop](../media/e0e793cc-fb24-434b-abfe-2944ff4175c1.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Host name**|**TTL**|**RR Type**|**Data (Target)**|
    |:-----|:-----|:-----|:-----|
    |(leave blank)  <br/> |1 hour  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![TXT record in DNS record in Domainnameshop](../media/c4957cf7-ac21-4345-ad72-90fd879ac83c.png)
  
7. Choose the **+** (Add) button. 
    
## Add the two SRV records that are required for Office 365
<a name="bkmk_srv"> </a>

To get started, go to your domains page in Domainnameshop by using [this link](https://www.domainnameshop.com/login). You'll be prompted to log in.
  
1. Choose **My Domains**. 
    
    ![My Domains in Domainnameshop](../media/6057954a-6777-4d40-877a-257bb600b933.png)
  
2. Choose the domain that you want to edit. 
    
    ![Select the domain in Domainnameshop](../media/21fc0117-70a7-470c-b184-2031e2cc3ef7.png)
  
3. Choose the **DNS records** tab. 
    
    ![DNS records tab in Domainnameshop](../media/c2cd4aed-58cb-49b1-9a53-d06db77eeb8f.png)
  
4. Choose **Show advanced settings**. This link toggles between two modes: normal settings and advanced settings. If you see **Show normal settings**, you are already in the advanced settings mode. 
    
    ![Show advanced settings for DNS record in Domainnameshop](../media/aaa7fbe4-4575-41eb-b416-6be07291d81d.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Host name**|**TTL**|**RR Type**|**Parameters (Priority)**|**Parameters (Weight)**|**Parameters (Port)**|**Data**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |1 hour  <br/> |SRV (Service)  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |1 hour  <br/> |SRV (Service)  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![SRV record in Domainnameshop](../media/6ebbf167-229a-4c58-8a83-4d1e6223f553.png)
  
6. Choose the **+** (Add) button. 
    
7. Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  


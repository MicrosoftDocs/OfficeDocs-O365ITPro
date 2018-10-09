---
title: "Create DNS records at Onamae for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a321b635-526f-4c79-8e97-18c1789db685

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Onamae for Office 365."
---

# Create DNS records at Onamae for Office 365

[C﻿heck the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If Onamae is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](create-dns-records-at-onamae.md#bkmk_txt)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-onamae.md#bkmk_mx)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-onamae.md#bkmk_cname)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-onamae.md#bkmk_spf)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-onamae.md#bkmk_srv)
    
After you add these records at Onamae, your domain will be set up to work with Office 365 services.
  
To learn about web hosting and DNS for websites with [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="bkmk_txt"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log on.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3. Select the radio button next to the domain, and then choose **Next**.
    
    ![Callout next to the domain name in Onamae](../media/2bd27471-8dea-49ea-b4e1-b54fa0f620a2.png)
  
4. Next to **Use DNS record settings**, choose **Set up**.
    
    ![Set up button in Onamae](../media/73def81e-d25a-426b-bde6-cf12c5861885.png)
  
5. In the entry fields for new DNS records, select **TXT**, and then type or copy and paste the values from the following table.
    
|**Host name**|**Type**|**TTL**|**Value (Points to address or value)**|
|:-----|:-----|:-----|:-----|
|(leave blank)  <br/> |TXT  <br/> |3600          (seconds)  <br/> |MS=msXXXXXXXX  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![TXT Value for a new DNS record in Onamae](../media/f4f0c932-3659-47dd-90fc-919ed5657c86.png)
  
6. Choose **Add**.
    
    ![Add button for TXT value in Onamae](../media/6aa5b0c2-a20e-453e-9b84-dbdbbcfb3419.png)
  
7. At the bottom of the page, choose **Go to confirmation screen**
    
    ![Go to confirmation screen in Onamae](../media/230f27d6-82b0-42dc-a61a-d26dc1b9cee6.png)
  
8. At the bottom of the Confirmation screen, choose **Set up**.
    
    ![Confirm set up in Onamae](../media/63a91c3a-26b3-42c3-9d40-0922a8398ad6.png)
  
9. At the bottom of the page, select **Continue the procedure**.
    
    ![Continue the procedure button in Onamae](../media/7a38f2db-b9ea-4907-865e-263b0cdc57cd.png)
  
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup button](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify button](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="bkmk_mx"> </a>

1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log on.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3. Select the radio button next to the domain, and then choose **Next**.
    
    ![Callout next to the domain name in Onamae](../media/2bd27471-8dea-49ea-b4e1-b54fa0f620a2.png)
  
4. Next to **Use DNS record settings**, choose **Set up**.
    
    ![Set up button in Onamae](../media/73def81e-d25a-426b-bde6-cf12c5861885.png)
  
5. Under **Registered**, if any MX records are listed, select the **Delete** checkbox for the record. Choose **Go to confirmation screen**, choose **Set up**, and then choose **Continue the procedure**.
    
6. In the entry fields for new DNS records, select **MX**, and then type or copy and paste the values from the following table .
    
|**Hostname**|**Type**|**TTL(SEC)**|**Value (Points to address or value)**|**Priority**|
|:-----|:-----|:-----|:-----|:-----|
|(leave blank)  <br/> |MX (Mail Exchanger)  <br/> |3600          (seconds)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![MX value](../media/6a4e60a8-ba40-49ca-9677-264f787cb04d.png)
  
7. Choose **Add**.
    
    ![Add MX value](../media/dcf5704d-5dd5-420d-8e42-cfaa8c01d9d8.png)
  
8. At the bottom of the page, choose **Go to confirmation screen**.
    
    ![Go to confirmation screen in Onamae](../media/9067dce0-e215-4bef-9330-0277a534aeee.png)
  
9. At the bottom of the Confirmation screen, choose **Set up**.
    
    ![Set up button in Onamae](../media/24a1ff6f-4283-4d1a-b43c-ad69ae834c8f.png)
  
10. At the bottom of the page, select **Continue the procedure**.
    
    ![Continue the procedure button](../media/4afc86e2-5364-4079-8240-21f1501cc55d.png)
  
## Add the CNAME records that are required for Office 365
<a name="bkmk_cname"> </a>

1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log on.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3. Select the radio button next to the domain, and then choose **Next**.
    
    ![Callout next to the domain name in Onamae](../media/2bd27471-8dea-49ea-b4e1-b54fa0f620a2.png)
  
4. Next to **Use DNS record settings**, choose **Set up**.
    
    ![Set up button in Onamae](../media/73def81e-d25a-426b-bde6-cf12c5861885.png)
  
5. In the entry fields for new DNS records, select **CNAME**, and then type or copy and paste the values from the following table.
    
|**Hostname﻿**|**Type﻿**|**TTL (SEC)﻿**|**Value (Points to or address value)﻿**|
|:-----|:-----|:-----|:-----|
|autodiscover  <br/> |CNAME  <br/> |3600          (seconds)  <br/> |autodiscover.outlook.com  <br/> |
|sip  <br/> |CNAME  <br/> |3600          (seconds)  <br/> |sipdir.online.lync.com  <br/> |
|lyncdiscover  <br/> |CNAME  <br/> |3600          (seconds)  <br/> |webdir.online.lync.com  <br/> |
|msoid  <br/> |CNAME  <br/> |3600          (seconds)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|enterpriseregistration  <br/> |CNAME  <br/> |3600          (seconds)  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |3600          (seconds)  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![CNAME value](../media/4456c3ba-df9c-4461-85fa-bb4f64c66d49.png)
  
6. Choose **Add**.
    
    ![Add button](../media/ec719e57-b70a-4460-8ff4-9599f516ea5b.png)
  
7. Repeat the steps 5 and 6 to create the other five CNAME records. For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.
    
8. At the bottom of the page, choose **Go to confirmation screen**.
    
    ![Go to confirmation screen in Onamae](../media/2e5ecf5c-9f12-4b60-aa7a-722f9433801d.png)
  
9. At the bottom of the Confirmation screen , choose **Set up**.
    
    ![Confirm set up in Onamae](../media/36ce7ac7-c716-4f86-ac7d-c0267e848b6e.png)
  
10. At the bottom of the page, select **Continue the procedure**.
    
    ![Continue the procedure](../media/536cd4d3-ce84-434e-8425-5dc3aa0f3ec2.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log on.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3. Select the radio button next to the domain, and then choose **Next**.
    
    ![Callout next to the domain name in Onamae](../media/2bd27471-8dea-49ea-b4e1-b54fa0f620a2.png)
  
4. Next to **Use DNS record settings**, choose **Set up**.
    
    ![Set up button in Onamae](../media/73def81e-d25a-426b-bde6-cf12c5861885.png)
  
5. 
    
    In the entry fields for new DNS records, select **TXT**, and then type or copy and paste the values from the following table.
    
|**Hostname**|**Type**|**TTL (SEC)**|**Value (Points to address or value)**|
|:-----|:-----|:-----|:-----|
|(leave blank)  <br/> | TXT  <br/> |3600 (seconds)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![TXT value](../media/5254895f-4272-45f9-9acc-ca0173a6a5a2.png)
  
6. Choose **Add**.
    
    ![Add button highlighted in TXT record](../media/323b444c-e441-411e-af54-19f2c35f80a8.png)
  
7. At the bottom of the page, choose **Go to confirmation screen**.
    
    ![Go to confirmation screen in Onamae](../media/6ebb504e-c4d5-4a44-9e49-a75e9fd6fe87.png)
  
8. At the bottom of the Confirmation screen, choose **Set up**.
    
    ![Confirm set up in Onamae](../media/241dae1b-21ed-43ff-ad75-b0acc916b0bc.png)
  
9. At the bottom of the page, select **Continue the procedure**.
    
    ![Continue the procedure button](../media/dbf7c390-d741-4999-a461-da269bd3ef40.png)
  
## Add the two SRV records that are required for Office 365
<a name="bkmk_srv"> </a>

1. To get started, go to your domains page in Onamae by using [this link](https://navi.onamae.com/login). If necessary, select **Domain Navi Login**. You'll be prompted to log on.
    
    ![Onamae login screen](../media/66bdffbf-6224-4f49-a998-5d6917968c8b.png)
  
2. Point to **Domain settings**, and then choose **DNS related function settings**.
    
    ![DNS related function settings in Onamae](../media/a98e91cf-5620-49a2-981b-912e53a277bb.png)
  
3. Select the radio button next to the domain, and then choose **Next**.
    
    ![Callout next to the domain name in Onamae](../media/2bd27471-8dea-49ea-b4e1-b54fa0f620a2.png)
  
4. Next to **Use DNS record settings**, choose **Set up**.
    
    ![Set up button in Onamae](../media/73def81e-d25a-426b-bde6-cf12c5861885.png)
  
5. 
    
    I﻿n the entry fields for new DNS records, select **SRV**, and then type or copy and paste the values from the following table.
    
|**Service name**|**Protocol**|**Hostname﻿**|**Type**|**TTL (SEC)**|**Priority**|**Weight﻿**|**Port﻿**|**Target﻿**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|_sip﻿  <br/> |_tls﻿  <br/> |(leave blank)﻿  <br/> |SRV (service)﻿  <br/> |3600          (seconds)﻿  <br/> |100﻿  <br/> |1﻿  <br/> |443﻿  <br/> |sipdir.online.lync.com  <br/> |
|_sipfederationtls  <br/> |_tcp  <br/> |(leave blank)﻿  <br/> |SRV (service)  <br/> |3600          (seconds)  <br/> |100﻿  <br/> |1﻿  <br/> |5061﻿  <br/> |sipfed.online.lync.com  <br/> |
   
    ![SRV values](../media/b7512d37-7b9b-4408-94ea-a5d62b159882.png)
  
6. Choose **Add**.
    
    ![Add button in SRV values](../media/6ce296a5-5914-419a-bc9a-f3cb4e5e18a9.png)
  
7. Repeat steps 5 and 6 to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.
    
8. At the bottom of the page, choose **Go to confirmation screen**.
    
    ![Go to confirmation screen in Onamae](../media/ae66cc05-3453-4b27-910a-c5c806437ead.png)
  
9. At the bottom of the Confirmation screen, choose **Set up**.
    
    ![Confirm set up in Onamae](../media/c9471b2f-5e69-424f-a439-4b4f2a4ce1de.png)
  
10. At the bottom of the page, select **Continue the procedure**.
    
    ![Continue the procedure](../media/41e909b5-a533-452b-972d-658487ecbff8.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  


---
title: "Create DNS records at NearlyFreeSpeech.net for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_NFS'
- 'O365M_DOM_NFS'
- 'O365E_DOM_NFS'
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
- Adm_UI_Elements
ms.custom:
- Adm_O365
- Adm_O365_FullSet
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ffc64782-442f-4ad2-ae81-33c3fbff5341
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at NearlyFreeSpeech.net for Office 365."
---

# Create DNS records at NearlyFreeSpeech.net for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If NearlyFreeSpeech.net is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-nearlyfreespeech-net.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-nearlyfreespeech-net.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-nearlyfreespeech-net.md#BKMK_add_MX)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-nearlyfreespeech-net.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-nearlyfreespeech-net.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-nearlyfreespeech-net.md#BKMK_add_SRV)
    
After you add these records at NearlyFreeSpeech.net, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/domains). You'll be prompted to log in first.
    
2. .In the **Domains** section, find the name of the domain that you want to edit and then, in the **DNS** column for that domain, choose **Manage**.
    
3. On the **DNS** page, in the **Actions** area, choose **Add a DNS Resource Record**.
    
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|Name  <br/> |Type  <br/> |Data  <br/> |TTL  <br/> |
|(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |3600  <br/> |
   
5. Choose **Add Record**.
    
6. Choose **Click here to continue...** to return to the DNS page. 
    
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Office 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/domains). You'll be prompted to log in first.
    
2. .In the **Domains** section, find the name of the domain that you want to edit and then, in the **DNS** column for that domain, choose **Manage**.
    
3. On the **DNS** page, in the **Actions** area, choose **Add a DNS Resource Record**.
    
4. In the boxes for the new record, type or paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Name**|**Type**|**Data**|**TTL**|
|:-----|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |MX  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> > [!NOTE]> Get your \< *domain-key*  \> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |3600  <br/> |
   
  ![NearlyFreeSpeech-BP-Configure-2-1](../media/82956d6b-ed21-4cd4-8d28-513f0f501a9b.png)
  
5. Choose **Add Record**.
    
    ![NearlyFreeSpeech-BP-Configure-2-2](../media/c2f7c429-cbf8-420c-8ff3-6abf62fc0ae8.png)
  
6. Choose **Click here to continue...** to return to the **DNS** page. 
    
    ![NearlyFreeSpeech-BP-Configure-2-4](../media/29ac85e5-0b19-4aa5-8825-23f122ed0a27.png)
  
7. If there are any other MX records, delete them:
    
    For one of the other MX records, choose **Remove** in the **X** column. 
    
    ![NearlyFreeSpeech-BP-Configure-2-3](../media/d4526745-d72a-4e23-aa0d-076487d5cf4e.png)
  
8. Choose **Click here to continue…** to return to the **DNS** page. 
    
    ![NearlyFreeSpeech-BP-Configure-2-4](../media/29ac85e5-0b19-4aa5-8825-23f122ed0a27.png)
  
9. Repeat the same process to delete any other MX records (first choosing **Remove** in the **X** column, and then choosing **Click here to continue…** to return to the **DNS** page), until only the one that you created earlier in this procedure remains. 
    
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/domains). You'll be prompted to log in first.
    
2. .In the **Domains** section, find the name of the domain that you want to edit and then, in the **DNS** column for that domain, choose **Manage**.
    
3. On the **DNS** page, in the **Actions** area, choose **Add a DNS Resource Record**.
    
4. Add the first of the CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Name**|**Type**|**Data**|**TTL**|
|:-----|:-----|:-----|:-----|
|autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
|sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
|lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
|msoid  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
|enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |
   
 ![NearlyFreeSpeech-BP-Configure-3-1](../media/3d67c502-1c76-47de-b746-b947876cb3cb.png)
  
5. Choose **Add Record**.
    
    ![NearlyFreeSpeech-BP-Configure-3-2](../media/eb273857-ab50-409f-90ff-d328c2088730.png)
  
6. Choose **Click here to continue…** to return to the **DNS** page. 
    
    ![NearlyFreeSpeech-BP-Configure-2-4](../media/29ac85e5-0b19-4aa5-8825-23f122ed0a27.png)
  
7. To add each of the other five CNAME records, choose **Add a DNS Resource Record** again, create a record using the values from the next row in the table, and then again choose **Add Record** to complete that record and **Click here to continue…** to return to the **DNS** page. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/domains). You'll be prompted to log in first.
    
2. .In the **Domains** section, find the name of the domain that you want to edit and then, in the **DNS** column for that domain, choose **Manage**.
    
3. On the **DNS** page, in the **Actions** area, choose **Add a DNS Resource Record**.
    
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
|**Name**|**Type**|**Data**|**TTL**|
|:-----|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |3600  <br/> |
   
 ![NearlyFreeSpeech-BP-Configure-4-1](../media/1d3efb49-6198-468d-a9e8-91b79dcd7722.png)
  
5. Choose **Add Record**.
    
    ![NearlyFreeSpeech-BP-Configure-4-2](../media/4b0e26be-0d31-43c9-9495-eb8b0f40582f.png)
  
6. Choose **Click here to continue…** to return to the **DNS** page. 
    
    ![NearlyFreeSpeech-BP-Configure-2-4](../media/29ac85e5-0b19-4aa5-8825-23f122ed0a27.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at NearlyFreeSpeech.net by using [this link](https://members.nearlyfreespeech.net/domains). You'll be prompted to log in first.
    
2. .In the **Domains** section, find the name of the domain that you want to edit and then, in the **DNS** column for that domain, choose **Manage**.
    
3. On the **DNS** page, in the **Actions** area, choose **Add a DNS Resource Record**.
    
4. Add the first of the two SRV records:
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Choose the **Type** value from the drop-down list.) 
    
|**Name**|**Type**|**Data**|**TTL**|
|:-----|:-----|:-----|:-----|
|_sip._tls|SRV|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |3600|
|_sipfederationtls._tcp|SRV|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**> [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |3600|
   
 ![NearlyFreeSpeech-BP-Configure-5-1](../media/067aadd6-4828-44bc-a57b-258746b0a8d6.png)
  
5. Choose **Add Record**.
    
    ![NearlyFreeSpeech-BP-Configure-5-2](../media/23919348-0d1c-4b17-b7eb-dce4b267171d.png)
  
6. Choose **Click here to continue…** to return to the **DNS** page. 
    
    ![NearlyFreeSpeech-BP-Configure-2-4](../media/29ac85e5-0b19-4aa5-8825-23f122ed0a27.png)
  
7. To add the other SRV record, choose **Add a DNS Resource Record** again, create a record using the values from the second row in the table, and then again choose **Add Record** to complete that record and **Click here to continue…** to return to the **DNS** page. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

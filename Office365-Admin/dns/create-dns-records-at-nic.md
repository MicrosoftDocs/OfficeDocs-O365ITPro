---
title: "Create DNS records at Network Information Center (NIC) for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_NIC'
- 'O365M_DOM_NIC'
- 'O365E_DOM_NIC'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
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
ms.assetid: 8b0ae817-f090-475f-92ba-1fb3239c1e63
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at NIC for Office 365."
---

# Create DNS records at Network Information Center (NIC) for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Network Information Center (NIC) is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business online, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](#add-a-txt-record-for-verification)
    
- [Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [Add the CNAME records that are required for Office 365](#add-the-cname-records-that-are-required-for-office-365)
    
- [Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
After you add these records at NIC, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose **Manage DNS** for the domain that you want to edit. 
    
4. On the **DNS Management** page, in the **Records** section, choose **Add**.
    
    (You may have to scroll down.)
    
5. Choose **TXT** from the **Type** drop-down list. 
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the TTL value from the drop-down list.)
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**TYPE** <br/> |**HOST** <br/> |**TXT Value** <br/> |**TTL** <br/> |
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1 Hour  <br/> |
   
7. Choose **Save**.
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Microsoft 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose **Manage DNS** for the domain that you want to edit. 
    
4. On the **DNS Management** page, in the **Records** section, choose **Add**.
    
    (You may have to scroll down.)
    
5. Choose **MX** from the **Type** drop-down list. 
    
    ![NIC-BP-Configure-2-1](../media/b7882dc3-8ee3-44b6-a9de-a3cafa1ff2f4.png)
  
6. In the boxes for the new record, type or paste the values from the following table.
    
    (Select the **TTL** value from the drop-down list.) 
    
    |**TYPE**|**HOST**|**POINTS TO**|**PRIORITY**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your \<*domain-key*\> from your Office 365 portal account. <br> [How do I find this?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1 Hour  <br/> |
   
    ![NIC-BP-Configure-2-2](../media/b6ac4a39-e894-46c6-8008-08ed1d247eee.png)
  
7. Choose **Save**.
    
    ![NIC-BP-Configure-2-3](../media/3281a1d9-2770-4493-84f0-dfb16674f93f.png)
  
8. If there are any other MX records, delete them all in the **MX** section of the **Domain Details** page. 
    
    First, choose the pencil **Edit** icon for each record. 
    
    ![NIC-BP-Configure-2-4](../media/e83920bf-e0c9-4696-8e93-aee84aee482b.png)
  
    Then choose the trash can **Delete Record** icon. 
    
    ![NIC-BP-Configure-2-5](../media/ca1b8f74-2be8-4265-bba2-77421e93ce2e.png)
  
9. Choose **Delete**.
    
    ![NIC-BP-Configure-2-6](../media/ee1a9894-049d-4f4d-bfca-b7a9ab98f7f7.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose **Manage DNS** for the domain that you want to edit. 
    
4. On the **DNS Management** page, in the **Records** section, choose **Add**.
    
    (You may have to scroll down.)
    
5. Choose **CNAME** from the **Type** drop-down list. 
    
    ![NIC-BP-Configure-3-1](../media/931c9785-83e8-4a0d-b8da-d799b29393d0.png)
  
6. Add the first CNAME record.
    
    In the boxes for the new record, type or paste the values from the first row in the following table.
    
    (Select the **TTL** value from the drop-down list.) 
    
    |**TYPE**|**HOST**|**POINTS TO**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 Hour  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |1 Hour  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 Hour  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
       
    ![NIC-BP-Configure-3-2](../media/47b8500f-cec5-446f-a3b8-b8ece1233efb.png)
  
7. Choose **Save**.
    
    ![NIC-BP-Configure-3-3](../media/b682c307-1579-4d7f-8a7b-20a9b387dfae.png)
  
8. Add the other five CNAME records.
    
    Use the same process, but use the values from each of the other five rows in the table.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose **Manage DNS** for the domain that you want to edit. 
    
4. On the **DNS Management** page, in the **Records** section, choose **Add**.
    
    (You may have to scroll down.)
    
5. Choose **TXT** from the **Type** drop-down list. 
    
    ![NIC-BP-Configure-4-1](../media/d4585381-0704-4655-a289-654e81d63774.png)
  
6. In the boxes for the new record, type or paste the values from the following table.
    
    (Select the **TTL** value from the drop-down list.) 
    
    |**TYPE**|**HOST**|**TXT VALUE**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct. |1 Hour  <br/> |
   
    ![NIC-BP-Configure-4-2](../media/7e9195f0-8da5-4e6b-8fb2-8f657189f078.png)
  
7. Choose **Save**.
    
    ![NIC-BP-Configure-4-3](../media/f9a818e5-f54b-4cd2-8a26-6574e2034a76.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at NIC by using [this link](https://sso.secureserver.net/). You'll be prompted to log in.
    
2. On the **Domain Admin** page, in the **Domains** row, choose **Manage**.
    
3. On the **Domains** page, choose the **Settings** icon, and then choose **Manage DNS** for the domain that you want to edit. 
    
4. On the **DNS Management** page, in the **Records** section, choose **Add**.
    
    (You may have to scroll down.)
    
5. Choose **SRV** from the **Type** drop-down list. 
    
    ![NIC-BP-Configure-5-1](../media/96b1a46c-df12-4d1a-9c71-6b0ceade2ce7.png)
  
6. Create the first SRV record.
    
    In the boxes for the first new record, type or copy and paste the values from the first row in the following table.
    
    (Select the **TTL** values from the drop-down list.) 
        
    |**TYPE**|**NAME**|**TARGET**|**PROTOCOL**|**SERVICE**|**PRIORITY**|**WEIGHT**|**PORT**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 Hour  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 Hour  <br/> |
       
    ![NIC-BP-Configure-5-2](../media/a47c45ea-02cc-49f6-89cd-6530f72175fd.png)
      
7. Choose **Save**.
    
    ![NIC-BP-Configure-5-3](../media/0734119a-4c6a-43d2-a3f6-a3ac694e321e.png)
  
8. Add the second new record, using the values from the second row in the table.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 

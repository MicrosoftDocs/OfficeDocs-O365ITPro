---
title: "Create DNS records at TransIP for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_TransIP'
- 'O365M_DOM_TransIP'
- 'O365E_DOM_TransIP'
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
ms.assetid: 9977e873-fab4-4963-88ef-85d690113eb5
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at TransIP for Office 365."
---

# Create DNS records at TransIP for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If TransIP is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. 
  
- [Add a TXT record for verification](#add-a-txt-record-for-verification)
    
- [Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Add the six CNAME records that are required for Office 365](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
After you add these records at TransIP, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domains-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. In the **DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **TTL** and **Type** values from the drop-down lists.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Type** <br/> |**Value** <br/> |
    |@  <br/> |1 Hour  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Choose **Save**.
    
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domains-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. In the **DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **TTL** and **Type** values from the drop-down lists.) 
    
    |**Name**|**TTL**|**Type**|**Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |1 Hour  <br/> |MX  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> **Note:** Get your \<*domain-key* \> from your Office 365 portal account. [How do I find this?](../get-help-with-domains/information-for-dns-records.md) <br>For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![TransIP-BP-Configure-2-1](../media/22cf7c7c-c966-4129-b9e2-1ccd0d25728f.png)
  
4. Choose **Save**.
    
    ![TransIP-BP-Configure-2-2](../media/ebf66131-99a0-4bc0-b198-fc7255c0a3b7.png)
  
5. If there are any other MX records listed, delete each one by choosing the **Delete (X)** icon for that record. 
    
    ![TransIP-BP-Configure-2-3](../media/9d1662f5-1b8e-4b29-898d-dd6174598bc9.png)
  
6. Choose **Save**.
    
    ![TransIP-BP-Configure-2-4](../media/9c94b207-c7ef-4b14-aa9f-1b2868f3a2f3.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domains-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. In the **DNS** section, in the boxes for the new records, type or copy and paste the values from the following table. 
    
    (Select the **TTL** and **Type** values from the drop-down lists.) 
    
    |**Name**|**TTL**|**Type**|**Value**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |1 Hour  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |1 Hour  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |1 Hour  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |msoid  <br/> |1 Hour  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |1 Hour  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |1 Hour  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![TransIP-BP-Configure-3-1](../media/4862ce52-ece9-4033-81f5-a9d7d5eb4720.png)
  
4. Choose **Save**.
    
    ![TransIP-BP-Configure-3-2](../media/016c1290-0cd6-45ce-ba66-5bc165b703ca.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.  
  
1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domains-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. In the **DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **TTL** and **Type** values from the drop-down lists.) 
    
    |**Name**|**TTL**|**Type**|**Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |1 Hour  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![TransIP-BP-Configure-4-1](../media/e4f9c374-dabf-43a6-acd5-2a085d11385c.png)
  
4. Choose **Save**.
    
    ![TransIP-BP-Configure-4-2](../media/7adf0c44-7d2c-4bf2-9e61-f44b2b92daa0.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at TransIP by using [this link](https://www.transip.eu/cp/domains-hosting/). You'll be prompted to sign in first.
    
2. On the **Domains &amp; Hosting** tab, choose the name of the domain that you want to update. 
    
3. In the **DNS** section, in the boxes for the new records, type or copy and paste the values from the following table. 
    
    (Select the **TTL** and **Type** values from the drop-down lists.) 
    
    |**Name**|**TTL**|**Type**|**Value**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|1 Hour|SRV|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br>**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
    |_sipfederationtls._tcp|1 Hour|SRV|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br>**Note:**  We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![TransIP-BP-Configure-5-1](../media/5a748443-05d3-43bd-acca-7364cfba232a.png)
  
4. Choose **Save**.
    
    ![TransIP-BP-Configure-5-2](../media/74fd5d9e-e712-4413-8698-8bf2e5b47949.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

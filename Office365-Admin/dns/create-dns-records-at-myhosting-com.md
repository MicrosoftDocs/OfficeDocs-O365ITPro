---
title: "Create DNS records at myhosting.com for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_myh'
- 'O365M_DOM_myh'
- 'O365E_DOM_myh'
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
ms.assetid: eaf0adf4-bb52-4152-9ab8-0ee26c30fd46
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at myhosting.com for Office 365."
---

# Create DNS records at myhosting.com for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If myhosting.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at myhosting.com, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/). You'll be prompted to login first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
4. Choose the **DNS** tab, and then choose **DNS Records**.
    
5. Choose **Add New DNS Record**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**DNS Record Type** <br/> |**Domain** <br/> |**Data** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Select **Custom** and enter the value **3600**.  <br/> |
   
7. Choose **Finish**.
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/). You'll be prompted to login first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
4. Choose the **DNS** tab, and then choose **DNS Records**.
    
5. Choose **Add New DNS Record**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** and **Preference** values from the drop-down lists.) 
    
    |**DNS Record Type**|**Mail domain**|**Preference**|**Mail exchanger**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(Leave this field empty.)  <br/> |Very high (10)  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/>**Note:** Get your \<*domain-key*\> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![MyHosting-BP-Configure-2-1](../media/e8740f03-5fcb-42b3-9a08-c28210f32b3a.png)
  
7. Choose **Finish**.
    
    ![MyHosting-BP-Configure-2-2](../media/3232a239-2f6a-48f0-9e7f-0ab14a27b433.png)
  
8. If there are any other MX records, delete them by selecting all of them.
    
    ![MyHosting-BP-Configure-2-3-1](../media/f0ed5472-b486-44e8-b394-89e598b5cc3c.png)
  
9. Then choose **Delete**.
    
    ![MyHosting-BP-Configure-2-3-2](../media/208c3aed-b1e3-43ab-9ced-f2ccc655a4b1.png)
  
10. If you deleted any MX records in the preceding step, choose **OK** in the confirmation dialog box. 
    
    ![MyHosting-BP-Configure-2-4](../media/c5e31b69-7073-4289-b640-4e31128ae792.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/). You'll be prompted to login first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
4. Choose the **DNS** tab, and then choose **DNS Records**.
    
5. Choose **Add New DNS Record**.
    
6. Add the first of the CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **DNS Record Type** value from the drop-down list.) 
    
    |**DNS Record Type**|**Domain**|**Canonical name**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |Select **Custom** and enter the value **3600**.  <br/> |
  
   ![MyHosting-BP-Configure-3-1](../media/a602666a-cad1-4d95-adb3-ff160a1d360b.png)
  
7. Choose **Finish**.
    
    ![MyHosting-BP-Configure-3-2](../media/dd71b19d-6ce5-4a71-8406-ec97a8850f21.png)
  
8. To add each of the other five CNAME records, choose **Add New DNS Record** again, create a record using the values from the next row in the table, and then again choose **Finish** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/). You'll be prompted to login first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
4. Choose the **DNS** tab, and then choose **DNS Records**.
    
5. Choose **Add New DNS Record**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **DNS Record Type** value from the drop-down list.) 
        
    |**DNS Record Type**|**Domain**|**Data**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![MyHosting-BP-Configure-4-1](../media/c9587d45-0643-4750-a8e4-112f7f200644.png)
  
7. Choose **Finish**.
    
    ![MyHosting-BP-Configure-4-2](../media/42d78be2-4f49-44f1-aaf6-0921a057b92b.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at MyHosting by using [this link](https://manage.myhosting.com/). You'll be prompted to login first.
    
2. In the **Domains** section, choose **Registered Domains**.
    
3. Under **Registered Domains**, find the name of the domain that you want to edit and then, in that same row, choose **Manage DNS**.
    
4. Choose the **DNS** tab, and then choose **DNS Records**.
    
5. Choose **Add New DNS Record**.
    
6. Add the first of the two SRV records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Choose the **DNS Record Type**, **Protocol**, and **Preference** values from the drop-down lists. The **Protocol** list is the unlabeled drop-down list to the right of the **Service** box. The **Port** field is the unlabeled box to the right of the first **Server Host** field.) 
    
    |**DNS Record Type**|**Service**|**Protocol**|**Preference**|**Weight**|**Server Host**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |Custom (100)  <br/> |1  <br/> |sipdir.online.lync.com.  <br/> |443  <br/> |Select **Custom** and enter the value **3600**.  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |Custom (100)  <br/> |1  <br/> |sipfed.online.lync.com.  <br/> |5061  <br/> |Select **Custom** and enter the value **3600**.  <br/> |
   
    ![MyHosting-BP-Configure-5-1](../media/286f2f3a-c3b9-4b23-98c3-289e367e4085.png)
  
7. Choose **Finish**.
    
    ![MyHosting-BP-Configure-5-2](../media/b3f4c94f-f8e6-4539-8603-204439f93370.png)
  
8. To add the other SRV record, choose **Add New DNS Record** again, create a record using the values from the second row in the table, and then again choose **Finish** to complete the record. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

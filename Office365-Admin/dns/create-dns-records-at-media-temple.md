---
title: "Create DNS records at Media Temple for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5831648d-f334-4cbe-919f-0dc02654eb3b
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Media Temple for Office 365."
---

# Create DNS records at Media Temple for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Media Temple is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-media-temple.md#BKMK_NeedHelp).)
  
- [Lower the TTL value](create-dns-records-at-media-temple.md#BKMK_TTL)
    
- [Add a TXT record for verification](create-dns-records-at-media-temple.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-media-temple.md#BKMK_add_MX)
    
- [Add the four CNAME records that are required for Office 365](create-dns-records-at-media-temple.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-media-temple.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-media-temple.md#BKMK_add_SRV)
    
After you add these records at Media Temple, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Lower the TTL value
<a name="BKMK_TTL"> </a>

By default, Media Temple uses a TTL of 43200 seconds (12 hours). To speed up the Office 365 verification process, we recommend setting the TTL to 3600 (1 hour). Since Media Temple does not support arbitrary TTL values, use the following procedure to lower the TTL during the interval required to verify your Office 365 DNS records. You only need to do this once, at the start of the verification process.
  
1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Additional Zone Actions** section, choose **Lower TTL**.
    
    (You may have to scroll down.)
    
    ![MediaTemple-BP-Configure-1-6](../media/8cbaf91f-f77a-4088-b241-b67685b17c9a.png)
  
6. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-7](../media/4a09010b-4ea4-4170-aa20-69572304d25f.png)
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Zone Records** section, choose **+ Add Row**. 
    
6. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Select the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**Data** <br/> |
|(Leave this field empty.)  <br/> |(This value cannot be changed.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Choose **Save Changes**.
    
8. Choose **OK**.
    
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Zone Records** section, choose **+ Add Row**.
    
6. In the boxes for the new record, type or copy and paste the following values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |(This value cannot be changed.)  <br/> |MX  <br/> | *10 \<domain-key\>*  .mail.protection.outlook.com.  <br/> The  *10*  is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> **This value MUST end with a period (.)** <br/> **Note:** Get your \< *domain-key*  \> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![MediaTemple-BP-Configure-2-1](../media/1fab65a4-1309-432e-aac2-39a94c45ba78.png)
  
7. Choose **Save Changes**.
    
    ![MediaTemple-BP-Configure-2-2](../media/27f31693-6831-4062-b9aa-65913ae59200.png)
  
8. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-8](../media/fa2fe510-ce21-4722-b0a2-f83d277e611e.png)
  
9. If there are any other MX records in the **MX records** section, delete them by selecting the **Delete** icon for each one. 
    
    > [!IMPORTANT]
    > Delete all other MX records except for the one that you created in this procedure. 
  
    ![MediaTemple-BP-Configure-2-3](../media/061b8e0b-bd41-46c9-b2cb-9b9643ed8c59.png)
  
10. Choose **Save Changes**.
    
    ![MediaTemple-BP-Configure-2-4](../media/cc6f6339-ac9e-467c-9c92-a72059202891.png)
  
11. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-8](../media/fa2fe510-ce21-4722-b0a2-f83d277e611e.png)
  
## Add the four CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Zone Records** section, choose **+ Add Row.**
    
6. Add the first of the four CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |(This value cannot be changed.)  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |(This value cannot be changed.)  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |(This value cannot be changed.)  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |msoid  <br/> |(This value cannot be changed.)  <br/> |CNAME  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![MediaTemple-BP-Configure-3-1](../media/55a9fe55-2635-42e7-a9df-49c17981089c.png)
  
7. Choose **Save Changes**.
    
    ![MediaTemple-BP-Configure-3-2](../media/4cd07e11-cd3d-4bdc-9862-9924ddad775f.png)
  
8. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-8](../media/fa2fe510-ce21-4722-b0a2-f83d277e611e.png)
  
9. Add each of the other three CNAME records.
    
    In the **Zone Records** section, choose **+ Add Row**, create a record using the values from the next row in the table, and then again choose **Save Changes** and **OK** to complete that record. 
    
    Repeat this process until you have created all four CNAME records.
       
    >[!IMPORTANT]
    > If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (If you do not have MDM, you can skip this step.) 
  
    |**Name**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |enterpriseregistration  <br/> |(This value cannot be changed.)  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |(This value cannot be changed.)  <br/> |CNAME  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> **This value MUST end with a period (.)** <br/> |
   
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Zone Records** section, choose **+ Add Row**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |(This value cannot be changed.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![MediaTemple-BP-Configure-4-1](../media/09dfea1c-319f-456c-9894-ac13a1f9486f.png)
  
7. Choose **Save Changes**.
    
    ![MediaTemple-BP-Configure-4-2](../media/2f8c3dba-bb6c-4c11-8664-8beb4b6a5c1e.png)
  
8. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-8](../media/fa2fe510-ce21-4722-b0a2-f83d277e611e.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Media Temple by using [this link](https://ac.mediatemple.net/login.mt?redirect=home.mt). You'll be prompted to log in first.
    
2. On the **SERVICES** page, choose **List All Domains**.
    
3. On the **Domains** page, find the name of the domain that you are updating, and then choose the name of the domain that you want to edit. 
    
4. On the **Control Panel** page for your domain, in the **DNS &amp; Zone Files** section, choose **Edit DNS Zone File**.
    
5. On the **Edit Zone** page, in the **Zone Records** section, choose **+ Add Row**.
    
6. Add the first of the two SRV records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
    (Select the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |(This value cannot be changed.)  <br/> |SRV  <br/> |100 1 443 sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |_sipfederationtls._tcp  <br/> |(This value cannot be changed.)  <br/> |SRV  <br/> |100 1 5061 sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![MediaTemple-BP-Configure-5-1](../media/46099213-80e5-4aa9-b337-35f4c3b5d63c.png)
  
7. Choose **Save Changes**.
    
    ![MediaTemple-BP-Configure-5-2](../media/7dd9b3c7-d24b-4594-93cf-36fd871d0bb4.png)
  
8. Choose **OK**.
    
    ![MediaTemple-BP-Configure-1-8](../media/fa2fe510-ce21-4722-b0a2-f83d277e611e.png)
  
9. Add the other SRV record.
    
    In the **Zone Records** section, choose **+Add Row**, create a record using the values from the next row in the table, and then again choose **Save Changes** and **OK** to complete the second record. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
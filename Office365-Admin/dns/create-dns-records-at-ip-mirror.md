---
title: "Create DNS records at IP Mirror for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_IPMirror'
- 'O365M_DOM_IPMirror'
- 'O365E_DOM_IPMirror'
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
ms.assetid: db71eff0-6e69-41d3-a256-75ff27b0d8c3
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at IP Mirror for Office 365."
---

# Create DNS records at IP Mirror for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If IP Mirror is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
> [!IMPORTANT]
> Some IP Mirror accounts are restricted to a limit of 10 DNS records. To ensure that your account is not affected by that limit, we recommend deleting this record once your domain is verified. 
  
1. To get started, go to your domains page at IP Mirror by using [this link](https://portal.speednames.asia/portal/). You'll be prompted to log in first.
    
2. In the **Manage Domain** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
5. On the **Domain Properties** page, choose **Edit DNS Record**.
    
6. On the **Edit DNS Record** page, at the top of the **Domain** section, check the value in the **TTL** box. 
    
    If the **TTL** value is not already set to **300**, then set it to **300** now. (This value is set only once, and it is applied to all of your DNS records for IP Mirror.) 
    
7. Still on the **Edit DNS Record** page, in the **TXT Records** section, choose the **Host +** icon. 
    
    (You may have to scroll down.) 
    
8. In the **TXT Records** section, in the boxes for the new record, type or copy and paste the following values. 
    
    |||
    |:-----|:-----|
    |**Host** <br/> |**Description** <br/> |
    |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)   <br/>       |
   
9. Choose **Save**.
    
    (You may have to scroll down.) 
    
10. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the Microsoft 365 admin center, choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
3. On the **Setup** page, choose **Start setup**.
    
4. On the **Verify domain** page, choose **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365

1. To get started, go to your domains page at IP Mirror by using [this link](https://portal.speednames.asia/portal/). You'll be prompted to log in first.
    
2. In the **Manage Domain** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the ** Domain Name ** section, choose the name of the domain that you are updating. 
    
5. On the **Domain Properties** page, choose **Edit DNS Record**.
    
6. On the **Edit DNS Record** page, at the top of the **Domain** section, check the value in the **TTL** box. 
    
    If the **TTL** value is not already set to **300**, then set it to **300** now. (This value is set only once, and it is applied to all of your DNS records for IP Mirror.) 
    
    ![ipMirror-BP-Configure-1-6](../media/f89fc84b-29e0-4d8a-b6bf-75dd1e1a9578.png)
  
7. Still on the **Edit DNS Record** page, in the **MX Records** section, choose the **Host +** icon. 
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-2-1](../media/95e9fc7c-204d-412b-94f2-e00228360ead.png)
  
8. In the boxes for the new record, type or copy and paste the following values.
    
    |**Host**|**Priority**|**Mail server**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |1  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your *\<domain-key\>* from your Office 365 portal account. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)    <br/>      |
   
    ![ipMirror-BP-Configure-2-2](../media/91b8c48f-4486-425d-a994-afdb251ebdb3.png)
  
9. Choose **Save**.
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-2-3](../media/e02c9201-ab32-4e81-a5b8-227c1b9c18f9.png)
  
10. If there are any other MX records in the **MX Records** section, delete one of them by choosing the **Delete (trash can)** icon for that record. 
    
    ![ipMirror-BP-Configure-2-4](../media/c4d2c234-759f-40d2-a215-33ae0042ed67.png)
  
11. In the confirmation dialog box, choose **OK** to confirm the deletion. 
    
    ![ipMirror-BP-Configure-2-5](../media/e92c8f5a-cf2e-465f-afa6-3a0e06625ccf.png)
  
12. Use the same process (choose the **Delete (trash can)** icon, and then choose **OK** to confirm) to remove any other MX records in the list, leaving only the one that you created earlier in this procedure. 
    
13. Choose **Save**.
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-2-3](../media/e02c9201-ab32-4e81-a5b8-227c1b9c18f9.png)
  
## Add the six CNAME records that are required for Office 365

1. To get started, go to your domains page at IP Mirror by using [this link](https://portal.speednames.asia/portal/). You'll be prompted to log in first.
    
2. In the ** Manage Domain ** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the ** Domain Name ** section, choose the name of the domain that you are updating. 
    
5. On the ** Domain Properties ** page, choose **Edit DNS Record**.
    
6. On the **Edit DNS Record** page, at the top of the **Domain** section, check the value in the **TTL** box. 
    
    If the **TTL** value is not already set to **300**, then set it to **300** now. (This value is set only once, and it is applied to all of your DNS records for IP Mirror.) 
    
    ![ipMirror-BP-Configure-1-6](../media/f89fc84b-29e0-4d8a-b6bf-75dd1e1a9578.png)
  
7. Still on the **Edit DNS Record** page, in the **CNAME Records** section, choose the **Alias Name +** icon six times to create six empty rows. 
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-3-1](../media/61494fe5-401a-4afd-a764-b445745f58ef.png)
  
8. In the boxes for the new records, type or copy and paste the following values.
    
    |**Alias Name**|**Is an alias for**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![ipMirror-BP-Configure-3-2](../media/c442b576-4a1d-4f15-bcc1-fe7ff589e67f.png)
  
9. Choose **Save**.
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-3-3](../media/db10f2d6-7594-456e-93a0-e6f80b122f3a.png)
  
## Add a TXT record for SPF to help prevent email spam

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at IP Mirror by using [this link](https://portal.speednames.asia/portal/). You'll be prompted to log in first.
    
2. In the ** Manage Domain ** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the ** Domain Name ** section, choose the name of the domain that you are updating. 
    
5. On the ** Domain Properties ** page, choose **Edit DNS Record**.
    
6. On the **Edit DNS Record** page, at the top of the **Domain** section, check the value in the **TTL** box. 
    
    If the **TTL** value is not already set to **300**, then set it to **300** now. (This value is set only once, and it is applied to all of your DNS records for IP Mirror.) 
    
    ![ipMirror-BP-Configure-1-6](../media/f89fc84b-29e0-4d8a-b6bf-75dd1e1a9578.png)
  
7. Still on the **Edit DNS Record** page, in the **TXT Records** section, choose the **Host +** icon. 
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-4-1](../media/b45338b9-8751-4a3b-ab22-6952f894fc86.png)
  
8. In the box for the new record, type or copy and paste the following values.
    
    |**Host**|**Description**|
    |:-----|:-----|
    |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:**> We recommend copying and pasting this entry, so that all of the spacing stays correct.   <br/>        |
       
    ![ipMirror-BP-Configure-4-2](../media/4bdba745-ebe0-4ab7-9214-8a8eecf6281a.png)
  
9. Choose **Save**.
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-4-3](../media/d35c4c69-b14c-4072-b6a6-fd2fbb7c3453.png)
  
## Add the two SRV records that are required for Office 365

1. To get started, go to your domains page at IP Mirror by using [this link](https://portal.speednames.asia/portal/). You'll be prompted to log in first.
    
2. In the **Manage Domain** column, choose **My Domains**.
    
3. On the **My Domains** page, choose **View All**.
    
4. On the **My Domains** page, in the ** Domain Name ** section, choose the name of the domain that you are updating. 
    
5. On the ** Domain Properties ** page, choose **Edit DNS Record**.
    
6. On the **Edit DNS Record** page, at the top of the **Domain** section, check the value in the **TTL** box. 
    
    If the **TTL** value is not already set to **300**, then set it to **300** now. (This value is set only once, and it is applied to all of your DNS records for IP Mirror.) 
    
    ![ipMirror-BP-Configure-1-6](../media/f89fc84b-29e0-4d8a-b6bf-75dd1e1a9578.png)
  
7. Still on the **Edit DNS Record** page, in the **SRV Records** section, choose the **Host +** icon two times, to create two empty rows. 
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-5-1](../media/b63b002b-4a0d-4bac-bf6a-a7a6d9c890f8.png)
  
8. In the boxes for the new records, type or copy and paste the following values.
    
    |**Host**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![ipMirror-BP-Configure-5-2](../media/2c7efc4f-375d-4cf8-a834-fae5cf50e916.png)
  
9. Choose **Save**.
    
    (You may have to scroll down.)
    
    ![ipMirror-BP-Configure-5-3](../media/f6c3ea01-0b92-4afe-829c-408cb651fdb7.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 

---
title: "Create DNS records at Fasthosts.co.uk for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Fast'
- 'O365M_DOM_Fast'
- 'O365E_DOM_Fast'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7fc2d2a9-418f-45b7-9c70-6218e388a3f2
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Fasthosts.co.uk for Office 365."
---

# Create DNS records at Fasthosts.co.uk for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Fasthosts.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-fasthosts-co-uk.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-fasthosts-co-uk.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-fasthosts-co-uk.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-fasthosts-co-uk.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-fasthosts-co-uk.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-fasthosts-co-uk.md#BKMK_add_SRV)
    
After you add these records at Fasthosts.co.uk, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/DomainNames/). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then choose the **DNS** icon for that domain name. 
    
4. On the **Advanced DNS** page for your domain, in the **TXT Records** section, choose **Add TXT Record**.
    
    (You may have to scroll down.)
    
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|||
|:-----|:-----|
|**Host Name** <br/> |**Value** <br/> |
|@  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Choose **Save**.
    
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

1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/DomainNames/). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then choose the **DNS** icon for that domain name. 
    
4. On the **Advanced DNS** page for your domain, in the **MX Records** section, choose **Add MX Record**.
    
    (You may have to scroll down.)
    
    ![FasthostsUK-BP-Configure-2-1](../media/1e4ec5ff-5d07-4a8f-af27-a6bff83d4e39.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Host Name**|**Points To**|**Priority**|
|:-----|:-----|:-----|
|@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your \< *domain-key*  \> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![FasthostsUK-BP-Configure-2-2](../media/47930740-2660-426b-832f-6847fb5a33b5.png)
  
6. Choose **Save**.
    
    ![FasthostsUK-BP-Configure-2-3](../media/aa2dfb7f-22ec-4c8a-8f41-1a7a028d76e0.png)
  
7. If there are any other MX records in the **MX Records** section, delete one of them by choosing **Remove** for that one. 
    
    ![FasthostsUK-BP-Configure-2-4](../media/d74abd4c-ed1a-4875-977f-ba16706570ad.png)
  
8. Select the confirmation check box.
    
    ![FasthostsUK-BP-Configure-2-5](../media/5a14902a-346d-4cbc-9001-883cba0df0dc.png)
  
9. Choose **Confirm**.
    
    ![FasthostsUK-BP-Configure-2-6](../media/57b5adb9-8cf4-4605-80e4-2ceb95159ffb.png)
  
10. Use the same process to delete all other MX records except for the one that you created in this procedure.
    
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/DomainNames/). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then choose the **DNS** icon for that domain name. 
    
4. On the **Advanced DNS** page for your domain, in the **CNAME Records** section, choose **Add CNAME Record**.
    
    (You may have to scroll down.)
    
    ![FasthostsUK-BP-Configure-3-1](../media/781581b6-79bb-4acc-a97e-ba625e02d4b5.png)
  
5. Add the first of the six CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
|**Host Name**|**Points To**|
|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
|msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![FasthostsUK-BP-Configure-3-2](../media/995d90ae-298e-43e9-ba50-240cf17e946b.png)
  
6. Choose **Save**.
    
    ![FasthostsUK-BP-Configure-3-3](../media/ba1fa6d6-f003-45c4-9e51-a22893862c2c.png)
  
7. Add each of the other five CNAME records.
    
    On the **Advanced DNS** page, choose **Add CNAME Record**, create a record using the values from the next row in the table, and then again choose **Save** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/DomainNames/). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then choose the **DNS** icon for that domain name. 
    
4. On the **Advanced DNS** page for your domain, in the **TXT Records** section, choose **Add TXT Record**.
    
    (You may have to scroll down.)
    
    ![FasthostsUK-BP-Configure-4-1](../media/2218c30b-1524-48fb-801b-8ad841577232.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Host Name**|**Value**|
|:-----|:-----|
|@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![FasthostsUK-BP-Configure-4-2](../media/50531996-80b7-48c1-b2f0-a654f0e6e203.png)
  
6. Choose **Save**.
    
    ![FasthostsUK-BP-Configure-4-3](../media/ac3f444d-79cd-4444-a1a0-377d6d9fa83d.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Fasthosts.co.uk by using [this link](https://admin.fasthosts.co.uk/DomainNames/). You'll be prompted to log in first.
    
2. On the top navigation bar, choose **Domain**, and then choose **Manage Domains**.
    
3. On the **Configure Domain Names** page, find the name of the domain that you are updating, and then choose the **DNS** icon for that domain name. 
    
4. On the **Advanced DNS** page for your domain, in the **SRV Records** section, choose **Add SRV Record**.
    
    (You may have to scroll down.)
    
    ![FasthostsUK-BP-Configure-5-1](../media/cb5721e8-1128-42fa-b4ed-a474c08646f6.png)
  
5. Add the first of the two SRV records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
|**Host Name**|**Priority**|**Weight**|**Port**|**Target**|
|:-----|:-----|:-----|:-----|:-----|
|_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
|_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![FasthostsUK-BP-Configure-5-2](../media/dab4b5f6-93b4-4ada-81f8-223bec86fc06.png)
  
6. Choose **Save**.
    
    ![FasthostsUK-BP-Configure-5-3](../media/0af1d298-8925-468f-9d49-8d534135c3e2.png)
  
7. Add the other SRV record.
    
    On the **Advanced DNS** page, in the **SRV Records** section, choose **Add SRV Record**, create a record using the values from the other row in the table, and then again choose **Save** to complete the second record. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 


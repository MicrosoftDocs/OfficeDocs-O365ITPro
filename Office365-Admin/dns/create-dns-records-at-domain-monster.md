---
title: "Create DNS records at Domain Monster for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 31cabbae-0bab-45b5-9995-8645b2d284c3

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Domain Monster for Office 365."
---

# Create DNS records at Domain Monster for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Domain Monster is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. Follow the steps below. (Need more help? [Still need help?](create-dns-records-at-domain-monster.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-domain-monster.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-domain-monster.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-domain-monster.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-domain-monster.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-domain-monster.md#BKMK_add_SRV)
    
After you add these records at Domain Monster, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Manage DNS**.
    
    ![DomainMonster-BP-Configure-1-3](../media/1b9ed73e-1930-4075-a214-000ba0a5d18a.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record type** from the drop-down lists.) 
    
|**Record type**|**Hostname**|**Comment**|
|:-----|:-----|:-----|
|TXT  <br/> |(Leave this field blank.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DomainMonster-BP-Verify-1-1](../media/32e7e4ef-f51b-44ed-b5ad-a1508a95e82b.png)
  
5. Choose **Add record**.
    
    ![DomainMonster-BP-Verify-1-2](../media/c959f008-0644-43f2-b50a-5cbdac289392.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Manage DNS**.
    
    ![DomainMonster-BP-Configure-1-3](../media/1b9ed73e-1930-4075-a214-000ba0a5d18a.png)
  
4. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record type** and **Preference** values from the drop-down lists.) 
    
|**Record type**|**Hostname**|**Address**|**Preference**|
|:-----|:-----|:-----|:-----|
|MX  <br/> |(Leave this field blank.)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |1  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![DomainMonster-BP-Configure-2-1](../media/68edbd1b-9818-4886-893f-f784b4e29ef8.png)
  
5. Choose **Add Record**.
    
    ![DomainMonster-BP-Configure-2-2](../media/2501e987-4659-436b-984c-3a3ca92b1f15.png)
  
6. If there are any other MX records, delete them by selecting the checkbox in the **Delete** (Trash icon) column. 
    
    ![DomainMonster-BP-Configure-2-3](../media/2387e050-3237-4043-8817-792a2b4c6e50.png)
  
7. Choose **Save DNS Updates**.
    
    ![DomainMonster-BP-Configure-2-4](../media/075f3405-b3b2-4e1f-8af4-5142a1704498.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Manage DNS**.
    
    ![DomainMonster-BP-Configure-1-3](../media/1b9ed73e-1930-4075-a214-000ba0a5d18a.png)
  
4. Add the first of the CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the ** Record type ** from the drop-down list.) 
    
|**Record type**|**Alias**|**Address**|
|:-----|:-----|:-----|
|CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
|CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |
|CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
|CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
|CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> |
   
    ![DomainMonster-BP-Configure-3-1](../media/bc8668f5-c29a-4486-91fa-abefed7a0181.png)
  
5. Choose **Add Record**.
    
    ![DomainMonster-BP-Configure-3-2](../media/6e4eaf95-49fe-4f8e-a4ad-44cf9d4a098d.png)
  
6. To add each of the other five CNAME records, create a record using the values from the next row in the table, and then again choose **Add Record** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Manage DNS**.
    
    ![DomainMonster-BP-Configure-1-3](../media/1b9ed73e-1930-4075-a214-000ba0a5d18a.png)
  
4. In the boxes for the new record, type or copy and paste the value from the following table.
    
    (Select the **Record type** from the drop-down list.) 
    
|**Record type**|**Hostname**|**Comment**|
|:-----|:-----|:-----|
|TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![DomainMonster-BP-Configure-4-1](../media/d14fa725-e501-436f-8dfb-376e91de3490.png)
  
5. Choose **Add Record**.
    
    ![DomainMonster-BP-Configure-4-2](../media/1130e681-c0b6-4edf-b708-c2bd6c6318e0.png)
  
    > [!NOTE]
    > Domain Monster creates a default TXT/SPF record for each account. Depending on your email configuration, you should either delete this record, or add its TXT/SPF values to the Office 365 TXT/SPF record. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). To validate your SPF record, you can use one of these [SPF validation tools](https://support.office.com/article/92a43f6a-4651-455a-a1cc-300684bedcfa.aspx). 
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Domain Monster by using [this link](https://www.domainmonster.com/login/). You'll be prompted to login first.
    
    ![DomainMonster-BP-Configure-1-1](../media/2063248b-88fc-426a-9e00-fa1d3eabd6eb.png)
  
2. In the **Manage Domains** section, select the domain you want to update and then choose **Manage**.
    
    ![DomainMonster-BP-Configure-1-2](../media/d935caaa-273a-4e94-a463-42c3136ba785.png)
  
3. On the **Domain Control Panel** page, choose **Manage DNS**.
    
    ![DomainMonster-BP-Configure-1-3](../media/1b9ed73e-1930-4075-a214-000ba0a5d18a.png)
  
4. Add the first of the two SRV records.
    
    In the boxes for the new records, type or copy and paste the values from the following table.
    
    (Choose the **Record Type**, **Service/Protocol**, **Preference** and **Weight** values from the drop-down lists.) 
    
|**Record type**|**Service/Protocol**|**Address**|**Preference**|**Weight**|**Port**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|SRV  <br/> |_sip._tls  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |
|SRV  <br/> |_sipfederationtls._tcp  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |
   
    ![DomainMonster-BP-Configure-5-1](../media/f32f07ec-d741-4cfe-a73d-ea77e0eced90.png)
  
5. Choose **Add Record**.
    
    ![DomainMonster-BP-Configure-5-2](../media/573ce381-692d-4376-bb76-b3af5261cb3b.png)
  
6. To add the other SRV record, create a record using the values from the second row in the table, and then again choose **Add Record** to complete the record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

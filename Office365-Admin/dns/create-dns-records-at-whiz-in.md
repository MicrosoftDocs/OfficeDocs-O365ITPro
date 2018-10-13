---
title: "Create DNS records at Whiz.in for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Whiz'
- 'O365M_DOM_Whiz'
- 'O365E_DOM_Whiz'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6821d391-dc72-4e3b-a143-8f8c1871864c
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Whiz.in for Office 365."
---

# Create DNS records at Whiz.in for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Whiz.in is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-whiz-in.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-whiz-in.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-whiz-in.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-whiz-in.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-whiz-in.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-whiz-in.md#BKMK_add_SRV)
    
After you add these records at Whiz.in, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. In the **Manage Orders** drop down, choose **List/Search Orders**.
    
    ![WhizIn-BP-Configure-1-2](../media/9c9202b1-2463-40a1-ad0f-5e7800e70d6b.png)
  
3. On the **List of Orders** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Configure-1-3](../media/3c241f4f-2ce1-4286-90a2-959a40761b7e.png)
  
4. In the **DNS Management** section, choose **Manage DNS**.
    
    (You may need to scroll down.)
    
    ![WhizIn-BP-Configure-1-4](../media/f94b8ccc-e677-4825-b432-fc26781e1596.png)
  
5. In the **Manage Records for** ** *domain_name* ** section, choose the **TXT Records** tab. 
    
    ![WhizIn-BP-Verify-1-1-1](../media/541c2f15-cebf-472b-80c6-a4312fb65f10.png)
  
6. In the **List of TXT Records** area, choose **Add TXT Record**.
    
    ![WhizIn-BP-Verify-1-1-2](../media/1cdd1e12-da95-421c-ab9a-29ad317cbeae.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|
|@  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |7200  <br/> |
   
    ![WhizIn-BP-Verify-1-2](../media/8310a995-a796-4ee4-bbe0-1cee5571ff6d.png)
  
8. Choose **Add Record**.
    
    ![WhizIn-BP-Verify-1-3](../media/e0bb42b9-733e-4a51-8aec-a2a7c89f855b.png)
  
9. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Office 365 Admin Center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. In the **Manage Orders** drop down, choose **List/Search Orders**.
    
    ![WhizIn-BP-Configure-1-2](../media/9c9202b1-2463-40a1-ad0f-5e7800e70d6b.png)
  
3. On the **List of Orders** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Configure-1-3](../media/3c241f4f-2ce1-4286-90a2-959a40761b7e.png)
  
4. In the **DNS Management** section, choose **Manage DNS**.
    
    (You may need to scroll down.)
    
    ![WhizIn-BP-Configure-1-4](../media/f94b8ccc-e677-4825-b432-fc26781e1596.png)
  
5. In the **Manage Records for** ** *domain_name* ** section, choose the **MX Records** tab. 
    
    ![WhizIn-BP-Configure-2-1-1](../media/e1ed3c2e-9b41-44d3-8cf0-38c14a0d22f2.png)
  
6. In the **List of MX Records** area, choose **Add MX Record**.
    
    ![WhizIn-BP-Configure-2-1-2](../media/b88011eb-b55b-4e2e-9e1b-85924447a8f0.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Zone**|**Value**|**TTL**|**MX Priority**|
|:-----|:-----|:-----|:-----|
|@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |7200  <br/> |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![WhizIn-BP-Configure-2-2](../media/06a3ed03-6b3e-4171-b17c-dda6fa4783cc.png)
  
8. Choose **Add Record**.
    
    ![WhizIn-BP-Configure-2-3](../media/66caf9ab-2e4a-43ad-ae74-58d1b7d1d058.png)
  
9. If there are any other MX records listed in the **List of MX Records** area, delete each of them. 
    
    Find the first record to be deleted and, in the **Name** field, choose the ** *domain_name.* **
    
    ![WhizIn-BP-Configure-2-4](../media/76caf95a-a217-4fa9-bb9c-43396b5ed3e7.png)
  
10. In the ** *domain_name* ** ** MX Record Details ** area, choose **Delete Record**.
    
    ![WhizIn-BP-Configure-2-5](../media/cd594eae-5c38-45fd-a956-224b022fa3cc.png)
  
11. On the confirmation dialog box, choose **OK**.
    
    ![WhizIn-BP-Configure-2-6](../media/fd556a12-ffb6-46e8-8412-6c35754bf986.png)
  
12. Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.
    
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. In the **Manage Orders** drop down, choose **List/Search Orders**.
    
    ![WhizIn-BP-Configure-1-2](../media/9c9202b1-2463-40a1-ad0f-5e7800e70d6b.png)
  
3. On the **List of Orders** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Configure-1-3](../media/3c241f4f-2ce1-4286-90a2-959a40761b7e.png)
  
4. In the **DNS Management** section, choose **Manage DNS**.
    
    (You may need to scroll down.)
    
    ![WhizIn-BP-Configure-1-4](../media/f94b8ccc-e677-4825-b432-fc26781e1596.png)
  
5. In the **Manage Records for** ** *domain_name* ** section, choose the **CNAME Records** tab. 
    
    ![WhizIn-BP-Configure-3-1-1](../media/403a2397-8360-4362-b628-a893aba0cb85.png)
  
6. In the **List of CNAME Records** area, choose **Add CNAME Record**.
    
    ![WhizIn-BP-Configure-3-1-2](../media/64691d43-37fa-470c-9aa2-8f382a7d39ae.png)
  
7. Add the first of the six CNAME records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
|**Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|
|autodiscover|autodiscover.outlook.com> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
|sip|sipdir.online.lync.com> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
|lyncdiscover|webdir.online.lync.com> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
|msoid|clientconfig.microsoftonline-p.net> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
|enterpriseregistration|enterpriseregistration.windows.net> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
|enterpriseenrollment|enterpriseenrollment.manage.microsoft.com> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
   
    ![WhizIn-BP-Configure-3-2](../media/4eeae047-d2f9-49c5-87e2-050df7b3d2d7.png)
  
8. Choose **Add Record**.
    
    ![WhizIn-BP-Configure-3-3](../media/c7f82782-b362-4abe-b888-52b1c7430260.png)
  
9. Add each of the other five CNAME records.
    
    In the **List of CNAME Records** area, choose **Add CNAME Record** again, create a record using the values from the next row in the table, and then again choose **Add Record** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. In the **Manage Orders** drop down, choose **List/Search Orders**.
    
    ![WhizIn-BP-Configure-1-2](../media/9c9202b1-2463-40a1-ad0f-5e7800e70d6b.png)
  
3. On the **List of Orders** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Configure-1-3](../media/3c241f4f-2ce1-4286-90a2-959a40761b7e.png)
  
4. In the **DNS Management** section, choose **Manage DNS**.
    
    (You may need to scroll down.)
    
    ![WhizIn-BP-Configure-1-4](../media/f94b8ccc-e677-4825-b432-fc26781e1596.png)
  
5. In the **Manage Records for** ** *domain_name* ** section, choose the **TXT Records** tab. 
    
    ![WhizIn-BP-Configure-4-1-1](../media/e5076053-e072-43c4-9c81-4745b3f796d6.png)
  
6. In the **List of TXT Records** area, choose **Add TXT Record**.
    
    ![WhizIn-BP-Configure-4-1-2](../media/833a08c1-5432-4d12-affb-f0c573b70730.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Host Name**|**Value**|**TTL**|
|:-----|:-----|:-----|
|@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |7200  <br/> |
   
    ![WhizIn-BP-Configure-4-2](../media/f59dd9f8-0d1b-4e4f-af01-ae97a1f70d27.png)
  
8. Choose **Add Record**.
    
    ![WhizIn-BP-Configure-4-3](../media/17f9dc35-1b7c-469c-ae45-66b08747e658.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Whiz.in by using [this link](http://domain.whiz.in/). You'll be prompted to login first.
    
    > [!IMPORTANT]
    > Before you login, choose **Customer** (not **Reseller**) in the drop-down list. 
  
    ![WhizIn-BP-Configure-1-1](../media/23f281b0-69ff-483b-908b-beb6b9d7ee65.png)
  
2. In the **Manage Orders** drop down, choose **List/Search Orders**.
    
    ![WhizIn-BP-Configure-1-2](../media/9c9202b1-2463-40a1-ad0f-5e7800e70d6b.png)
  
3. On the **List of Orders** page, in the **Domain Name** section, choose the name of the domain that you are updating. 
    
    ![WhizIn-BP-Configure-1-3](../media/3c241f4f-2ce1-4286-90a2-959a40761b7e.png)
  
4. In the **DNS Management** section, choose **Manage DNS**.
    
    (You may need to scroll down.)
    
    ![WhizIn-BP-Configure-1-4](../media/f94b8ccc-e677-4825-b432-fc26781e1596.png)
  
5. In the **Manage Records for** ** *domain_name* ** section, choose the **SRV Records** tab. 
    
    ![WhizIn-BP-Configure-5-1-1](../media/28d30c89-29c2-4c74-879d-356ca7d9aed9.png)
  
6. In the **List of SRV Records** area, choose **Add SRV Record**.
    
    ![WhizIn-BP-Configure-5-1-2](../media/21b4671f-af5a-4592-be9d-1d5547eb0af1.png)
  
7. Add the first of the two SRV records.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
|**Service Record Name**|**Priority**|**Weight**|**Port**|**Target**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|_sip_tls. *domain* (Where  *domain*  is your  *domain_name*  .) |100|1|443|sipdir.online.lync.com> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
|_sipfederationtls_tcp. *domain* (Where  *domain*  is your  *domain_name*  .) |100|1|5061|sipfed.online.lync.com> [!IMPORTANT]> Select the **Fully Qualified Domain Name** option and enter the value in this field.           |7200|
   
    ![WhizIn-BP-Configure-5-2](../media/138c0cf8-9f09-4180-b871-b392888ce831.png)
  
8. Choose **Add Record**.
    
    ![WhizIn-BP-Configure-5-3](../media/46ec9a4b-d7c0-4b70-bd6b-70933a2b9c44.png)
  
9. Add the other SRV record.
    
    In the **List of SRV Records** area, choose **Add SRV Record** again, create a record using the values from the other row in the table, and then again choose **Add Record**.
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

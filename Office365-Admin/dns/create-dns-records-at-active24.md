---
title: "Create DNS records at Active24 for Office 365"
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
ms.assetid: 58ccfe22-96b8-4b6e-ac29-50fcc233f9c4
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Active24 for Office 365."
---

# Create DNS records at Active24 for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Active24 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-active24.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-active24.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-active24.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-active24.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-active24.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-active24.md#BKMK_add_SRV)
    
After you add these records at Active24, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:  *domain_name* **, choose **DNS administration**.
    
    ![Active24-BP-Configure-1-3](../media/0220173b-f73d-4659-a7d1-6f607afbb6d8.png)
  
4. On the **Customer center** page, in the **Add record** section, choose **TXT**.
    
    ![Active24-BP-Verify-1-1](../media/1e2afb98-af1d-494d-aad8-42ea3c29a675.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Name**|**TTL**|**Text**|
|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Active24-BP-Verify-1-2](../media/ce5bc8bf-2809-4fe4-bcb8-2a281247ce35.png)
  
6. Choose **Create**.
    
    ![Active24-BP-Verify-1-3](../media/1f9c5de8-6360-435a-9d74-5045b0041660.png)
  
7. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:  *domain_name* **, choose **DNS administration**.
    
    ![Active24-BP-Configure-1-3](../media/0220173b-f73d-4659-a7d1-6f607afbb6d8.png)
  
4. On the **Customer center** page, in the **Add record** section, choose **MX**.
    
    ![Active24-BP-Configure-2-1](../media/1ae5378b-f342-4759-a9af-4822577cb6fb.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Name**|**TTL**|**Priority**|**MailServer**|
|:-----|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |3600  <br/> |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![Active24-BP-Configure-2-2](../media/646f782f-46a9-4220-abe3-33492680260a.png)
  
6. Choose **Create**.
    
    ![Active24-BP-Configure-2-3](../media/e665df12-9212-4301-886e-918e89475c23.png)
  
7. If there are any other MX records, delete them by choosing the **Delete** (trash can) control. 
    
    ![Active24-BP-Configure-2-4](../media/bfc35e32-b822-474c-a745-0da3c5b26481.png)
  
8. If you deleted any MX records in the preceding step, choose **Delete record** on the confirmation page. 
    
    ![Active24-BP-Configure-2-5](../media/406e6835-2720-4021-89d7-0313b52512c3.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:  *domain_name* **, choose **DNS administration**.
    
    ![Active24-BP-Configure-1-3](../media/0220173b-f73d-4659-a7d1-6f607afbb6d8.png)
  
4. On the **Customer center** page, in the **Add record** section, choose **CNAME**.
    
    ![Active24-BP-Configure-3-1](../media/647dc9d9-9f74-4864-91a2-ef6a33c64abc.png)
  
5. Add the first of the six CNAME records.
    
    In the boxes for the new records, type or copy and paste the values from the first row of the following table.
    
|**Name**|**TTL**|**Alias to**|
|:-----|:-----|:-----|
|autodiscover  <br/> |3600  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
|sip  <br/> |3600  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|lyncdiscover  <br/> |3600  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|msoid  <br/> |3600  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseregistration  <br/> |3600  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseenrollment  <br/> |3600  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
   ![Active24-BP-Configure-3-2](../media/51f796b3-67ed-4eba-a32f-cd283aa6ccba.png)
  
6. Choose **Create**.
    
    ![Active24-BP-Configure-3-3](../media/6bf0839f-d2c1-465d-81a0-f8184426ed5e.png)
  
7. To add each of the other five CNAME records, choose **CNAME** again, create a record using the values from the next row in the table, and then again choose **Create** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:  *domain_name* **, choose **DNS administration**.
    
    ![Active24-BP-Configure-1-3](../media/0220173b-f73d-4659-a7d1-6f607afbb6d8.png)
  
4. On the **Customer center** page, in the **Add record** section, choose **TXT**.
    
    ![Active24-BP-Configure-4-1](../media/08de3407-6d0d-49ed-9849-cbf9d5e6b7d6.png)
  
5. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Name**|**TTL**|**Text**|
|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![Active24-BP-Configure-4-2](../media/da9378c2-56a0-42a8-bea0-179bfa6cb414.png)
  
6. Choose **Create**.
    
    ![Active24-BP-Configure-4-3](../media/b5f91dcc-ce6c-4262-a530-17e4b291cdf6.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Active24 by using [this link](https://customer.active24.com/login.jsp). You'll be prompted to Log In first.
    
    ![Active24-BP-Configure-1-1](../media/33a223fd-57af-415c-9c5d-df18b1dee13d.png)
  
2. On the **Customer center** page, in the **Domain overview** section, choose the name of the domain that you want to edit. 
    
    ![Active24-BP-Configure-1-2](../media/487b9930-6a61-46b5-824b-1f87026210ce.png)
  
3. Under **Domain details:  *domain_name* **, choose **DNS administration**.
    
    ![Active24-BP-Configure-1-3](../media/0220173b-f73d-4659-a7d1-6f607afbb6d8.png)
  
4. On the **Customer center** page, in the **Add record** section, choose **SRV**.
    
    ![Active24-BP-Configure-5-1](../media/21b92466-3314-455c-b5f4-6c4575043f38.png)
  
5. Add the first of the two SRV records.
    
    In the boxes for the new records, type or copy and paste the values from the first row of the following table.
    
|**Name**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|_sip._tls  <br/> |3600  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|_sipfederationtls._tcp  <br/> |3600  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Active24-BP-Configure-5-2](../media/47f6b0d8-c39f-4028-8339-038a7f20a5a3.png)
  
6. Choose **Create**.
    
    ![Active24-BP-Configure-5-3](../media/6e6622eb-0452-47e3-a316-263f904061a2.png)
  
7. To add the other SRV record, choose **SRV** again, create a record using the values from the second row in the table, and then again choose **Create** to complete the record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

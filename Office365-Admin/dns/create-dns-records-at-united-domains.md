---
title: "Create DNS records at United Domains for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_UD'
- 'O365M_DOM_UD'
- 'O365E_DOM_UD'
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
ms.assetid: 91c3a2c3-6700-453a-9dd6-cc2f56700a06
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at United Domains for Office 365."
---

# Create DNS records at United Domains for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If United Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add.
  
- [Add a TXT record for verification](#add-a-txt-record-for-verification)
    
- [Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Add the six CNAME records that are required for Office 365](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
After you add these records at United Domains, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit. 
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. In the **DNS Records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may need to scroll down.)
    
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Subdomain**|**Record Type**|**Value**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT Record  <br/> |MS=ms *XXXXXXXX*  <br/>**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![UnitedDomains-BP-Verify-1-1](../media/b596efe5-3a06-4104-ac26-8e470d69c2db.png)
  
4. Choose the **Save** control that is indicated in the following illustration. 
    
    ![UnitedDomains-BP-Verify-1-2](../media/b47b6111-387a-4cf0-9eec-f16d50b91c03.png)
  
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    ![Domain name selected in Microsoft 365 admin center](../media/c61204f1-a025-448b-a2a1-c4d7abee7a06.png)
  
3. On the **Setup** page, choose **Start setup**.
    
    ![Start setup](../media/5f6578af-ae32-49e8-b283-ec2d080420da.png)
  
4. On the **Verify domain** page, choose **Verify**.
    
    ![Verify](../media/c256ab1d-03f2-498e-bb63-19e4d49a6b97.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit. 
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. In **DNS Records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may need to scroll down.)
    
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Subdomain**|**Record Type**|**Value**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |MX Record  <br/> |10  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> The 10 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 account.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
     ![UnitedDomains-BP-Configure-2-1](../media/6e24cc3f-fada-4d14-8358-f18ca83720ce.png)
  
4. Choose the **Save** control that is indicated in the following illustration. 
    
    ![UnitedDomains-BP-Configure-2-2](../media/b98faf3d-1d7b-45fd-9d40-1191e86074fb.png)
  
5. If there are any other MX records, remove each of them by choosing **delete** for that record. 
    
    ![UnitedDomains-BP-Configure-2-3](../media/435dcd6f-18ae-4c0e-a043-9091096caaf4.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit. 
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. Choose **+ Add new record**.
    
    ![UnitedDomains-BP-Configure-3-1](../media/0cca691b-316f-4c13-bc38-e03363cba954.png)
  
4. Add the required CNAME records.
    
    In the **DNS Records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
        
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Subdomain**|**Record Type**|**Value**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME Record  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME Record  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME Record  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |msoid  <br/> |CNAME Record  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME Record  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME Record  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![UnitedDomains-BP-Configure-3-2](../media/7773fdf5-24f7-49d1-87e9-eb4c53edae29.png)
  
5. When you've added the final new CNAME record, choose the **Save** control that is indicated in the following illustration. 
    
    ![UnitedDomains-BP-Configure-3-3](../media/91abe959-ef31-4563-8afb-488296d580a7.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit. 
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. In the **DNS Records** section, in the boxes for the new record, type or paste the values from the following table. 
    
    (You may need to scroll down.)
    
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Subdomain**|**Record Type**|**Value**|
    |:-----|:-----|:-----|
    |(Leave this box empty.)  <br/> |TXT Record  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![UnitedDomains-BP-Configure-4-1](../media/6b86e269-e1b7-47bd-a87d-2e6d693ce865.png)
  
4. Choose the **Save** control that is indicated in the following illustration. 
    
    ![UnitedDomains-BP-Configure-4-2](../media/3f488358-7dd1-443d-a630-1810990860fd.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at United Domains by using [this link](https://www.uniteddomains.com/portfolio/index/domainlist/). You'll be prompted to log in.
    
2. Under **My Domain List**, in the **Manage Settings** column, choose **DNS** for the domain that you want to edit. 
    
    ![UnitedDomains-BP-Configure-1-2](../media/4b888afd-1870-4f77-97b9-65d843f65442.png)
  
3. Add the first of the two required SRV records.
    
    In the **DNS Records** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
    (You may need to scroll down.)
    
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Subdomain**|**Record Type**|**Value**|
    |:-----|:-----|:-----|
    |_sip._tls|SRV Record|100 1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br>**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
    |_sipfederationtls._tcp|SRV Record|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br>**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![UnitedDomains-BP-Configure-5-1](../media/9ba36aca-8567-4be8-823d-1f7a69a95993.png)
  
4. Choose **+ Add new record**.
    
    ![UnitedDomains-BP-Configure-5-2](../media/857e15c0-d67b-4227-993d-226d74d9abf6.png)
  
5. Add the second SRV record.
    
    Type or copy and paste the values from the second row of the table above into the boxes for the second record.
    
    ![UnitedDomains-BP-Configure-5-3](../media/871563b7-04d2-42df-963c-8b9a59758558.png)
  
6. When you've added both SRV records, choose the **Save** control that is indicated in the following illustration. 
    
    ![UnitedDomains-BP-Configure-5-4](../media/15680c13-aab9-43ca-84b8-8a8cbf61b328.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

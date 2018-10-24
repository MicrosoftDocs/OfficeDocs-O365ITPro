---
title: "Create DNS records at Heart Internet for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_HI'
- 'O365M_DOM_HI'
- 'O365E_DOM_HI'
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
ms.assetid: 74ae495b-d347-4539-89eb-bb771ae669d1
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Heart Internet for Office 365."
---

# Create DNS records at Heart Internet for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Heart Internet is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-heart-internet.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-heart-internet.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-heart-internet.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-heart-internet.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-heart-internet.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-heart-internet.md#BKMK_add_SRV)
    
After you add these records at Heart Internet, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.co.uk/manage/manage.cgi). You'll be prompted to log-in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the **Manage Domain Parking** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
4. In the **Manage Domain** section, choose **DNS Management**.
    
5. In the **TXT Records** section, in the **Text** box for the new record, type or copy and paste the value from the following table. 
    
    (You may have to scroll down.) 
    
|||
|:-----|:-----|
|**Subdomain** <br/> |**Text** <br/> |
|(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Choose **Update DNS**.
    
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

1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.co.uk/manage/manage.cgi). You'll be prompted to log-in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the **Manage Domain Parking** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
    ![HeartInternet-BP-Configure-1-3](../media/51e545f1-176b-4569-b98f-bf5e673facb3.png)
  
4. In the **Manage Domain** section, choose **DNS Management**.
    
5. In the **MX Records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
|**Subdomain**|**Mail server**|**Priority**|
|:-----|:-----|:-----|
|(Leave this field empty.)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> > [!NOTE]> Get your \< *domain-key*  \> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![HeartInternet-BP-Configure-2-1](../media/05d1b532-3daa-43d9-be89-dcd15b9a38f5.png)
  
6. Choose **Update DNS**.
    
    ![HeartInternet-BP-Configure-2-2](../media/a2926530-fe6b-4f8a-92a5-e860da7d0dd3.png)
  
7. If there are any other MX records in the **MX Records** section, remove them by selecting each of them in the **Delete** column and then choosing **Update DNS** again. 
    
    ![HeartInternet-BP-Configure-2-3](../media/f948c812-8318-47ba-af84-5b4ca24dd0bf.png)
  
8. Then choose **Update DNS** again. 
    
    ![HeartInternet-BP-Configure-2-4](../media/08253923-6bee-4986-a9da-93ef9e2790a4.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.co.uk/manage/manage.cgi). You'll be prompted to log-in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the **Manage Domain Parking** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
    ![HeartInternet-BP-Configure-1-3](../media/51e545f1-176b-4569-b98f-bf5e673facb3.png)
  
4. In the **Manage Domain** section, choose **DNS Management**.
    
5. Add the first two of the six CNAME records.
    
    In the **CNAME Records** section, in the boxes for the two new records, type or copy and paste the values from the first two rows of the following table. 
    
    (You may have to scroll down.)
    
|**Subdomain**|**Address**|
|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
|sip  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
|msoid  <br/> |clientconfig.microsoftonline-p.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
   ![HeartInternet-BP-Configure-3-1](../media/57714603-9278-4a55-904f-54b48d2ddec7.png)
  
6. Choose **Update DNS**.
    
    ![HeartInternet-BP-Configure-3-2](../media/8ee1985f-8691-4808-8b6e-b995e0f634fd.png)
  
7. Add the other four CNAME records.
    
    In the **Create New A/AAAA/CNAME** records section, create records using the values from the next two rows in the table, and then again choose **Update DNS**.
    
    Repeat this process until you have created all six CNAME records.
    
    ![HeartInternet-BP-Configure-3-4](../media/4b8bcec3-ac26-4373-89a9-ee1724a140b6.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.co.uk/manage/manage.cgi). You'll be prompted to log-in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the **Manage Domain Parking** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
    ![HeartInternet-BP-Configure-1-3](../media/51e545f1-176b-4569-b98f-bf5e673facb3.png)
  
4. In the **Manage Domain** section, choose **DNS Management**.
    
5. In the **TXT Records** section, in the **Text** box for the new record, type or copy and paste the value from the following table. 
    
    (You may have to scroll down.)
    
|**Subdomain**|**Text**|
|:-----|:-----|
|(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![HeartInternet-BP-Configure-4-1](../media/2cec212d-db02-4d5b-bf78-7e4070748d6b.png)
  
6. Choose **Update DNS**.
    
    ![HeartInternet-BP-Configure-4-2](../media/7db388f0-8a25-4f6d-a1f5-30c298ecbade.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Heart Internet by using [this link](https://customer.heartinternet.co.uk/manage/manage.cgi). You'll be prompted to log-in first.
    
2. On the **Manage Domain Names** page, in the drop-down list in the **Manage Domain Parking** section, select the name of the domain you're updating. 
    
3. Choose **Manage Now**.
    
    ![HeartInternet-BP-Configure-1-3](../media/51e545f1-176b-4569-b98f-bf5e673facb3.png)
  
4. In the **Manage Domain** section, choose **DNS Management**.
    
5. In the **SRV Records** section, in the boxes for the new records, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Select the **Service** and **Proto** values from the drop-down lists. For the **Service** value for the second record, choose **(Enter your own)** in the drop-down list, and then type or copy and paste the value **_sipfederationtls** ) 
    
|**Service**|**Proto**|**Server**|**Port**|**Pri**|**Wei**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP  <br/> |TLS  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |443  <br/> |100  <br/> |1  <br/> |
|_sipfederationtls  <br/> |TCP  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |5061  <br/> |100  <br/> |1  <br/> |
   
   ![HeartInternet-BP-Configure-5-1](../media/71bbbf65-b7b5-4269-8e42-26bee16b9128.png)
  
6. Choose **Update DNS**.
    
    ![HeartInternet-BP-Configure-5-2](../media/0f6aa75f-bab6-437d-9bbe-23c9b22da642.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 

---
title: "Create DNS records at iFastNet for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_O365_Domain_Registrars
- Adm_O365_Setup
ms.custom:
- Adm_O365
- Adm_O365_Setup
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6e1c713b-0915-45c4-937b-55d5d51ff88e
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at iFastNet for Office 365."
---

# Create DNS records at iFastNet for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If iFastNet is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you make all of these changes at iFastNet, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your cPanel page at iFastNet. You'll be prompted to log in first.
    
    (Each hosted account at iFastNet is assigned a unique cPanel address. Your cPanel address should look like this: https://YourHostAddress:secure-port-number. The sign-up email you received from iFastNet will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with iFastNet. To get started with Office 365, you can either purchase a hosting account from iFastNet or [redelegate your nameservers to point to Office 365](change-nameservers-at-ifastnet.md). 
  
    ![iFast-BP-Configure-1-1](../media/a88310c4-fe7a-48c2-adbb-bd467ad30516.png)
  
2. On the **iFastNet cPanel** page, in the **DOMAINS** area, choose **Advanced Zone Editor**.
    
    (You may have to scroll down.)
    
    ![iFast-BP-Configure-1-2](../media/c41ac6cc-14c3-42b4-8503-c6bf20a0b402.png)
  
3. In the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Type**|**Name**|**TTL**|**TXT Data**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |Use your  *domain_name*  . (For example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![iFast-BP-Verify-1-1](../media/badeea37-286e-471e-a333-8ab87b634ae1.png)
  
4. Choose **Add Record**.
    
    ![iFast-BP-Verify-1-2](../media/78d2e8eb-4ebe-476f-8e17-fd009860fcb0.png)
  
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your cPanel page at iFastNet. You'll be prompted to log in first.
    
    (Each hosted account at iFastNet is assigned a unique cPanel address. Your cPanel address should look like this: https://YourHostAddress:secure-port-number. The sign-up email you received from iFastNet will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with iFastNet. To get started with Office 365, you can either purchase a hosting account from iFastNet or [redelegate your nameservers to point to Office 365](change-nameservers-at-ifastnet.md). 
  
    ![iFast-BP-Configure-1-1](../media/a88310c4-fe7a-48c2-adbb-bd467ad30516.png)
  
2. On the **iFastNet cPanel** page, in the **EMAIL** area, choose **MX Entry**.
    
    (You may have to scroll down.)
    
    ![iFast-BP-Configure-2-1](../media/0b4f9c7e-5ff5-44b9-859b-d9696ca21ff3.png)
  
3. On the **MX Entry** page, select **Remote Mail Exchanger**.
    
    ![iFast-BP-Configure-2-2](../media/f40f15b9-5b4a-4ca8-a459-0129f1422502.png)
  
4. Choose **Change**.
    
    ![iFast-BP-Configure-2-3](../media/41330150-25c5-43de-9782-aa81ca182f55.png)
  
5. In the **Add New Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You might have to scroll down.)
    
|**Priority**|**Destination**|
|:-----|:-----|
|0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
   ![iFast-BP-Configure-2-4](../media/2799b541-e376-4a00-bffe-67d71664c4fc.png)
  
6. Choose **Add New Record**.
    
    ![iFast-BP-Configure-2-5](../media/c8616987-bbf8-4ce1-95aa-85549a4e884b.png)
  
7. If there are any other MX records in the **MX Records** section, remove each of them. 
    
    Begin by choosing **Remove** in the **Actions** column for one of the other records. 
    
    ![iFast-BP-Configure-2-6](../media/aeb850be-5241-47e9-8190-1a782dd50fc9.png)
  
8. Choose **Delete** to confirm the removal of that record. 
    
    ![iFast-BP-Configure-2-7](../media/8e7fb366-27f0-4784-8e8b-8e5675dfa64b.png)
  
9. Use the same process to remove each of the other records, keeping only the one that you created earlier in this procedure.
    
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your cPanel page at iFastNet. You'll be prompted to log in first.
    
    (Each hosted account at iFastNet is assigned a unique cPanel address. Your cPanel address should look like this: https://YourHostAddress:secure-port-number. The sign-up email you received from iFastNet will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with iFastNet. To get started with Office 365, you can either purchase a hosting account from iFastNet or [redelegate your nameservers to point to Office 365](change-nameservers-at-ifastnet.md). 
  
    ![iFast-BP-Configure-1-1](../media/a88310c4-fe7a-48c2-adbb-bd467ad30516.png)
  
2. On the **iFastNet cPanel** page, in the **DOMAINS** area, choose **Advanced Zone Editor**.
    
    (You may have to scroll down.)
    
    ![iFast-BP-Configure-1-2](../media/c41ac6cc-14c3-42b4-8503-c6bf20a0b402.png)
  
3. Add the first of the six CNAME records.
    
    In the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Type**|**Name**|**TTL**|**CNAME**|
|:-----|:-----|:-----|:-----|
|CNAME  <br/> |autodiscover. *domain_name*  . (For example, autodiscover.fourthcoffee.com)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |autodiscover.outlook.com  <br/> |
|CNAME  <br/> |sip. *domain_name*  .(For example, sip.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |sipdir.online.lync.com  <br/> |
|CNAME  <br/> |lyncdiscover. *domain_name*  . (For example, lyncdiscover.fourthcoffee.com.  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |webdir.online.lync.com  <br/> |
|CNAME  <br/> |msoid. *domain_name*  . (For example, msoid.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |msoid.online.lync.com  <br/> |
|CNAME  <br/> |enterpriseregistration. *domain_name*  . (For example, enterpriseregistration.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |enterpriseregistration.windows.net  <br/> |
|CNAME  <br/> |enterpriseenrollment. *domain_name*  . (For example, enterpriseenrollment.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
   ![iFast-BP-Configure-3-1](../media/023389cc-adc1-4f67-ba01-0fdaa0d2005d.png)
  
4. Choose **Add Record**.
    
    ![iFast-BP-Configure-3-2](../media/1da1fab1-2dd4-416a-86f3-a7232e31dc5c.png)
  
5. Add each of the other five CNAME records.
    
    In the **Add a Record** area, create a record by using the values from the next row in the table, and then again choose **Add Record** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. To get started, go to your cPanel page at iFastNet. You'll be prompted to log in first.
    
    (Each hosted account at iFastNet is assigned a unique cPanel address. Your cPanel address should look like this: https://YourHostAddress:secure-port-number. The sign-up email you received from iFastNet will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with iFastNet. To get started with Office 365, you can either purchase a hosting account from iFastNet or [redelegate your nameservers to point to Office 365](change-nameservers-at-ifastnet.md). 
  
    ![iFast-BP-Configure-1-1](../media/a88310c4-fe7a-48c2-adbb-bd467ad30516.png)
  
2. On the **iFastNet cPanel** page, in the **DOMAINS** area, choose **Advanced Zone Editor**.
    
    (You may have to scroll down.)
    
    ![iFast-BP-Configure-1-2](../media/c41ac6cc-14c3-42b4-8503-c6bf20a0b402.png)
  
3. In the **Add a Record** area, in the boxes for the new record, type or copy and paste the vales from the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Type**|**Name**|**TTL**|**TXT Data**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |Use your  *domain_name*  . (For example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
   ![iFast-BP-Configure-4-1](../media/55d1e5d6-5f2c-4952-af0a-6570cf3de80e.png)
  
4. Choose **Add Record**.
    
    ![iFast-BP-Configure-4-2](../media/b753ca7f-6d40-43a9-8367-7ec0c1f519a6.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your cPanel page at iFastNet. You'll be prompted to log in first.
    
    (Each hosted account at iFastNet is assigned a unique cPanel address. Your cPanel address should look like this: https://YourHostAddress:secure-port-number. The sign-up email you received from iFastNet will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with iFastNet. To get started with Office 365, you can either purchase a hosting account from iFastNet or [redelegate your nameservers to point to Office 365](change-nameservers-at-ifastnet.md). 
  
    ![iFast-BP-Configure-1-1](../media/a88310c4-fe7a-48c2-adbb-bd467ad30516.png)
  
2. On the **iFastNet cPanel** page, in the **DOMAINS** area, choose **Advanced Zone Editor**.
    
    (You may have to scroll down.)
    
    ![iFast-BP-Configure-1-2](../media/c41ac6cc-14c3-42b4-8503-c6bf20a0b402.png)
  
3. Add the first of the two SRV records.
    
    In the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    (Select the **Type** value from the drop-down list.) 
    
|**Type**|**Name**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SRV  <br/> |_sip._tls. *domain_name*  . (For example, _sip._tls.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
|SRV  <br/> |_sipfederationtls._tcp. *domain_name*  . (For example, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
   ![iFast-BP-Configure-5-1](../media/f8746617-67b4-432c-a303-7f45d48fcbcf.png)
  
4. Choose **Add Record**.
    
    ![iFast-BP-Configure-5-2](../media/cdbcde13-011c-49b3-9ce6-819817ec0dd5.png)
  
5. Add the other SRV record.
    
    In the **Add a Record** area, create a record by using the values from the next row in the table, and then again choose **Add Record** to complete that record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 

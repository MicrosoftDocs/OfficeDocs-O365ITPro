---
title: "Create DNS records at Hostgator for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Hostgator'
- 'O365M_DOM_Hostgator'
- 'O365E_DOM_Hostgator'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Hostgator for Office 365."
---

# Create DNS records at Hostgator for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If Hostgator is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
> [!IMPORTANT]
> You must perform the first procedurebelow, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account), before you add DNS records by using any of the other procedures in this article. 

After you make all of these changes at Hostgator, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Point your domain to your hosting account
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> You must perform this procedure before you perform any of the other procedures in this article. 
  
Follow these steps to associate your domain and hosting accounts.
  
1. To get started, go to your domain management page at Hostgator by using [this link](https://register.hostgator.com/?manage). You'll be prompted to log in.
    
    ![Hostgator-BP-Redelegate-1-0](../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Select **Manage Domains**.
    
    ![Hostgator-BP-Redelegate-1-1](../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update. 
    
    ![Hostgator-BP-Redelegate-1-3](../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
4. Select **Name Servers**.
    
    ![Hostgator-BP-Redelegate-1-4](../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
5. On the **Name Servers** page for your domain, in the **To point this domain to an existing host account** drop-down list, choose the **hosting account** that is associated with your domain. 
    
    ![Hostgator-BP-Redelegate-1-5](../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
6. Select **Save Name Servers**.
    
    ![Hostgator-BP-Redelegate-1-9](../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account). 
  
Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md). 
  
2. On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
    |Use your  *domain_name*. (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Select **Add Record**.
    
5. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.
    
2. On the **Domains** page, select the domain that you are verifying. 
    
3. On the **Setup** page, select **Start setup**.
    
4. On the **Verify domain** page, select **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md). 
  
2. On the **Control Panel** page, in the **Mail** area, select **MX Entry**.
    
    (You may have to scroll down.)
    
    ![Hostgator-BP-Configure-2-1](../media/dfe89de2-5e69-4359-9036-c6de5523a003.png)
  
3. In the **Email Routing** area, select **Remote Mail Exchanger**.
    
    ![Hostgator-BP-Configure-2-2](../media/c3aeff9c-c168-4833-b1f0-1dab2c1facb8.png)
  
4. Select **Change**.
    
    ![Hostgator-BP-Configure-2-3](../media/9b263b0a-076e-40ba-abdb-35799e460a92.png)
  
5. On the **MX Entry Maintenance** page, in the **Add a New Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your \< *domain-key*  \> from your Office 365 account.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Hostgator-BP-Configure-2-4](../media/cedfb530-eb60-4e0b-82cc-35a30c9c1287.png)
  
6. Select **Add New Record**.
    
    ![Hostgator-BP-Configure-2-5](../media/fa0ef9c1-7e8a-40cc-b8f3-0e7cad7c6026.png)
  
7. If there are any other MX records in the **MX Records** section, remove each of them: 
    
    Begin by choosing **Delete** in the **Action** column for one of the other records. 
    
    ![Hostgator-BP-Configure-2-6](../media/e6e0e834-c414-4038-937d-65186657b14a.png)
  
8. Select **Delete** to confirm the removal of that record. 
    
    ![Hostgator-BP-Configure-2-7](../media/7f615e35-2755-42e9-ab79-4ea30b858bc2.png)
  
9. Use the same process to remove each of the other records, keeping only the one that you created earlier in this procedure.
    
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md). 
  
2. On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.
    
    (You may have to scroll down.)
    
3. Add the first of the six CNAME records.
    
    On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (for example, autodiscover.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (for example, sip.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (for example, lyncdiscover.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (for example, enterpriseregistration.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (for example, enterpriseregistration.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Hostgator-BP-Configure-3-1](../media/9f9e988b-9f8a-4f7b-a6da-c04bd8e5da7c.png)
  
4. Select **Add Record**.
    
    ![Hostgator-BP-Configure-3-2](../media/5d82422e-6e38-4cc3-bd1c-9154a9cad471.png)
  
5. Add each of the other five CNAME records.
    
    In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record. 
    
    Repeat this process until you have created all six CNAME records.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md). 
  
2. On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.
    
    (You may have to scroll down.)
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Use your  *domain_name*. (for example, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Hostgator-BP-Configure-4-1](../media/e3e6c591-2678-4b6a-b5ba-a03389a98906.png)
  
4. Select **Add Record**.
    
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account](#point-your-domain-to-your-hosting-account). 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started with Office 365, you can either purchase a hosting account from Hostgator or [redelegate your nameservers to point to Office 365](change-nameservers-at-hostgator.md). 
  
2. On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.
    
    (You may have to scroll down.)
    
3. Add the first of the two SRV records.
    
    On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**TTL**|**Type**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls. *domain_name*. (for example, _sip._tls.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*. (for example, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
   ![Hostgator-BP-Configure-5-1](../media/6a9e1afd-e9fa-4b37-b65e-689668f7eee9.png)
  
4. Select **Add Record**.
    
    ![Hostgator-BP-Configure-5-2](../media/801990e1-e311-406c-ab2d-dd5b163dc496.png)
  
5. Add the other SRV record.
    
    In the **Add a Record** section, create a record by using the values from the next row in the table, and then again select **Add Record** to complete that record. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 

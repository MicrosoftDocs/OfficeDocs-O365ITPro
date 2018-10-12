---
title: "Create DNS records at Netfirms for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe

ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_Netf'
- 'O365M_DOM_Netf'
- 'O365E_DOM_Netf'
ms.service: o365-administration
localization_priority: Priority
ms.custom:
- Adm_O365
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 967be009-94a4-46a9-8f0d-5ed15020d45a

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Netfirms for Office 365."
---

# Create DNS records at Netfirms for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
> [!CAUTION]
> The Netfirms website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at Netfirms, there are significant [service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider. 
  
If despite the service limitations you choose to manage your own Office 365 DNS records at Netfirms, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-netfirms.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-netfirms.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-netfirms.md#BKMK_add_MX)
    
- [Add the CNAME records that are required for Office 365](create-dns-records-at-netfirms.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-netfirms.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-netfirms.md#BKMK_add_SRV)
    
After you add these records at Netfirms, your domain will be set up to work with Office 365 services, though not with the Skype for Business Online and Outlook Web App mentioned above.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Netfirms by using [this link](https://www2.netfirms.com/controlpanel/domaincentral). You'll be prompted to log in first.
    
2. In the **My Favorites** section, choose **Domain Central**.
    
3. In the **Domain** column, choose the name of the domain that you want to edit. 
    
4. In the **Overview** row, choose **DNS**.
    
5. In the **Modify** drop-down list, choose **TXT/SPF Record**.
    
6. Under **Content**, in the box for the new record, type or copy and paste the value from the following table.
    
||
|:-----|
|**Content** <br/> |
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365. [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Choose **Add**.
    
8. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at Netfirms by using [this link](https://www2.netfirms.com/controlpanel/domaincentral). You'll be prompted to log in first.
    
2. In the **My Favorites** section, choose **Domain Central**.
    
3. In the **Domain** column, choose the name of the domain that you want to edit. 
    
4. In the **Overview** row, choose **DNS**.
    
5. In the **Modify** drop-down list, choose **MX Record**.
    
    ![Netfirms-BP-Configure-2-1](../media/d12dff8b-41fd-4c51-9344-a120c0c037cf.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
|**Priority**|**Host**|**Points To:**|
|:-----|:-----|:-----|
|0  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your \< *domain-key*  \> from your Office 365 portal account. > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Netfirms-BP-Configure-2-2](../media/485c9b77-6ebc-4c8e-b245-3eec54b110a4.png)
  
7. Choose **Add**.
    
    ![Netfirms-BP-Configure-2-3](../media/940fecfc-79ad-47ad-a25f-0902d2662c5f.png)
  
8. If there are any other existing MX records, choose **Remove** in the **Action** column for each one to remove it. 
    
    ![Netfirms-BP-Configure-2-4](../media/19ab4c75-685e-4c30-8311-9f86ef289097.png)
  
9. Choose **OK** to confirm your deletion. 
    
    ![Netfirms-BP-Configure-2-5](../media/fcba10bb-290d-458a-ac0a-068fc5504da1.png)
  
## Add the CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Netfirms by using [this link](https://www2.netfirms.com/controlpanel/domaincentral). You'll be prompted to log in first.
    
2. In the **My Favorites** section, choose **Domain Central**.
    
3. In the **Domain** column, choose the name of the domain that you want to edit. 
    
4. In the **Overview** row, choose **DNS**.
    
5. In the **Modify** drop-down list, choose **CNAME Alias**.
    
    ![Netfirms-BP-Configure-3-1](../media/addb9c08-96ec-4f47-963d-3827cf8bceb7.png)
  
6. Add the first CNAME record.
    
    In the boxes for the new record, type or copy and paste the values from the first row of the following table.
    
|**Host**|**Points To:**|
|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
|msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![Netfirms-BP-Configure-3-2](../media/c8e26900-742a-4a42-a60d-d638477f4043.png)
  
7. Choose **Add** to add the first record. 
    
    ![Netfirms-BP-Configure-3-3](../media/5c4db029-0e64-4b34-8599-d9778f32e989.png)
  
8. Add the second CNAME record.
    
    Use the values from the second row of the table above, and then choose **Add** to add the second record. 
    
    Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values. Need examples? Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at Netfirms by using [this link](https://www2.netfirms.com/controlpanel/domaincentral). You'll be prompted to log in first.
    
2. In the **My Favorites** section, choose **Domain Central**.
    
3. In the **Domain** column, choose the name of the domain that you want to edit. 
    
4. In the **Overview** row, choose **DNS**.
    
5. In the **Modify** drop-down list, choose **TXT/SPF Record**.
    
    ![Netfirms-BP-Configure-4-1](../media/5073681a-59cf-4992-bd95-4dc7a57547ac.png)
  
6. Under **Content**, in the box for the new record, type or copy and paste the value from the following table.
    
|**Content**|
|:-----|
|v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![Netfirms-BP-Configure-4-2](../media/536b60c6-a59f-4c12-a3b6-6de4a5053914.png)
  
7. Choose **Add**.
    
    ![Netfirms-BP-Configure-4-3](../media/228ac96b-7dba-4977-aa90-6979b2d12391.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> The Netfirms website doesn't support SRV records, which means that several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at Netfirms, there are significant [service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

---
title: "Create DNS records at Rackspace for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f51b14b-78fc-4c77-8beb-c11fbdea3379
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Rackspace for Office 365."
---

# Create DNS records at Rackspace for Office 365

[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for. 
  
If you manage the DNS records for your domain through Rackspace, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
Rackspace Cloud is not a domain registrar, but if you have a domain registered with another provider and your domain's nameservers have been updated to direct DNS queries to Rackspace, you can use Rackspace Cloud to manage your DNS records as described in this article.
  
These are the main records to add.
  
- [Create DNS records at Rackspace for Office 365](#create-dns-records-at-rackspace-for-office-365)
    
- [Add an MX record so email for your domain will come to Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Add the CNAME records that are required for Office 365](#add-the-cname-records-that-are-required-for-office-365)
    
- [Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Add the two SRV records that are required for Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
After you add these records at Rackspace, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="bkmk_txt"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page in Rackspace by using [this link](https://login.Rackspace.com). You'll be prompted to log in.
    
    ![Rackspace_login](../media/aa52b13f-08e3-4aeb-ae76-14452a9f030d.png)
  
2. Select **Networking**, and then select **Networking**.
    
    ![Rackspace_NetworkingCloudDNS](../media/9933b96a-b28c-4da5-98b4-77e06889b6f3.png)
  
3. On the **Cloud DNS** page, choose your domain name. 
    
    ![Rackspace_selectDomainName](../media/302c6358-58c3-4917-bab0-3def8aa2f3b9.png)
  
4. Choose **Add Record**. Next to **Record Type**, choose **TXT**. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Record Type**|**Hostname**|**Text**|**Time to Live (TTL)**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(leave blank)  <br/> |MS=msXXXXXXXX  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)   |60 Minutes  <br/> |
   
    ![Rackspace_TXTforVerificationValues](../media/d00b252c-10d3-4a16-a7ac-fc75b292db18.png)
  
5. Select **Add Record**.
    
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. Choose **Setup** \> **Domains**.
    
2. On the **Domains** page, choose the domain that you are verifying. 
    
    
  
3. On the **Setup** page, choose **Start setup**.
    
    
  
4. On the **Verify domain** page, choose **Verify**.
    
    
  
## Add an MX record so email for your domain will come to Office 365
<a name="bkmk_mx"> </a>

1. To get started, go to your domains page in Rackspace by using [this link](https://login.Rackspace.com). You'll be prompted to log in.
    
    ![Rackspace_login](../media/9a2c09d3-95ef-4b77-ae02-4d3ccffa40c3.png)
  
2. Select **Networking**, and then select **Cloud DNS**.
    
    ![Rackspace_NetworkingCloudDNS](../media/05d17cd8-c2bc-44c8-b8ec-dd6f71528976.png)
  
3. On the **Cloud DNS** page, choose your domain name. 
    
    ![Rackspace_selectDomainName](../media/b19a153e-0cb1-4698-89f1-6975c64b06d9.png)
  
4. Choose **Add Record**. Next to **Record Type**, choose **MX**. In the boxes for the new record, type or copy and paste the following values.
    
    |**Record Type**|**Hostname**|**Mailserver Domain**|**Priority**|**Time to Live (TTL)**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(leave blank)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 account.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)   |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |60 Minutes  <br/> |
   
    ![Rackspace_MXrecordValues](../media/d26b9323-82f5-4eac-a383-878ecb4dff79.png)
  
5. Select **Add Record** to save the record. 
    
6. If there are any other MX records, delete them. Next to the MX record, select the gear icon, and then select **Delete Record**. Select **Delete Record** again to confirm. 
    
    ![Rackspace_MXrecordDelete](../media/50f2b856-f74a-4e43-b83b-5bf8e6cef349.png)
  
## Add the CNAME records that are required for Office 365
<a name="bkmk_cname"> </a>

1. To get started, go to your domains page in Rackspace by using [this link](https://login.Rackspace.com). You'll be prompted to log in.
    
    ![Rackspace_login](../media/bb1eff97-d27e-493e-ac19-329c5626b44f.png)
  
2. Select **Networking**, and then select **Cloud DNS**.
    
    ![Rackspace_NetworkingCloudDNS](../media/d02865e6-3903-4a0d-ab59-b2dbfc320048.png)
  
3. On the **Cloud DNS** page, choose your domain name. 
    
    ![Rackspace_selectDomainName](../media/2ee00b08-c5de-49ce-baae-b9afe0cdc221.png)
  
4. Choose **Add Record**. Next to **Record Type**, choose **CNAME**. In the boxes for the new record, type or copy and paste the following values.
    
    |**Record Type**|**Hostname**|**Target (Domain)**|**Time to Live (TTL)**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |60 Minutes  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |60 Minutes  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |60 Minutes  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |60 Minutes  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |60 Minutes  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |60 Minutes  <br/> |
       
    ![Rackspace_CNAMErecordValues](../media/18eec053-af71-4583-80e3-739261ccbfa7.png)
  
5. Select **Add Record** to save the record. 
    
6. Repeat the previous steps to create the other five CNAME records. For each record, type of copy and paste the values from the next row of the table above into the boxes for that record.
    
## Add a TXT record for SPF to help prevent email spam
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. 
  
1. To get started, go to your domains page in Rackspace by using [this link](https://login.Rackspace.com). You'll be prompted to log in.
    
    ![Rackspace_login](../media/30de8e2a-755e-4532-b15f-1b98b64e3f8c.png)
  
2. Select **Networking**, and then select **Cloud DNS**.
    
    ![Rackspace_NetworkingCloudDNS](../media/3876cdb5-396e-42b3-b39d-0d2eda38de0d.png)
  
3. On the **Cloud DNS** page, choose your domain name. 
    
    ![Rackspace_selectDomainName](../media/3e3efe23-c2da-498d-a641-4fe6a4dc6218.png)
  
4. Choose **Add Record**. Next to **Record Type**, choose **TXT**. In the boxes for the new record, type or copy and paste the following values.
    
    |**Record Type**|**Hostname**|**Text**|**Time to Live (TTL)**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(leave blank)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**NOte:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |60 Minutes  <br/> |
       
    ![Rackspace_TXTforSPFValues](../media/f61aa5ff-357f-4e01-91bb-7501d338fb16.png)
  
5. Select **Add Record** to save the record. 
    
## Add the two SRV records that are required for Office 365
<a name="bkmk_srv"> </a>

1. To get started, go to your domains page in Rackspace by using [this link](https://login.Rackspace.com). You'll be prompted to log in.
    
    ![Rackspace_login](../media/c4f5e2b5-5627-4e49-ba3d-16e12526d199.png)
  
2. Select **Networking**, and then select **Cloud DNS**.
    
    ![Rackspace_NetworkingCloudDNS](../media/531b6cd8-cc76-498b-8485-81f88735c054.png)
  
3. On the **Cloud DNS** page, choose your domain name. 
    
    ![Rackspace_selectDomainName](../media/f08c7029-10d4-49e3-af38-f1965f12f582.png)
  
4. Choose **Add Record**. Next to **Record Type**, choose **SRV**. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Record Type**|**Service**|**Protocol**|**Hostname**|**Target Domain**|**Port**|**Priority**|**Weight**|**Time to Live (TTL)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |sip  <br/> |tls  <br/> |(leave blank)  <br/> |sipdir.online.lync.com  <br/> |443  <br/> |100  <br/> |1  <br/> |60 Minutes  <br/> |
    |SRV (Service)  <br/> |sipfederationtls  <br/> |tcp  <br/> |(leave blank)  <br/> |sipfed.online.lync.com  <br/> |5061  <br/> |100  <br/> |1  <br/> |60 Minutes  <br/> |
       
     ![Rackspace_SRVrecordValues](../media/4ffbd17d-ca18-4220-a4cb-70b95a362d0d.png)
  
5. Select **Add Record** to save the record. 
    
6. Repeat the previous steps to create the other SRV record. Type or copy and paste the values from the second row of the table above into the boxes for the second record.
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  


---
title: "Create DNS records at NoIP for Office 365"
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
ms.assetid: 2784a5a5-a8b5-477c-8c0e-f824a718b592

description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at NoIP for Office 365."
---

# Create DNS records at NoIP for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If NoIP is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
> [!IMPORTANT]
> You need a NoIP  *Plus Managed DNS*  account or better to create all the DNS record types required for Office 365. If your account does not meet this requirement, you will be able to create all record types except for the CNAME records required for Exchange OnlineExchange Online and Skype for Business. 
  
These are the main records to add. (Need more help? [Still need help?](create-dns-records-at-noip.md#BKMK_NeedHelp).)
  
- [Add a TXT record for verification](create-dns-records-at-noip.md#BKMK_verify)
    
- [Add an MX record so email for your domain will come to Office 365](create-dns-records-at-noip.md#BKMK_add_MX)
    
- [Add the six CNAME records that are required for Office 365](create-dns-records-at-noip.md#BKMK_add_CNAME)
    
- [Add a TXT record for SPF to help prevent email spam](create-dns-records-at-noip.md#BKMK_add_TXT)
    
- [Add the two SRV records that are required for Office 365](create-dns-records-at-noip.md#BKMK_add_SRV)
    
After you add these records at NoIP, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Modify** for the domain that you want to edit. 
    
    > [!IMPORTANT]
    > Choose the naked domain, without prefixes such as "ftp", "mail", or "www". 
  
    ![NoIP-BP-Configure-1-2](../media/d964404e-d5c9-4be7-a060-e48bf8099b3d.png)
  
3. In the **Hostname Information** section, in the **Advanced Records** row, choose **TXT**.
    
    ![NoIP-BP-Verify-1-1](../media/cf8ef84a-fea8-4036-8127-d965a2d91253.png)
  
4. In the **TXT record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
|**TXT Record**|
|:-----|
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![NoIP-BP-Verify-1-2](../media/3a7b6740-794c-4b3b-a140-518e1f04fa2a.png)
  
5. Choose **Submit**.
    
    ![NoIP-BP-Verify-1-3](../media/da3030b8-5e0f-4ba1-bb8b-2272eaa38cd4.png)
  
6. Wait a few minutes before you continue, so that the record you just created can update across the Internet.
    
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

1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Modify** for the domain that you want to edit. 
    
    > [!IMPORTANT]
    > Choose the naked domain, without prefixes such as "ftp", "mail", or "www". 
  
    ![NoIP-BP-Configure-1-2](../media/d964404e-d5c9-4be7-a060-e48bf8099b3d.png)
  
3. In the **Mail Options** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
|**MX Record**|**MX Priority**|
|:-----|:-----|
| *\<domain-key\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |5  <br/> (This is the default value.)  <br/> |
   
    ![NoIP-BP-Configure-2-1](../media/7fdf72ed-d6ce-4074-98ca-df1e83eea349.png)
  
4. Choose **Update Host**.
    
    ![NoIP-BP-Configure-2-2](../media/c1f642e2-ca8d-4a9e-a413-659bb27c966d.png)
  
5. If there are any other existing MX records, delete each record by selecting the entry and then pressing the **Delete** key on your keyboard. 
    
    ![NoIP-BP-Configure-2-3](../media/81ff6392-259e-4c98-8612-13b9b535cf0b.png)
  
6. If you have deleted any records, choose **Update Host**.
    
    ![NoIP-BP-Configure-2-2](../media/c1f642e2-ca8d-4a9e-a413-659bb27c966d.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

To create a CNAME record, NoIP requires a two-step process. First, you create a set of hostnames at NoIP, and then you assign them to CNAME records.
  
1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Add a Host**.
    
    ![NoIP-BP-Configure-3-1](../media/fc424b7e-db3a-4a54-8752-8f5ebb96d12e.png)
  
3. Select the Domain value from the drop-down list.
    
    (You may have to scroll through the list.)
    
    ![NoIP-BP-Configure-3-2-1](../media/29cd531e-d5aa-41c5-9593-bdbb179da959.png)
  
4. Add the first **CNAME** record. 
    
    In the **Host Information** section, in the box for the new record, type or copy and paste the first **Hostname** value from the following table. 
    
|**Hostname**|**Domain**|**Target**|
|:-----|:-----|:-----|
|autodiscover  <br/> |Select your  *domain_name*  , for example, contoso.com.  <br/> |autodiscover.outlook.com  <br/> |
|sipdir  <br/> |Select your  *domain_name*  , for example, contoso.com.  <br/> |sipdir.online.lync.com  <br/> |
|webdir  <br/> |Select your  *domain_name*  , for example, contoso.com.  <br/> |webdir.online.lync.com  <br/> |
|clientconfig  <br/> |Select your  *domain_name*  , for example, contoso.com.  <br/> |clientconfig.microsoftonline-p.net  <br/> |
|enterpriseregistration  <br/> |Select your  *domain_name*  , for example, contoso.com.  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |Select your  *domain_name*  , for example, contoso.com.  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |
   
    ![NoIP-BP-Configure-3-2-2](../media/660dfdfc-949e-419e-9b23-caeb3ac3d934.png)
  
5. Choose **DNS Alias (CNAME)**.
    
    ![NoIP-BP-Configure-3-2-3](../media/441324b5-da25-4d7d-b8d7-3cfe1f931960.png)
  
6. In the box for the new record, type or copy and paste the first **Target** value from the table. 
    
    ![NoIP-BP-Configure-3-2-4](../media/4c3ea6bd-38aa-4975-a339-768fb2b4c350.png)
  
7. Choose **Add Host**.
    
    ![NoIP-BP-Configure-3-3](../media/5213dddb-b6a7-4b2e-98ff-5c95cfce64d3.png)
  
8. Add the second **CNAME** record. 
    
    Choose **Add a Host** from the **Manage Hosts** page, and in the **Host Information** section, in the box for the new record, use the values from the second row of the table above. Then choose **Add Host** to add the second record. 
    
    Add the remaining records in the same way using the values from the third, fourth, fifth, and sixth rows of the table.
    
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values. Need examples? Check out these [](external-domain-name-system-records.md#BKMK_SPFrecords). To validate your SPF record, you can use one of these [SPF validation tools](92a43f6a-4651-455a-a1cc-300684bedcfa.md). 
  
1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Modify** for the domain that you want to edit. 
    
    > [!IMPORTANT]
    > Choose the naked domain, without prefixes such as "ftp", "mail", or "www". 
  
    ![NoIP-BP-Configure-1-2](../media/d964404e-d5c9-4be7-a060-e48bf8099b3d.png)
  
3. In the **Hostname Information** section, in the **Advanced Records** row, choose **TXT**.
    
    ![NoIP-BP-Configure-4-1](../media/18742424-4aec-4c07-b325-2196e987bdda.png)
  
4. In the **TXT Record** area, add double-quotes to the start and end of the entry for the existing record, then press **Enter** on your keyboard to create a new line. 
    
    On that new line (under the existing value), type or copy and paste the value from the following table, making sure to add double-quotes to the start and end of the value. (You can see an example in the screenshot below the table.)
    
|**TXT Record**|
|:-----|
|v=spf1 include:spf.protection.outlook.com -all  <br/> > [!NOTE]> We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![NoIP-BP-Configure-4-2](../media/322de050-3a8a-4a5b-857e-7ec407a32201.png)
  
5. Choose **Update**.
    
    ![NoIP-BP-Configure-4-3](../media/1187d9dd-e479-479c-8d7e-b5a64c8011b2.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at NoIP by using [this link](https://www.noip.com/login?ref_url=%2Fmembers%2Fdns%2F). You'll be prompted to Sign In.
    
    ![NoIP-BP-Configure-1-1](../media/22cdfc00-b081-48f0-b15d-59c78cb68395.png)
  
2. On the **Manage Hosts** page, choose **Modify**.
    
    > [!IMPORTANT]
    > Choose the naked domain, without prefixes such as "ftp", "mail", or "www". 
  
    ![NoIP-BP-Configure-1-2](../media/d964404e-d5c9-4be7-a060-e48bf8099b3d.png)
  
3. In the **Hostname Information** section, in the **Advanced Records** row, choose **SRV**.
    
    ![NoIP-BP-Configure-5-1](../media/0363d36b-3a36-4fcf-a4f0-5c912e5cc522.png)
  
4. Create the first SRV record.
    
    In the **Create SRV record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table. 
    
    (Select the **Protocol** value in the **Protocol** row.) 
    
|**Service**|**Protocol**|**Priority**|**Weight**|**Target**|**Port**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  <br/> |TLS  <br/> |100  <br/> |1  <br/> |sipdir.online.lync.com  <br/> |443  <br/> |300  <br/> |
|sipfederationtls  <br/> |TCP  <br/> |100  <br/> |1  <br/> |sipfed.online.lync.com  <br/> |5061  <br/> |300  <br/> |
   
    ![NoIP-BP-Configure-5-2](../media/386af063-74d0-4da0-ae1d-57710f537649.png)
  
5. Choose **Submit**.
    
    ![NoIP-BP-Configure-5-3](../media/6226c873-428b-44e3-83f9-6e5a5da06466.png)
  
6. To add the other SRV record.
    
    In the **Update Host** page, choose **SRV**, create a record using the values from the next row in the table, and then again choose **Submit** to complete that record. 
    
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

---
title: "Create DNS records at Freeparking.co.nz for Office 365"
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
f1_keywords:
- 'O365P_DOM_FreeP'
- 'O365M_DOM_FreeP'
- 'O365E_DOM_FreeP'
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
ms.assetid: b22df8b4-7d3a-4327-af90-5bacbb3c11ee
description: "Learn to verify your domain and set up DNS records for email, Skype for Business Online, and other services at Freeparking.co.nz for Office 365."
---

# Create DNS records at Freeparking.co.nz for Office 365

 **[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for. 
  
If FreeParking.co.nz is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.
  
After you add these records at FreeParking.co.nz, your domain will be set up to work with Office 365 services.
  
To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add a TXT record for verification
<a name="BKMK_verify"> </a>

Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, choose the **Service Management** tab. 
    
    ![FreeparkingNZ-BP-Configure-1-3-1](../media/23a0863e-d792-4026-a05e-6598af21e1fd.png)
  
4. In the **Name Server Records** section, choose **Modify**.
    
    ![FreeparkingNZ-BP-Configure-1-3-2](../media/9767944c-a27a-4b66-949e-d2d3d2c7cf2d.png)
  
5. Choose **Advanced View**.
    
    ![FreeparkingNZ-BP-Configure-1-4-1](../media/f1d95e8d-7a63-4511-b53e-4c8d15c266c3.png)
  
6. Set the **Time to Live (TTL)** value for all records by selecting the **Data** value specified in the following table. 
    
    (Select the **Data** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Data**|
    |:-----|:-----|:-----|
    | *All records*  <br/> |Caching Time (TTL)  <br/> |1 Hour  <br/> |
   
    ![FreeparkingNZ-BP-Configure-1-4-2](../media/7caef32d-ba28-4d57-8ea3-7d694af5a47e.png)
  
7. Choose **Add another record**.
    
    ![FreeparkingNZ-BP-Configure-1-4-3](../media/9f204f1f-6078-4504-8ba7-e73bbcd96da6.png)
  
8. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Data**|
    |:-----|:-----|:-----|
    |Use your domain name (for example, fourthcoffee.com)  <br/> |Descriptive (TXT)  <br/> |MS=ms *XXXXXXXX*  <br/> **Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.  [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![FreeparkingNZ-BP-Verify-1-1](../media/927e8240-9cba-4431-bbc0-a016f5a44d0b.png)
  
9. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Verify-1-2](../media/2b721ea6-bb7e-4fea-8d51-13c9bdd11973.png)
  
10. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Verify-1-3](../media/9d7a3161-cd95-4f50-9809-d3d745be6f7c.png)
  
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
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## Add an MX record so email for your domain will come to Office 365
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, choose the **Service Management** tab. 
    
    ![FreeparkingNZ-BP-Configure-1-3-1](../media/23a0863e-d792-4026-a05e-6598af21e1fd.png)
  
4. In the **Name Server Records** section, choose **Modify**.
    
    ![FreeparkingNZ-BP-Configure-1-3-2](../media/9767944c-a27a-4b66-949e-d2d3d2c7cf2d.png)
  
5. Choose **Advanced View**.
    
    ![FreeparkingNZ-BP-Configure-1-4-1](../media/f1d95e8d-7a63-4511-b53e-4c8d15c266c3.png)
  
6. Set the **Time to Live (TTL)** value for all records by selecting the **Data** value specified in the following table. 
    
    (Select the **Data** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Data**|
    |:-----|:-----|:-----|
    | *All records*  <br/> |Caching Time (TTL)  <br/> |1 Hour  <br/> |
   
    ![FreeparkingNZ-BP-Configure-1-4-2](../media/7caef32d-ba28-4d57-8ea3-7d694af5a47e.png)
  
7. Choose **Add another record**.
    
    ![FreeparkingNZ-BP-Configure-1-4-3](../media/9f204f1f-6078-4504-8ba7-e73bbcd96da6.png)
  
8. In the **Mail Servers ("MX" Records**) section, in the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record Type** value from the drop-down list. To view the names of the fields under **Data**, point to each field.)
    
    (You may have to scroll down.)
    
    |**Host Name**|**Record Type**|**First Data Field (Preference)**|**Second Data Field (Target)**|
    |:-----|:-----|:-----|:-----|
    |Use your domain name (for example, fourthcoffee.com)  <br/> |Mail Server (MX)  <br/> |10  <br/> For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  <br/> **Note:** Get your  *\<domain-key\>*  from your Office 365 portal account.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![FreeparkingNZ-BP-Configure-2-1](../media/39382d03-eade-406b-95c1-e400ed83ef19.png)
  
9. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Configure-2-2](../media/966e77db-72f5-4524-9c6b-f737498d03c1.png)
  
10. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Configure-2-3](../media/d9d0ddbd-8cfe-4de6-b984-dbbe670dfbaf.png)
  
11. If there are any other MX records in the **Mail Servers ("MX" Record)** section, delete each one by selecting the **Delete** control (trash can). 
    
    ![FreeparkingNZ-BP-Configure-2-5](../media/903edeeb-de9b-4578-aacb-d062d3c3d24e.png)
  
12. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Configure-2-6](../media/dd596641-76a4-46b0-a0fd-cd056a27ed1b.png)
  
13. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Configure-2-7](../media/da5e139d-1f27-4215-b9e8-7f79a4576e0a.png)
  
## Add the six CNAME records that are required for Office 365
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, choose the **Service Management** tab. 
    
    ![FreeparkingNZ-BP-Configure-1-3-1](../media/23a0863e-d792-4026-a05e-6598af21e1fd.png)
  
4. In the **Name Server Records** section, choose **Modify**.
    
    ![FreeparkingNZ-BP-Configure-1-3-2](../media/9767944c-a27a-4b66-949e-d2d3d2c7cf2d.png)
  
5. Choose **Advanced View**.
    
    ![FreeparkingNZ-BP-Configure-1-4-1](../media/f1d95e8d-7a63-4511-b53e-4c8d15c266c3.png)
  
6. Set the **Time to Live (TTL)** value for all records by selecting the **Data** value specified in the following table. 
    
    (Select the **Data** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Data**|
    |:-----|:-----|:-----|
    | *All records*  <br/> |Caching Time (TTL)  <br/> |1 Hour  <br/> |
   
   ![FreeparkingNZ-BP-Configure-1-4-2](../media/7caef32d-ba28-4d57-8ea3-7d694af5a47e.png)
  
7. Choose **Add another record**, and then add six new rows.
    
    ![FreeparkingNZ-BP-Configure-1-4-3](../media/9f204f1f-6078-4504-8ba7-e73bbcd96da6.png)
  
8. In the **Alias ("CNAME" Record)** section, in the boxes for the new records, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    |**Host Name**|**Record Type**|**Data**|
    |:-----|:-----|:-----|
    |autodiscover. *domain_name*  <br/> The **autodiscover** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, autodiscover.fourthcoffee.com)  <br/> |Alias (CNAME)  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*  <br/> The **sip** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, sip.fourthcoffee.com)  <br/> |Alias (CNAME)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*  <br/> The **lyncdiscover** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, lyncdiscover.fourthcoffee.com)  <br/> |Alias (CNAME)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*  <br/> The **enterpriseregistration** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, enterpriseregistration.fourthcoffee.com)  <br/> |Alias (CNAME)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*  <br/> The **enterpriseenrollment** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, enterpriseenrollment.fourthcoffee.com)  <br/> |Alias (CNAME)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![FreeparkingNZ-BP-Configure-3-1](../media/aeee206c-2691-4f76-9b23-09d91c71e728.png)
  
9. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Configure-3-2](../media/89ba008d-6d68-47e0-8805-eadb218ec4cf.png)
  
10. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Configure-3-3](../media/c4c703fb-21a9-414f-aa5c-a805be548229.png)
  
## Add a TXT record for SPF to help prevent email spam
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.
  
1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, choose the **Service Management** tab. 
    
    ![FreeparkingNZ-BP-Configure-1-3-1](../media/23a0863e-d792-4026-a05e-6598af21e1fd.png)
  
4. In the **Name Server Records** section, choose **Modify**.
    
    ![FreeparkingNZ-BP-Configure-1-3-2](../media/9767944c-a27a-4b66-949e-d2d3d2c7cf2d.png)
  
5. Choose **Advanced View**.
    
    ![FreeparkingNZ-BP-Configure-1-4-1](../media/f1d95e8d-7a63-4511-b53e-4c8d15c266c3.png)
  
6. Set the **Time to Live (TTL)** value for all records by selecting the **Data** value specified in the following table. 
    
    (Select the **Data** value from the drop-down list.) 
    
|**Host Name**|**Record Type**|**Data**|
|:-----|:-----|:-----|
| *All records*  <br/> |Caching Time (TTL)  <br/> |1 Hour  <br/> |
   
   ![FreeparkingNZ-BP-Configure-1-4-2](../media/7caef32d-ba28-4d57-8ea3-7d694af5a47e.png)
  
7. Choose **Add another record**.
    
    ![FreeparkingNZ-BP-Configure-1-4-3](../media/9f204f1f-6078-4504-8ba7-e73bbcd96da6.png)
  
8. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Select the **Record Type** value from the drop-down list.) 
    
    |**Host Name**|**Record Type**|**Data**|
    |:-----|:-----|:-----|
    |Use your domain name (for example, fourthcoffee.com)  <br/> |Descriptive (TXT)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.           |
   
    ![FreeparkingNZ-BP-Configure-4-1](../media/8b9949cf-ba70-4e2c-9648-ed35b1ce6185.png)
  
9. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Configure-4-2](../media/f511dbb7-2150-4ed4-980e-71c6ee3f5be0.png)
  
10. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Configure-4-3](../media/0436e682-76fe-4353-8991-ac4e5ce808d5.png)
  
## Add the two SRV records that are required for Office 365
<a name="BKMK_add_SRV"> </a>

1. To get started, go to your domains page at Freeparking.co.nz by using [this link](https://secure.freeparking.co.nz/services/manage). You'll be prompted to log in first.
    
    ![FreeparkingNZ-BP-Configure-1-1](../media/796d4784-affc-4d22-ac1a-35921275a703.png)
  
2. On the **Dashboard** page, in the **Services Overview** area, find the name of the domain you want to update, and then choose **manage** for that domain. 
    
    ![FreeparkingNZ-BP-Configure-1-2](../media/1a7fbd6a-9fa7-4eb5-a1ff-b271c711e10d.png)
  
3. On the **Service** page for your domain, choose the **Service Management** tab. 
    
    ![FreeparkingNZ-BP-Configure-1-3-1](../media/23a0863e-d792-4026-a05e-6598af21e1fd.png)
  
4. In the **Name Server Records** section, choose **Modify**.
    
    ![FreeparkingNZ-BP-Configure-1-3-2](../media/9767944c-a27a-4b66-949e-d2d3d2c7cf2d.png)
  
5. Choose **Advanced View**.
    
    ![FreeparkingNZ-BP-Configure-1-4-1](../media/f1d95e8d-7a63-4511-b53e-4c8d15c266c3.png)
  
6. Set the **Time to Live (TTL)** value for all records by selecting the **Data** value specified in the following table. 
    
    (Select the **Data** value from the drop-down list.) 
    
|**Host Name**|**Record Type**|**Data**|
|:-----|:-----|:-----|
| *All records*  <br/> |Caching Time (TTL)  <br/> |1 Hour  <br/> |
   
   ![FreeparkingNZ-BP-Configure-1-4-2](../media/7caef32d-ba28-4d57-8ea3-7d694af5a47e.png)
  
7. Choose **Add another record**.
    
    ![FreeparkingNZ-BP-Configure-1-4-3](../media/9f204f1f-6078-4504-8ba7-e73bbcd96da6.png)
  
8. In the boxes for the new records, type or copy and paste the values from the following table.
    
    (Select the **Record Type** value from the drop-down list. To view the names of the fields under **Data**, point to each field.)
    
    |**Host Name**|**Record Type**|**First Data Field (Priority)**|**Second Data Field (Weight)**|**Third Data Field (Port)**|**Fourth Data Field (Target)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls. *domain_name*  <br/> The **_sip._tls** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, _sip._tls.fourthcoffee.com)  <br/> |Service (SRV)  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*  <br/> The **_sipfederationtls._tcp** value must be added as a single string to the beginning of your domain_name.  <br/> Use a period (.) to separate values (for example, _sipfederationtls._tcp.fourthcoffee.com)  <br/> |Service (SRV)  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
      
   ![FreeparkingNZ-BP-Configure-5-1](../media/94a3eb0d-1a42-4b37-9b99-5ef6a67d5e33.png)
  
9. Choose **Continue**.
    
    ![FreeparkingNZ-BP-Configure-5-2](../media/28a1e237-a032-4c92-858f-35c4532ea252.png)
  
10. Choose **Finish**.
    
    ![FreeparkingNZ-BP-Configure-5-3](../media/ac82048c-351f-4c9e-b4a2-96873833b059.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
